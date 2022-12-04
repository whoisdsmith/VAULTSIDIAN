# The 7 Most Common Types of Errors in Programming and How to Avoid Them

![The 7 most common types of errors in programming](https://textexpander.com/wp-content/uploads/2020/02/Featured_The-7-Most-Common-Types-of-Errors-in-Programming-and-How-to-Avoid-Them-1200x474.jpg)

The late computer scientist [Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) said, “if debugging is the process of removing bugs, then programming must be the process of putting them in.”

Experiencing different types of errors in programming is a huge part of the development process. The best developers become comfortable navigating the bugs they create and quickly fixing them.

Today, we’re going to talk about the seven most common types of programming errors and how you can avoid them.

## 1\. Syntax Errors

Just like human languages, computer languages have grammar rules. But while humans are able to communicate with less-than-perfect grammar, computers can’t ignore mistakes, i.e. syntax errors.

For example, let’s say the correct syntax for printing something is `print('hello')`, and we accidentally forget one of the parentheses while coding. A syntax error will happen, and this will stop the program from running.

As your proficiency with programming language increases, you will make syntax errors less frequently. The easiest way to prevent them from causing you problems is to be aware of them early. Many text editors or IDEs will come with the ability to warn you about syntax errors at the time of writing.



## 2\. Logic Errors

Logic errors can be the hardest to track down. Everything looks like it is working; you have just programmed the computer to do the wrong thing. Technically the program is correct, but the results won’t be what you expected.

If you didn’t check the requirements beforehand and wrote code to return the oldest user in your system when you needed the newest, you would have a logic error.

[A famous example](https://en.wikipedia.org/wiki/Mars_Climate_Orbiter#Cause_of_failure) happened in 1999 when NASA lost a spacecraft due to miscalculations between English and American units. The software was coded one way but needed to work another.

When writing your tests, show them to the product manager or product owner to confirm that the logic you’re about to write is correct. In the example above, someone closer to the business would have spotted that you aren’t mentioning the fact it is the newest user that is required.

## 3\. Compilation Errors

Some programming languages require a compilation step. Compilation is where your high-level language converts into a lower-level language that the computer can understand better. A compilation or compile-time error happens when the compiler doesn’t know how to turn your code into the lower-level code.

In our syntax error example, if we were compiling `print('hello'`, the compiler would stop and tell us it doesn’t know how to convert this into a lower-level language because it expected a `)` after the `'`.

If there is a compile-time error in your software, you won’t be able to get it tested or launched.

Like syntax errors, you will get better at avoiding these with time, but in general, the best thing you can do is get early feedback when it happens.

Compilation happens across all files of your project at the same time. If you’ve made lots of changes and see lots of compiler warnings or errors, it can be very daunting. By running the compiler often, you will get the feedback you need sooner, and you will more easily know where to address the issues.

## 4\. Runtime Errors

Runtime errors happen as a user is executing your program. The code might work correctly on your machine, but on the webserver, there might be a different configuration, or it might be interacted with in a way that could cause a runtime error.

If your system took the input from a form and tried to capitalize the first letter of a name by doing something like `params[:first_name].capitalize`, this would break if the form was sent without a first name.

Runtime errors are particularly annoying because they directly impact your end user. A lot of these other errors will happen when you’re at your computer working on the code. These errors occur when the system is running and can stop someone from doing what they need to do.

Make sure you have good error reporting in place to capture any runtime errors and automatically open up new bugs in your [ticketing system](https://textexpander.com/blog/write-better-issue-tracking-tickets-consistency-is-key/). Try and learn from each bug report so that in future you can guard against this type of error.

Making use of frameworks and community maintained code is an excellent way of minimizing these types of errors because the code is in many different projects, so it will have already encountered and fixed many issues.

## 5\. Arithmetic Errors

An arithmetic error is a type of logic error but involves mathematics. A typical example when performing a division equation is that you cannot divide by zero without causing an issue. Very few people would write 5 / 0, but you might not think that the size of something in your system might sometimes be zero, which would lead to this type of error.

`ages.max / ages.min` could return an error if either `ages.max` or `ages.min` were zero.

Arithmetic errors can generate logic errors as we’ve discussed, or even run-time errors in the case of divide by zero.

Having functional tests that always include edge-cases like zero, or negative numbers is an excellent way to stop these arithmetic errors in their tracks.

## 6\. Resource Errors

The computer that your program is on will allocate a fixed amount of resources to the running of it. If something in your code forces the computer to try and allocate more resources than it has, it can create a resource error.

If you accidentally wrote a loop that your code could never exit from, you would eventually run out of resources. In this example, the while loop will keep on adding new elements to an array. Eventually, you will run out of memory.
    
    
     while(true)
       my_array << 'new array element'
     end 


Resource errors can be hard to chase down because the machine you’re developing on can often be higher quality than the servers running your code. It is also hard to mimic real-world use from your local computer.

Having good reporting on resource usage on your web servers will flag code that is consuming too much of any type of resource over time.

Resource errors are an example of a type of error in programming that might be something for the operations team to fix rather than developers.

There are lots of load-testing applications and services that you can use to test what happens when multiple people try and run your code at once. Then, you can tune the testing to suit what is realistic for your application.

## 7. Interface Errors
Interface errors occur when there is a disconnect between how you meant your program to be used and how it is actually used. Most things in software follow standards. If input your program receives doesn’t conform to the standards, you might get an interface error.

For example, an interface error might happen if you have an API that requires that specific parameters are set and those parameters are not set.

Unless handled correctly, interface errors will look like an error on your side when it is an error on the caller’s side. This can lead to frustration from both sides.

Having clear documentation and catching these errors to pass back to the caller in a useful way is the best way of saying, “Hey, you haven’t given us what we need to process this request.” This will help keep support costs down and keep your clients happy because they know what they need to fix.

If you don’t catch these errors and pass them back to the caller, they will end up appearing like runtime errors in your reporting, and you will end up guarding against things excessively.

## Errors Are Inevitable

We are, thankfully, decades past needing to have perfectly placed punch-cards appropriately done the first time. Software engineering is hard, requirements are often fuzzy, and the [code changes often](https://textexpander.com/blog/what-is-code-churn-and-how-to-reduce-it/). Try not to beat yourself up and know that we all make mistakes.

Programming errors are inevitable. Get better at spotting them early, but know you will never be perfect.

Hopefully, this guide has prepared you for the different types of errors in programming and made sense of some of the most common error messages for you.

If you’ve been writing code for a long time, please comment below with some errors you’ve made recently, to help serve as reassurance for people who haven’t been writing code as long!

___

#article Errors