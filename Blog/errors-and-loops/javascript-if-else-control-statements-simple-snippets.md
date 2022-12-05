# JavaScript If - Else Control Statements - Simple Snippets

![javascript if else control statements - featured image][image-1]

Conditional statements are used to perform different actions based on different conditions. In this tutorial post we will study and understand the working of **if-eLse Control statements** in Javascript and also see a few example programs and variations of the if-else statements in JavaScript.

**Decision Making** in programming is similar to decision making in real life. In programming also we face some situations where we want a certain block of code to be executed when some condition is fulfilled. This is where conditional control statements come into picture.

JavaScript’s If-Else conditional statements variations :

```
	* **if**
	```
	* **if-else**
	* **nested-if**
	* **if-else-if**

These statements allow you to control the flow of your program’s execution based upon conditions known only during run time.

##### **if statements –**

if statement is the most simple decision making statement. It is used to decide whether a certain statement or block of statements will be executed or not i.e if a certain condition is true then a block of statement is executed otherwise not.

**Syntax**:
```
if(condition) 
{
   // Statements to execute if
   // condition is true
}


Here, **condition** after evaluation will be either true or false. if statement accepts **boolean** values – if the value is true then it will execute the block of statements under it.


**Flow Chart**:


![if statement flow diagram in javascript](https://simplesnippets.tech/wp-content/uploads/2018/10/if-statement-flow-diagram-in-javascript.jpg)


**Program Example **:


<script type = "text/javaScript"> 

// JavaScript program to illustrate If statement 

var i = 10; 

if (i > 15) 
  document.write("10 is less than 15"); 

// This statement will be executed 
// as if considers one statement by default 
document.write("If block not executed"); 

< /script>


**Output :**


If block not executed


##### **if – else statements –**


The if statement alone tells us that if a condition is true it will execute a block of statements and if the condition is false it won’t. But what if we want to do something else if the condition is false. Here comes the else statement. We can use the else statement with if statement to execute a block of code when the condition is false.


**Syntax**:


if (condition)
{
    // Executes this block if
    // condition is true
}
else
{
    // Executes this block if
    // condition is false
}


**Flow Chart**:


![if-else statement flow diagram in javascript](https://simplesnippets.tech/wp-content/uploads/2018/10/if-else-statement-flow-diagram-in-javascript.jpg)


**Program Example **:


<html>
 <head>
   <title>IF-Else if - Else Control Statments in javascript</title>
  <script type="text/javascript">
   /*Q1) Find whether is number is EVEN or ODD*/
   var x=7;
   if(x%2==0)
   {
    document.write("<h3>Even Number</h3>");    
   }
   else
   {
    document.write("<h3>Odd Number</h3>"); 
   }

  </script>
 </head>
 <body>
 </body>
</html>


**Output :**


Odd Number


##### **Nested if statements –**


A nested if is an if statement that is the target of another if or else. Nested if statements means an if statement inside an if statement. Yes, JavaScript allows us to nest if statements within if statements. i.e, we can place an if statement inside another if statement.


**Syntax:**


if (condition1) 
{
   // Executes when condition1 is true
   if (condition2) 
   {
      // Executes when condition2 is true
   }
}


**Flow Chart**:


![nested if statement flow diagram in javascript](https://simplesnippets.tech/wp-content/uploads/2018/10/nested-if-statement-flow-diagram-in-javascript.jpg)


**Program Example **:


<html>
 <head>
   <title>IF-Else if - Else Control Statments in javascript</title>
  <script type="text/javascript">
   /*Q3) Find if a number is positive and even*/
   var x=8;
   if(x>0)
   {
    document.write("<h3>Positive Number</h3>");  
    if(x%2==0)
    {
     document.write("<h3>Positive & Even Number</h3>");  
    }  
   }

  </script>
 </head>
 <body>
 </body>
</html>


**Output :**


Positive & Even Number


##### **if-else if ladder statements –**


If you have multiple statements, you can use if-else if ladder to check for multiple conditions. As soon as one of the conditions controlling the if is true, the statement associated with that if is executed, and the rest of the ladder is bypassed. If none of the conditions is true, then the final else statement will be executed.


**Syntax:**


if (condition)
    statement;
else if (condition)
    statement;
.
.
else
    statement;


**Flow Chart**:



**Program Example **:


<html>
 <head>
   <title>IF-Else if - Else Control Statments in javascript</title>
  <script type="text/javascript">
   /*Q1) Find if a number is positive, negative or 0*/
   var x=8;
   if(x>0)
   {
    document.write("<h3>Positive Number</h3>");  
   }
   else if(x<0)
   {
    document.write("<h3>Negative Number</h3>"); 
   }
   else
   {
    document.write("<h3>Number is 0</h3>"); 
   }

  </script>
 </head>
 <body>
 </body>
</html>


**Output **:


Positive Number


##### **Watch it on YouTube**
```


---- 

[image-1]:	https://simplesnippets.tech/wp-content/uploads/2018/10/javascript-if-else-control-statements-featured-image.jpg

#article