# JS Infinite Loops—Killing ‘em

![][image-1]

Having worked on Analytics and ChatBot platforms, one important thing I observed is, you will have to be fast in developing solutions and the requirements will keep coming crazily. To meet the competition, I had to develop solution in both these products which allows the users to write code to create solutions without having to add new features to the product. It helped a lot to showcase or convert any abstract thought to working solution in matter of minutes without undergoing any product deployment or testing cycle.

I had primarily worked on the data visualization area of the product and we realized soon we cannot accommodate all kinds of customers’ requirements(every possible chart type). Some of these requirements were not anticipated and some of them were not worthy to include in the product. To solve this problem, I had to develop a feature in which there will be a code editor where people can write JS code to develop visualization of any sort. The code they write will be run in an iframe with the required data along with jQuery and D3.

Similarly, in case of ChatBots, we had to provide a JS editor in which people do loads of state management, external API calls and data transformations. This untrusted code will run in [NodeJS VM][1] which is a controlled sandbox where only a few modules(xml parser, JSON parser, node-fetch, JWT token creation, cryptojs) are available via context, not even *require*, *fs*, *http, etc,* are available. The VM has timeout option through which we can specify when the VM should terminate the operation and exit.

![][image-2]

Image courtesy: [https://blog.codepen.io/2016/06/08/can-adjust-infinite-loop-protection-timing/][2]

The biggest problem with allowing people to write code is, what if some amateur developer writes a condition that will create infinite loops inside an **async code block**(promise callback for example)! If the code will execute in browsers, it will affect only the users who view the result. But in case of Node.js, this will have the ability to keep the event loop completely busy that the whole application will become unresponsive to any new requests. That is as good as the system is down. [Check this thread to understand more.][3] Unfortunately it has no solution from the VM implementation of Node.js.

We can solve this problem by moving this whole VM to execute in a child process and kill the process after it is done or exceeds the given time limit. If we want to fork one child process per request for VM every time, it might go uncontrolled. It is a bad idea to keep creating new processes. What if we keep only one process that creates multiple VMs to run the code on demand. Still it won’t solve the problem because the processes cannot identify which VM is executing the infinite loop as these problem causing functions are async and running in altogether a different frame. In this case if we kill the whole process by time limit, it will kill other VMs too which were running other users’ code. That is a again not acceptable.

To solve this problem, the only solution I could figure out is code injection. Inject code into every looping block and also at the end of function block(if needed) to throw timeout error after it exceeds the time limit. As far as I know, there are very few ways to create infinite loop in JS.

while loop

for loop

do..while loop

recursion

Recursion cannot keep the system occupied forever as it will throw “Maximum Call Stack Size Reached” exception which can be caught and that will free the event loop to serve next request.

So potentially, *while, for and do while* are the three constructs that can create infinite loops (Correct me if I am wrong). Back to code injection, we cannot simply inject code into a program using string match. That is very dangerous and could go wrong easily. The best solution to inject code at right place is using [AST(Abstract Syntax Tree)][4]. Take a look at how AST will look like in [ASTExplorer][5]. With AST, we don’t have to do any guess work, but by traversing through the nodes, we will be able to find all *while, for or do while* loops and inject code precisely.

Feeling nostalgia?? When we speak about AST and code injection, if you are using ES6, first thing that will come to your mind is Babel. Using [babel-core][6] we can create AST out of our JS code. Babel also provides a way to filter a specific statement type(while statement or for statement) using visitor pattern. [Check this plugins development handbook from Babel.][7] With this visitor pattern, we can find all while, for, do..while loops in all of our code and transform them to anything we want. In this case we will inject a simple condition to throw exception if it exceeds time limit.

```
**var **fs = require("fs");  
**var **babel = require("babel-core");  
**var **loopcontrol = require("./loopcontrol");  
// read the filename from the command line arguments  
**var **fileName = "test.js";  
// read the code from this file  
fs.readFile(fileName, **function**(err, data) {  
   **if **(err) **throw **err;  
   // convert from a buffer to a string  
   **var **src = data.toString();  
   // use our plugin to transform the source  
   **var **out = **_babel.transform_**(src, {  
      plugins: [loopcontrol]  
   });  
   // print the generated code to screen  
   console.log(out.code);  
});

The code above reads the JS code from _test.js_ and converts it to AST using **_babel.transform_** method. The code injection happens via the plugin(loopcontrol) that I have created. Let’s see the content of _loopcontrol.js_.

module.exports = **function**(babel) {  
   **var **t = babel.types;  
   **return **{  
      visitor: {  
         WhileStatement: **function transformWhile**(path) {  
            **let **variableName = path.scope  
.generateUidIdentifier("timer");  
            **let **declaration = t.declareVariable(variableName);  
            path.scope.parent.push(declaration);  
            **let **definition = t.assignmentExpression(  
               "=",  
               variableName,  
               t.callExpression(t.memberExpression(t.identifier("Date"), t.identifier("now")), [])  
            );  
            path.insertBefore(t.expressionStatement(definition));  
            **const **lhs = t.parenthesizedExpression(t.binaryExpression("+", variableName, t.NumericLiteral(30000)));  
            path  
               .get("body")  
               .pushContainer(  
                  "body",  
                  t.ifStatement(  
                     t.binaryExpression(">", t.callExpression(t.memberExpression(t.identifier("Date"), t.identifier("now")), []), lhs),  
                     t.throwStatement(t.stringLiteral("Execution Timedout")),  
                     **null  
                  **)  
               );  
         }  
      }  
   };  
};

In this snippet, babel calls the **_transformWhile_** method every time it encounters a _while_ statement. Inside the **_transformWhile_** method, **_[babel-types_**](https://www.npmjs.com/package/babel-types) is used to create a variable declaration(__timer_) to store current timestamp and then define the variable with **_Date.now()_**_ above the while loop_.**_ _**Then, an if statement is injected into the while statement’s body which checks if the current timestamp is greater that 30 seconds from the initialization and throws an error if true.

Here you can see before and after code injection.

//Before code injection  
Promise._resolve_().then(() => {  
    **while**(**true**) {  
        **let **x = 1;  
    }  
});//After code injection  
Promise._resolve_().then(() => {  
    **var **_timer;  
    _timer = Date.now();  
    **while **(**true**) {  
        **let **x = 1;  
        **if **(Date.now() > (_timer + 30000)) **throw **"Execution TIMEOUT";  
    }  
});

This provides the ability to transform code accurately to any extent thanks to Babel. Now we can apply the same solution to any loop or any potential malicious pattern of code that we encounter. There is a standalone version of Babel which allows us to do it in browsers directly.

Before executing the code we can perform the code injection which will solve the problem of Infinite loops from untrusted code in JS execution environments like VM.

ASTs are awesome.

Hope this saves someone’s time.
```

----

[1]:	https://nodejs.org/api/vm.html
[2]:	https://blog.codepen.io/2016/06/08/can-adjust-infinite-loop-protection-timing/
[3]:	https://github.com/nodejs/node/issues/3020
[4]:	https://en.wikipedia.org/wiki/AST
[5]:	https://astexplorer.net/
[6]:	https://github.com/babel/babel/tree/master/packages/babel-core
[7]:	https://github.com/thejameskyle/babel-handbook/blob/master/translations/en/plugin-handbook.md

[image-1]:	https://miro.medium.com/max/1626/1*pq0y-SfP50SkKnew5lgoDA.png
[image-2]:	https://miro.medium.com/max/1323/1*JgljmkkE1mprwe7O6C_Cew.png

#article #loops
