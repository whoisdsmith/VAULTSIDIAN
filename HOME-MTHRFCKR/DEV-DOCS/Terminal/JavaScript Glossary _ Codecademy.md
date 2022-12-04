# JavaScript Glossary | Codecademy

_Update: Cheat Sheets BETA is here!_

  * Introduction to JavaScript: [Introduction](https://www.codecademy.com/learn/introduction-to-javascript/modules/learn-javascript-introduction/reference)
  * Introduction to JavaScript: [Conditionals](https://www.codecademy.com/learn/introduction-to-javascript/modules/learn-javascript-control-flow/reference)
  * Introduction to JavaScript: [Functions](https://www.codecademy.com/learn/introduction-to-javascript/modules/learn-javascript-functions/reference)
  * Introduction to JavaScript: [Scope](https://www.codecademy.com/learn/introduction-to-javascript/modules/learn-javascript-scope/reference)

# Arrays

## Accessing array elements

You can get elements out of arrays if you know their index. Array elements’ indices start at 0 and increment by 1, so the first element’s index is 0, the second element’s index is 1, the third element’s index is 2, etc.

**Syntax**
    
    
    array[index];
    
    
    
    
    **Example**
    
    
    
    
    
    var primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37];
    
    primes[0]; 
    
    primes[3]; 
    
    primes[150]; 
    
    
    
    
    ## Array literals
    
    
    
    
    You can create arrays in two different ways. The most common of which is to list values in a pair of square brackets. JavaScript arrays can contain any types of values and they can be of mixed types.
    
    
    
    
    **Syntax**
    
    
    
    
    
    const arrayName = [element0, element1, ..., elementN]
    
    
    
    
    **Example**
    
    
    
    
    
    const primes = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37];
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array>
    
    
    
    
    ## Multi-dimensional Arrays
    
    
    
    
    A two-dimensional array is an array within an array. If you fill this array with another array you get a three-dimensional array and so on.
    
    
    
    
    **Example**
    
    
    
    
    
    const multidimensionalArray = [[1,2,3],[4,5,6],[7,8,9]]
    
    
    
    
    ## Array constructor
    
    
    
    
    You can also create an array using the Array constructor.
    
    
    
    
    **Example**
    
    
    
    
    
    const stuff = new Array();
    
    
    
    
    stuff[0] = 34;
    
    stuff[4] = 20;
    
    
    
    
    stuff;
    
    
    
    
    **Example**
    
    
    
    
    
    const myArray = new Array(45 , 'Hello World!' , true , 3.2 , undefined);
    
    console.log(myArray);
    
    
    
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Example.3A_Creating_an_array>
    
    
    
    
    ## Accessing nested array elements
    
    
    
    
    Accessing multi-dimensional array elements is quite similar to one-dimension arrays. They are accessed by using [index][index]….. (number of them depends upon the number of arrays deep you want to go inside).
    
    
    
    
    **Syntax**
    
    
    
    
    
    array[index][index] 
    
    
    
    
    **Example**
    
    
    
    
    
    const myMultiArray = [
    
      [1, 2, 3, 4, 5, [1, 2, 3, 4, 5] ],
    
      [6, 7, 8, 9, 10, [1, 2, 3, 4, 6] ],
    
      [11, 12, 13, 14, 15, [1, 2, 3, 4, 5] ],
    
      [16, 17, 18, 19, 20, [1, 2, 3, 4, 5] ]
    
    ];
    
    
    
    
    console.log(myMultiArray[1][5][4]);
    
    
    
    
    # Booleans
    
    
    
    
    ## Boolean literals
    
    
    
    
    **Syntax**
    
    
    
    
    
    true
    
    false
    
    
    
    
    ## Boolean logical operators
    
    
    
    
    **Syntax**
    
    
    
    
    
    expression1 && expression2
    
    
    
    
    expression3 || expression4
    
    
    
    
    !expression5
    
    
    
    
    **Example**
    
    
    
    
    
    if (true && false) {;
    
      
    
    }
    
    
    
    
    if (false || true) {
    
      
    
    }
    
    
    
    
    if (!false) {
    
      
    
    }
    
    
    
    
    !!true 
    
    
    
    
    **Example**
    
    
    
    
    
    if (!false && ( false || (false && true) )) {
    
      console.log('Guess what...');
    
    }
    
    
    
    
    
    
    
    **Example**
    
    
    
    
    
    
    
    
    
    
    if (true && !!false || true) {
    
      console.log('Guess again ??');
    
    }
    
    
    
    
    
    
    
    **Example**
    
    
    
    
    
    
    
    
    
    
    !false && !!false 
    
    
    
    
    ## Comparison operators
    
    
    
    
    **Syntax**
    
    
    
    
    
    x === y 
    
    x !== y 
    
    x <= y 
    
    x >= y 
    
    x < y 
    
    x > y 
    
    
    
    
    ## “Truthy” and “Falsy”
    
    
    
    
    Only Boolean literals (true and false) assert truth or false, but there are some other ways too to derive true or false. Have a look at the examples.
    
    
    
    
    **Example**
    
    
    
    
    
    if (1) {
    
      
    
      console.log('True!');
    
    }
    
    
    
    
    if (0) {
    
      
    
      console.log('I doubt if this gets executed');
    
    }
    
    
    
    
    if ('Hello') {
    
      
    
      console.log('So, any non-empty String is also true.'); 
    
    }
    
    
    
    
    if ('') {
    
      
    
      console.log('Hence , an empty String is false');
    
    }
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Glossary/Falsy>
    
    
      * <https://developer.mozilla.org/en-US/docs/Glossary/Truthy>
    
    
    
    
    ## == vs. ===
    
    
    
    
    A simple explanation would be that == does just value checking (no type checking ), whereas, === does both value checking and type checking. Seeing the examples may make it all clear. It is always advisable that you never use ==, because == often produces unwanted results.
    
    
    
    
    **Syntax**
    
    
    
    
    
    expression == expression
    
    expression === expression
    
    
    
    
    **Example**
    
    
    
    
    
    '1' == 1  
    
    '1' === 1 
    
    
    
    
    true == 1  
    
    true === 1 
    
    
    
    
    # Code Comments
    
    
    
    
    Code comments are used for increasing the readability of the code.If you write 100 lines of code and then forget what each function did, it’s not useful at all. Comments are like notes, suggestions, warnings, etc. that you can put for yourself. Code comments are not executed
    
    
    
    
    ## Single Line Comment
    
    
    
    
    Anything on the line following // will be a comment while anything before will still be code.
    
    
    
    
    **Syntax**
    
    
    
    
    
    console.log('This code will be run');
    
    
    
    
    ## Multi-Line Comment
    
    
    
    
    Anything between /* and */ will be a comment.
    
    
    
    
    **Syntax**
    
    
    
    
    
    
    
    **Example**
    
    
    
    
    
    
    
    # Console
    
    
    
    
    ## console.log
    
    
    
    
    Prints text to the console. Useful for debugging.
    
    
    
    
    **Example**
    
    
    
    
    
    const name = 'Codecademy';
    
    console.log(name);
    
    
    
    
    ## console.time
    
    
    
    
    This function starts a timer which is useful for tracking how long an operation takes to happen.You give each timer a unique name, and may have up to 10,000 timers running on a given page.When you call console.timeEnd() with the same name, the browser will output the time, in milliseconds, that elapsed since the timer was started.
    
    
    
    
    **Syntax**
    
    
    
    
    
    console.time(timerName);
    
    
    
    
    **Example**
    
    
    
    
    
    console.time('My Math');
    
    const x = 5 + 5;
    
    console.log(x);
    
    console.timeEnd('My Math');
    
    console.log('Done the math.');
    
    
    
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/API/console.time>
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/API/console.timeEnd>
    
    
    
    
    ## console.timeEnd()
    
    
    
    
    Stops a timer that was previously started by calling console.time().
    
    
    
    
    **Syntax**
    
    
    
    
    
    console.timeEnd(timerName);
    
    
    
    
    **Example**
    
    
    
    
    
    console.time('My Math');
    
    const x = 5 + 5;
    
    console.log(x);
    
    console.timeEnd('My Math');
    
    
    
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/API/console.timeEnd>
    
    
    
    
    # Functions
    
    
    
    
    A function is a JavaScript procedure—a set of statements that performs a task or calculates a value.It is like a reusable piece of code. Imagine , having 20 for loops ,and then having a single function to handle it all . To use a function, you must define it somewhere in the scope from which you wish to call it. A function definition (also called a function declaration) consists of the function keyword, followed by the name of the function, a list of arguments to the function, enclosed in parentheses and separated by commas, the JavaScript statements that define the function, enclosed in curly braces, { }.
    
    
    
    
    **Syntax**
    
    
    
    
    
    function name(argument1 , argument2, ){
    
      statement1;
    
      statement2;
    
      
    
      statementN;
    
    } 
    
    
    
    
    **Example**
    
    
    
    
    
    function greet(name) {
    
      return 'Hello' + name + '!';
    
    }
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions>
    
    
    
    
    ## Function calling
    
    
    
    
    **Syntax**
    
    
    
    
    
    functionName(argument1, argument2, ..., argumentN);
    
    
    
    
    **Example**
    
    
    
    
    
    greet('Anonymous');
    
    
    
    
    ## Function hoisting
    
    
    
    
    The two ways of declaring functions produce different results. Declaring a function one way “hoists” it to the top of the call, and makes it available before it’s actually defined.
    
    
    
    
    **Example**
    
    
    
    
    
    hoistedFunction(); 
    
    notHoistedFunction(); 
    
    
    
    
    function hoistedFunction () {
    
      console.log('Hello! I am defined immediately!');
    
    }
    
    
    
    
    var notHoistedFunction = function () {
    
      console.log('I am not defined immediately.');
    
    }
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Glossary/Hoisting>
    
    
    
    
    # If statement
    
    
    
    
    It simply states that if this condition is true, do this, else do something else (or nothing). It occurs in varied forms.
    
    
    
    
    # if
    
    
    
    
    **Syntax**
    
    
    
    
    
    if (condition) {
    
      
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    if (answer === 42) {
    
      console.log('Told you so!');
    
    }
    
    
    
    
    ## else
    
    
    
    
    A fallback to an if statement. This will only get executed if the previous statement did not.
    
    
    
    
    **Syntax**
    
    
    
    
    
    
    
    if (condition) {
    
      
    
    } else {
    
      
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    if (animal == 'dog') {
    
      console.log('Bark, bark!');
    
    } else {
    
      console.log('Meow!');
    
    }
    
    
    
    
    ## else if
    
    
    
    
    This is like an else statement, but with its own condition. It will only run if its condition is true, and the previous statement’s condition was false.
    
    
    
    
    **Syntax**
    
    
    
    
    
    if (condition1) {
    
      statement1;
    
    } else if (condition2) {
    
      statement2;
    
    } else {
    
      statement3;
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    if (someNumber > 10) {
    
      console.log('Numbers larger than 10 are not allowed.');
    
    } else if (someNumber < 0) {
    
      console.log('Negative numbers are not allowed.');
    
    } else {
    
      console.log('Nice number!');
    
    }
    
    
    
    
    # Loops
    
    
    
    
    ## For Loops
    
    
    
    
    You use for loops, if you know how often you’ll loop. The most often used varName in loops is i.
    
    
    
    
    **Syntax**
    
    
    
    
    
    for ([let i = startValue]; [i < endValue]; [i+=stepValue]) {
    
      
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    for (let i = 0; i < 5; i++) {
    
      console.log(i); 
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    let i;  
    
    for (i = 10; i >= 1; i--) {
    
        console.log(i); 
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    let i = 9;
    
    for(;;){
    
        if(i === 0) {
    
          break;
    
        }
    
        console.log(i);
    
        i--;
    
    }
    
    
    
    
    ## While Loops
    
    
    
    
    You use while loops, if you don’t know how often you’ll loop.
    
    
    
    
    **Syntax**
    
    
    
    
    
    while (condition) {
    
      
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    let x = 0;
    
    while (x < 5) {
    
      console.log(x); 
    
      x++;
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    let x = 10;
    
    while (x <= 5) {
    
        console.log(x); 
    
        x++;
    
    }
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while>
    
    
    
    
    ## Do While Loops
    
    
    
    
    You use do while loops, if you have to loop at least once, but if you don’t know how often.
    
    
    
    
    **Syntax**
    
    
    
    
    
    do {
    
      
    
    } while (condition);
    
    
    
    
    **Example**
    
    
    
    
    
    let x = 0;
    
    do {
    
        console.log(x);  
    
        x++;
    
    } while (x < 5);
    
    
    
    
    **Example**
    
    
    
    
    
    let x = 10;
    
    do {
    
        console.log(x); 
    
        x++;
    
    } while (x <= 5);
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while>
    
    
    
    
    # Math
    
    
    
    
    ## .random()
    
    
    
    
    Returns a random number between 0 and 1.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.random()
    
    
    
    
    **Example**
    
    
    
    
    
    Math.random(); 
    
    
    
    
    ## .floor()
    
    
    
    
    Returns the largest integer less than or equal to a number.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.floor(expression)
    
    
    
    
    **Example**
    
    
    
    
    
    Math.floor(9.99); 
    
    Math.floor(1 + 0.5); 
    
    Math.floor(Math.random() * x + 1); 
    
    
    
    
    ## .pow()
    
    
    
    
    Returns base raised to exponent.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.pow(base, exponent)
    
    
    
    
    **Example**
    
    
    
    
    
    Math.pow(2,4); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/pow>
    
    
    
    
    ## .ceil()
    
    
    
    
    Returns the smallest integer greater than or equal to a number.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.ceil(expression)
    
    
    
    
    **Example**
    
    
    
    
    
    Math.ceil(45.4); 
    
    Math.ceil(4 - 1.9); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil>
    
    
    
    
    ## .PI
    
    
    
    
    Returns the ratio of the circumference of a circle to its diameter, approximately 3.14159 or in better terms, the value of PI (π). Note in syntax , we do not put () at the end of Math.PI because Math.PI is not a function.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.PI
    
    
    
    
    **Example**
    
    
    
    
    
    Math.round(Math.PI); 
    
    Math.ceil(Math.PI); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/PI>
    
    
    
    
    ## .sqrt()
    
    
    
    
    Returns the square root of a number.
    
    
    
    
    **Syntax**
    
    
    
    
    
    Math.sqrt(expression)
    
    
    
    
    **Example**
    
    
    
    
    
    Math.sqrt(5+4); 
    
    Math.sqrt(Math.sqrt(122+22) + Math.sqrt(16)); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt>
    
    
    
    
    # Numbers
    
    
    
    
    # % (Modulus)
    
    
    
    
    It returns the remainder left after dividing the left hand side with the right hand side.
    
    
    
    
    **Syntax**
    
    
    
    
    
    number1 % number2
    
    
    
    
    **Example**
    
    
    
    
    
    14 % 9 
    
    
    
    
    ## isNaN()
    
    
    
    
    Returns true if the given number is not a number, else returns false.
    
    
    
    
    **Syntax**
    
    
    
    
    
    isNaN([value])
    
    
    
    
    **Example**
    
    
    
    
    
    const userInput = prompt('Enter a number'); 
    
    
    
    
    if (isNaN(userInput)) {
    
      console.log('I told you to enter a number.');
    
    }
    
    
    
    
    
    
    
    
    
    
    if (isNaN('3')) {
    
      console.log('bad');
    
    }
    
    
    
    
    
    
    
    ## Basic Arithmetic
    
    
    
    
    Doing basic arithmetic is simple.
    
    
    
    
    **Syntax**
    
    
    
    
    
    4 + 5;  
    
    4 * 5;  
    
    5 - 4;  
    
    20 / 5; 
    
    
    
    
    ## Prefix and Postfix increment/decrement operators
    
    
    
    
    Prefix increment / decrement operators are operators that first increase the value of the variable by 1 (increment) or decrease the value of an expression / variable by 1 (decrement) and then return this incremented / decremented value. They are used like ++(variable) [increment] or --(varaible) [decrement] On the other hand , Postfix increment / decrement operators are operators that first return the value of the variable and then increase the value of that variable by 1 (increment) or decrease the value of the variable by 1 (decrement) . They are used like (variable)++ [increment] or (varaible)-- [decrement].
    
    
    
    
    **Syntax**
    
    
    
    
    
    --variable
    
    ++variable
    
    variable--
    
    variable++
    
    
    
    
    **Example**
    
    
    
    
    
    
    
    let x = 15; 
    
    const y = x++;
    
    console.log(y); 
    
    console.log(x); 
    
    
    
    
    let a = 15; 
    
    const b = ++a;
    
    console.log(b); 
    
    console.log(a); 
    
    
    
    
    # Objects
    
    
    
    
    ## Object Literals
    
    
    
    
    **Syntax**
    
    
    
    
    
    {
    
      'property 1': value1,
    
      property2: value2,
    
      number: value3
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    var obj = {
    
      name: 'Bob',
    
      married: true,
    
      'mother\'s name': 'Alice',
    
      'year of birth': 1987,
    
      getAge: function () {
    
        return 2012 - obj['year of birth'];
    
      },
    
      1: 'one'
    
    };
    
    
    
    
    ## Property Access
    
    
    
    
    **Syntax**
    
    
    
    
    
    name1[string]
    
    name2.identifier
    
    
    
    
    **Example**
    
    
    
    
    
    obj['name'];  
    
    obj.name;     
    
    obj.getAge(); 
    
    
    
    
    # OOP
    
    
    
    
    ## Classes
    
    
    
    
    A class can be thought of as a template to create many objects with similar qualities. Classes are a fundamental component of object-oriented programming (OOP).
    
    
    
    
    **Syntax**
    
    
    
    
    
    SubClass.prototype = new SuperClass();
    
    
    
    
    **Example**
    
    
    
    
    
    const Lieutenant = function (age) {
    
      this.rank = 'Lieutenant';
    
      this.age = age;
    
    };
    
    
    
    
    Lieutenant.prototype = new PoliceOfficer();
    
    
    
    
    Lieutenant.prototype.getRank = function () {
    
      return this.rank;
    
    };
    
    
    
    
    const John = new Lieutenant(67);
    
    
    
    
    John.getJob(); 
    
    John.getRank(); 
    
    John.retire(); 
    
    
    
    
    # Popup boxes
    
    
    
    
    ## alert
    
    
    
    
    Display an alert dialog with the specified message and an OK button. The alert dialog should be used for messages which do not require any response on the part of the user, other than the acknowledgment of the message.
    
    
    
    
    **Syntax**
    
    
    
    
    
    alert(message);
    
    
    
    
    **Example**
    
    
    
    
    
    alert('Hello World');
    
    
    
    
    ## confirm
    
    
    
    
    Displays a dialog with the specified message and two buttons, OK and Cancel.
    
    
    
    
    **Syntax**
    
    
    
    
    
    confirm('message') 
    
    
    
    
    **Example**
    
    
    
    
    
    
    
    if (confirm('Are you sure you want to delete this post?')) {
    
      deletePost();
    
    }
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/API/window.confirm>
    
    
    
    
    ## prompt
    
    
    
    
    The prompt() displays a dialog with an optional message prompting the user to input some text. If the user clicks the “Cancel” button, null is returned.
    
    
    
    
    **Syntax**
    
    
    
    
    
    prompt(message);
    
    
    
    
    **Example**
    
    
    
    
    
    var name = prompt('Enter your name:');
    
    console.log('Hello ' + name + '!');
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/API/window.prompt>
    
    
    
    
    # Strings
    
    
    
    
    Strings are text. They are denoted by surrounding text with either single or double quotes.
    
    
    
    
    **Syntax**
    
    
    
    
    
    "string of text"
    
    'string of text'
    
    
    
    
    ## Concatenation
    
    
    
    
    **Syntax**
    
    
    
    
    
    string1 + string2
    
    
    
    
    **Example**
    
    
    
    
    
    'some' + 'text'; 
    
    const first = 'my';
    
    const second = 'string';
    
    const union = first + second; 
    
    
    
    
    ## .length
    
    
    
    
    Returns the length of the string.
    
    
    
    
    **Syntax**
    
    
    
    
    
    string.length
    
    
    
    
    **Example**
    
    
    
    
    
    'My name'.length 
    
    ''.length 
    
    
    
    
    ## .toUpperCase(), .toLowerCase()
    
    
    
    
    Changes the cases of all the alphabetical letters in the string.
    
    
    
    
    **Example**
    
    
    
    
    
    'my name'.toUpperCase(); 
    
    'MY NAME'.toLowerCase(); 
    
    
    
    
    ## .trim()
    
    
    
    
    Removes whitespace from both ends of the string.
    
    
    
    
    **Syntax**
    
    
    
    
    
    string.trim()
    
    
    
    
    **Example**
    
    
    
    
    
    '       a        '.trim(); 
    
    '     a  a       '.trim(); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/Trim>
    
    
    
    
    ## .replace()
    
    
    
    
    Returns a string with the first match substring replaced with a new substring.
    
    
    
    
    **Example**
    
    
    
    
    
    'original string'.replace('original', 'replaced'); 
    
    
    
    
    ## .charAt()
    
    
    
    
    Returns the specified character from a string. Characters in a string are indexed from left to right. The index of the first character is 0, and the index of the last character in a string called stringName is stringName.length - 1. If the index you supply is out of range, JavaScript returns an empty string.
    
    
    
    
    **Syntax**
    
    
    
    
    
    string.charAt(index) 
    
    
    
    
    **Example**
    
    
    
    
    
    'Hello World!'.charAt(0); 
    
    'Hello World!'.charAt(234); 
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt>
    
    
    
    
    ## .substring()
    
    
    
    
    Returns the sequence of characters between two indices within a string.
    
    
    
    
    **Syntax**
    
    
    
    
    
    string.substring(indexA[, indexB])
    
    
    
    
    **Example**
    
    
    
    
    
    'adventures'.substring(2,9); 
    
    'hello'.substring(1); 
    
    'Web Fundamentals'.substring(111); 
    
    'In the market'.substring(2,999); 
    
    'Fast and efficient'.substring(3,3); 
    
    'Go away'.substring('abcd' , 5); 
    
    
    
    
    ## .indexOf()
    
    
    
    
    Returns the index within the calling String object of the first occurrence of the specified value, starting the search at fromIndex, Returns -1 if the value is not found. The .indexOf() method is case sensitive.
    
    
    
    
    **Syntax**
    
    
    
    
    
    string.indexOf(searchValue[, fromIndex]) 
    
    
    
    
    **Example**
    
    
    
    
    
    'My name is very long.'.indexOf('name'); 
    
    'My name is very long.'.indexOf('Name'); 
    
    'Where are you going?'.indexOf('are', 11); 
    
    'Learn to Code'.indexOf(''); 
    
    'Learn to Code'.indexOf('', 3); 
    
    'Learn to Code'.indexOf('', 229); returns 13 , which is the string.length
    
    
    
    
    **Read more**
    
    
    
    
    
    
      * <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf>
    
    
    
    
    # Switch statements
    
    
    
    
    Acts like a big if / else if / else chain. Checks a value against a list of cases, and executes the first case that is true. It goes on executing all other cases it finds after the first true case till it finds a breaking statement, after which it breaks out of the switch If it does not find any matching case, it executes the default case.
    
    
    
    
    **Syntax**
    
    
    
    
    
    switch (expression) {
    
      case label1:
    
        statements1;
    
        
    
      case label2
    
        statements2;
    
        
    
      ...
    
      case labelN:
    
        statementsN;
    
        
    
      default:
    
        defaultStatement;
    
        
    
    }
    
    
    
    
    **Example**
    
    
    
    
    
    const weather = "clear";
    
    
    
    
    switch (weather) {
    
      case 'clear':
    
        console.log("Beautiful day!");
    
      case 'cloudy':
    
        console.log('I wish the sun were out!');
    
      default:
    
        console.log('Some weather, huh?');
    
    }
    
    
    
    
    
    
    
    # Ternary Operator
    
    
    
    
    The ternary operator is usually used as a shortcut for the if statement.
    
    
    
    
    **Syntax**
    
    
    
    
    
    condition ? expr1 : expr2
    
    
    
    
    **Example**
    
    
    
    
    
    const grade = 85;
    
    console.log('You ' + (grade > 50 ? 'passed!' : 'failed!'));
    
    
    
    
    
    
    
    
    
    
    # Variables
    
    
    
    
    ## Variable Assignment
    
    
    
    
    **Syntax**
    
    
    
    
    
    var name = value;
    
    
    
    
    **Example**
    
    
    
    
    
    var x = 1;
    
    var myName = 'Bob';
    
    var hisName = myName;
    
    
    
    
    ### ES6 const and let
    
    
    
    
    **Syntax**
    
    
    
    
    
    let message = 'I can be reassigned!';
    
    const message2 = 'I cannot be reassigned';
    
    
    
    
    **Scope**
    
    
    
    
    let and const are both scoped to the block in which they are initialized. This can be a smaller scope than var variables, which are scoped to the function in which they are initialized.
    
    
    
    
    
    const dog = true;
    
    if (dog) {
    
      let mood = 'happy'
    
    }
    
    console.log(mood)
    
    
    
    
    ## Variable Reassignment
    
    
    
    
    **Syntax**
    
    
    
    
    
    varname = newValue
    
    
    
    
    **Example**
    
    
    
    
    
    let name = 'Michael'
    
    name = 'Samuel'
    
    
    
    
    const variables cannot be reassigned and attempting to do so will throw a TypeError:
    
    
    
    
    **Example**
    
    
    
    
    
    const name = 'Michael'
    
    name = 'Samuel'
    
    
    
    
    
    


___

#article #javascript