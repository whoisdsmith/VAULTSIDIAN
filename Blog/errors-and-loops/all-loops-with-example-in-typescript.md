# All loops with example in TypeScript - LearnCodeWeb

[ ![All loops with example in TypeScript][image-1] ][1]

---- 

In this chapter, we will discuss in detail definite and indefinite loops in [TypeScript][2].

Sometimes you face situations when you want a block of code to run several times in your program. In general, statements run consecutively. The first statement in a function runs first, follows by the second, and so on.

Programming languages give many control systems that allow for more complex execution paths.

A loop statement lets us run a statement or group of statements multiple times. You can see the general form of a loop statement given below in most of the programming languages.

![][image-2]

TypeScript gives different kinds of loops to control looping requirements. The following figure shows the classification of loops.

![][image-3]

### Definite Loop

A loop whose number of repetitions is fixed is known as a **definite loop**. The _for loop_ is an application of a definite loop.

S.No.
**Loop Name**
Loops & Description

1.
for
The for loop is an implementation of a definite loop.

### Indefinite Loop

An indefinite loop is used when the number of repetitions in a loop is unknown.

Indefinite loops can be implemented using.

S.No
**Loop Name**
Loops & Description

1.
while
The while loop executes the instructions each time the condition specified evaluates to true.

2.
do…while
The do…while loop is similar to the while loop except that the do…while loop doesn’t evaluate the condition for the first time the loop executes.

### Example: while versus do..while

1

2

3

4

5

6

7

8

`var` `n:number = 5`

``while``(n > 5) {``

````console.log(``"Entered while"``)``

`}`

`do` `{`

````console.log(``"Entered do…while"``)``

`}`

``while``(n>5)``

The example at first declares a while loop. The loop enters only if the expression passes to while seems to be true. In this example, the value of n is not greater than zero. Therefore, the expression returns false and the loop will not run.

On the other hand, the do…while loop runs the statement once because the initial repetition does not consider the Boolean expression. However, the while loops check the condition and take the control out of the loop for the consecutive repetition.

It will run following [JavaScript][3] code on composing.

1

2

3

4

5

6

7

8

9

`var` `n = 5;`

`while` `(n > 5) {`

````console.log(``"Entered while"``);``

`}`

`do` `{`

````console.log(``"Entered do…while"``);``

``} ``while`` `(n > 5);`

The above code will produce the following output.

## The break Statement

The **break** statement allows us to take control out of a setup. If we use a **break** in a loop, it will cause the program to exit the loop. Its syntax is as follows.

Syntax

Flow diagram

![][image-4]

### Example

Now, take a look at the following example code.

1

2

3

4

5

6

7

8

`var` `i:number = 1`

``while``(i<=10) {``

````if`` `(i % 5 == 0) {`

````console.log (``"The first multiple of 5  between 1 and 10 is : "``+i)``

````break``  

````}``

````i++``

`}`

On compiling, it will generate the following JavaScript code.

1

2

3

4

5

6

7

8

9

10

`var` `i = 1;`

`while` `(i <= 10) {`

````if`` `(i % 5 == 0) {`

````console.log(``"The first multiple of 5  between 1 and 10 is : "`` `\+ i);`

````break``;``

````}``

````i++;``

`}`
```
It shows the following output.



1

The first multiple of 5  between 1 and 10 is : 5



## The continue Statement




The **continue** statement jumps the subsequent statements in the current repetition and takes the control back to the beginning of the loop. It does not exit the loop, unlike the break statement. . It ends the current repetition and starts the following repetition.




Syntax





Flowchart




![](https://learncodeweb.com/wp-content/uploads/2021/02/04.png)




### Example




An example of the continue statement is given below.



1

2

3

4

5

6

7

8

9

10

var num:number = 0

var count:number = 0;

for(num=0;num<=20;num++) {

   if (num % 2==0) {

      continue

   }

   count++

}

console.log (" The count of odd values between 0 and 20 is: "+count)    



The above example shows the number of odd values between 0 and 20. The loop exits the current repetition if the number is even. The **continue** statement helps us to get this.




It runs following JavaScript code on compiling.



1

2

3

4

5

6

7

8

9

10

11

var num = 0;

var count = 0;

for (num = 0; num <= 20; num++) {

   if (num % 2 == 0) {

      continue;

   }

   count++;

}

console.log(" The count of odd values between 0 and 20 is: " + count);     



Output



1

The count of odd values between 0 and 20 is: 10



## The Infinite Loop




An infinite loop is a loop that runs infinitely. The **for** loop and the **while** loop are used to make an endless loop.




### Example: Infinite loop using for loop



1

2

3

for(;;) { 

   console.log(“This is an endless loop”) 

}



### Syntax: Infinite loop using while loop



1

2

3

while(true) { 

   //statements 

} 



### Example: Infinite loop using while loop



1

2

3

while(true) { 

   console.log(“This is an endless loop”) 

}



* * *
```


---- 

[1]:	https://learncodeweb.com/typescript/all-loops-with-example-in-typescript/
[2]:	https://learncodeweb.com/learn/typescript/
[3]:	https://learncodeweb.com/learn/javascript/

[image-1]:	https://learncodeweb.com/wp-content/uploads/2021/02/All-loops-with-example-in-TypeScript.png
[image-2]:	https://learncodeweb.com/wp-content/uploads/2021/02/0.png
[image-3]:	https://learncodeweb.com/wp-content/uploads/2021/02/01.png
[image-4]:	https://learncodeweb.com/wp-content/uploads/2021/02/02.png

#article #loop