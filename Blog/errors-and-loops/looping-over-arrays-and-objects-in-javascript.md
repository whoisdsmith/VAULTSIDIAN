# Looping Over Arrays and Objects in JavaScript

You have **2** free member-only stories left this month.

![][image-1]

Photo by [Patrick McManaman][1] on [Unsplash][2]

A common problem many programmers encounter is looping over an enumerable data set. This data can come in the form of arrays, lists, maps, or other objects. Luckily, developers have at their disposal a variety of tools applicable to this exact problem. The JavaScript language, in particular, provides a diverse array of iteration devices. Below is a brief explanation of many useful JavaScript statements and methods applicable to looping over arrays and objects.

## While Loop

Let’s start with a simple problem. The task is to print out a series of messages stored in an array. A simple while loop using the array index can get the job done, as seen below.

```
messageArray = ["hello","how are you?",  
                "how's the weather",  
                "how's the family?",  
                "Where do you live?"];let index = 0;  
while(index < messageArray.length){  
  console.log(messageArray[index]);  
  index += 1;  
}OUTPUT:“hello”“how are you?”“how’s the weather”“how’s the family?”“Where do you live?”

The while loop works as follows:

  1. At the beginning of each iteration, the program evaluates the condition
  2. If the condition is true, i.e., the increment variable is less than the array length, the loop continues execution.
  3. If the condition is false, the loop execution is exited.
  4. At the end of the main code in the loop body, the index increments and the operation applies to the next array element.

It’s simple and works. However, it lacks elegance. It requires the declaration of a variable outside the loop itself, opening the possibility of scoping issues and value mutation. Additionally, a failure to increment the index will lead to an infinite loop.

## For Loop

For a more self-contained solution, there is the famous for loop.

messageArray = [“hello”,”how are you?”,  
                ”how’s the weather”,  
                ”how’s the family?”,  
                ”Where do you live?”];for(let i = 0;i < messageArray.length;i++){  
   console.log(messageArray[i]);  
}OUTPUT:“hello”“how are you?”“how’s the weather”“how’s the family?”“Where do you live?”

The for loop works as follows:

  1. The loop begins with three statements: a variable initialization, a condition, and a variable value change
  2. On the first iteration, the variable initializes to zero.
  3. If the condition statement evaluates to true, the loop execution is continued. i.e., the increment variable is less than the array length.
  4. If the condition statement evaluates to false, the loop execution is exited.
  5. The third statement increments the index variable.
  6. The main body code of the loop executes on each cycle.

This code works just as well and is more compact. All of the necessary information is contained in the first line of the loop with the logic self-contained. It does have its drawbacks, however. The problem we are giving the computer is as follows: “loop over the array and operate on each of its elements”

To accomplish this, we don’t need to explicitly initialize the variable, calculate the array length, or increment the variable. In truth, the counter variable itself is unnecessary. These things may be necessary for the mechanics of executing the loop. They are, however, unnecessary details if we are focusing on higher-level programming.

## for … of

To solve precisely this problem, Javascript developed the for..of loop. Let’s rewrite the problem above using it.

for(let message of messageArray){  
   console.log(message);  
}OUTPUT:“hello”“how are you?”“how’s the weather”“how’s the family?”“Where do you live?”

A for..ofloop is an excellent tool that is, in many cases, superior to the previous loops. It takes over much of the mundane implementation of the problem; while allowing the coder to focus on higher-level thinking. It does, however, leave the actual index value out of the loop. Luckily, in this case, we can simply fall back on while or for loops.

## for each

One other tool for iterating over loops is worth mentioning: forEach. forEach is a built-in method in JavaScript that allows us to iterate over an array with no additional information. I love this method because it is built specifically for this type of problem and is versatile as well. The basic syntax for the method is as follows:

arr.forEach(callback(currentValue,index,array),thisArg)

  1. callback: a callback function that operates on each element in the array.
  2. currentValue: the current element in the array the callback operates upon.
  3. array: the actual array that forEach is looping over.
  4. thisArg: the user is giving the option of specifying a ‘this’ argument.

Let’s see an example of how to apply forEachto this problem.

messageArray.forEach(function(message){  
   console.log(message);  
   });

or with an anonymous function…

messageArray.forEach(message => console.log(message));OUTPUT:“hello”“how are you?”“how’s the weather”“how’s the family?”“Where do you live?”

A great thing about forEachis that it allows access to the index if needed. This capability can be indispensable as, in many cases looping over each element along is not enough. forEach addresses this problem as the below code illustrates.

messageArray.forEach((message, index) =>   
   console.log(`${index}. ${message}`));OUTPUT:“0. hello”“1. how are you?”“2. how’s the weather”“3. how’s the family?”“4. Where do you live?”

forEach is among the highest level looping iterations tools at a JavaScript coder’s disposal. This code hides nearly all of the lower-level implementation of the loop while compacting the logic of loop iteration to one line. One note of caution, however. Unlike lower-level loops, forEach does not provide a way to break out of loops early with a break statement other than throwing an error.

# OBJECTS

JavaScript has many useful and versatile tools for looping through arrays. However, arrays are not the only iterable datasets a coder must handle. Additionally, array methods do not apply well to other kinds of objects with non-integer keys. For this reason, JavaScript provides methods for iterating over objects.

# for… in

Amongst the most common and straightforward tools for iterating over objects is for…in. It is the object equivalent of for…of. It simply iterates over an object by property names. Let’s look at an example below.

Let’s say we need to print out the prices and quantities for various items in a store based on their item names. To accomplish this, we can use an object with price and quantity properties.

storeItems = {   eggs: {price: 3.77, quantity: 30},   milk: {price: 2.22, quantity: 23},   butter: {price: 2.00, quantity: 22},   carrots: {price: 3.00, quantity: 11},   beef: {price: 6.18, quantity: 34},   chicken: {price: 5.44, quantity: 34}};

Using a for..in loop, we can iterate over this object by property name to access all the properties.

for(let item in storeItems){  
   console.log(`${storeItems[item].quantity} ${item}s each cost  
   ${storeItems[item].price}`);  
}OUTPUT:“30 eggs each cost 3.77”“23 milks each cost 2.22”“22 butters each cost 2”“11 carrots each cost 3”“34 beefs each cost 6.18”“34 chickens each cost 5.44”

The for…in loop works as follows:

  1. The loop begins with a variable declaration representing the property name of each element in the object.
  2. The loop then iterates over all enumerable properties of the object.
  3. The code in the body of the loop executes for each object property.
  4. After the final property is reached and processed, the loop exits.

## Object.keys(myObj)

Another useful object loop iteration tool worth exploring is Object.keys. It works similarly to for..in, essentially moving over the object’s property names. The main difference is that this function returns an array whose elements are strings corresponding to the enumerable properties found directly upon the object. The code iterates over the properties in the same order as if done manually. The example below illustrates object.keys applied to the previous object.

Object.keys(storeItems).forEach(item =>    
  console.log(`${storeItems[item].quantity} ${item}s each cost   
  ${storeItems[item].price}`  
));OUTPUT:“30 eggs each cost 3.77”“23 milks each cost 2.22”“22 butters each cost 2”“11 carrots each cost 3”“34 beefs each cost 6.18”“34 chickens each cost 5.44”

The Object.keys method works as follows:

  1. The method loops through the object, collecting all the enumerable property names in the object.
  2. These property names have coalesced into an array.
  3. The method now returns an array with all the object’s property names in string form.
  4. With this, the code can access all the object’s properties with a loop such as forEach.
  5. The forEach array method loops through the array and uses the property names to operate based on each object property.

The above code does the same job as for..in but is a little more verbose. However, there can be at least a couple of advantages of using Object.keys over for..in. First, it is much more likely to iterate over the object properties in their correct order as defined initially. Second, possessing the Object keys in array form has advantages. For example, the programmer can find the number of properties in the object by finding the length of the array returned.

## Object.entries(myObj)

Much like Object.keys, Object.entries returns an array. However, Object.entries returns an array of key, value pairs to allow more versatility in implementation. Like Object.keys, The code iterates over the properties in the same order as if done manually.  
 Let’s examine how the method is applied below:

Object.entries(storeItems).forEach(item =>  
   console.log(`${item[1].quantity} ${item[0]}s each cost  
   ${item[1].price}`);  
);OUTPUT:“30 eggs each cost 3.77”“23 milks each cost 2.22”“22 butters each cost 2”“11 carrots each cost 3”“34 beefs each cost 6.18”“34 chickens each cost 5.44”

The code above does the same job as Object.keys. The main difference is that this method gives direct access to both property names and the properties themselves.

# Key Takeaways

  * JavaScript provides a wide variety of tools to apply to many problems that require looping over an enumerable data set. This article is by no means an exhaustive list.
  * Although not ideal, General purpose loop statements such as while and for can be used to iterate over arrays using their indices.
  * JavaScript has many built-in tools developed specifically for the problem of looping over enumerable data sets, both arrays, and objects, including for…of, for…in, forEach, Object.keys, and object .entries.
  * As a developer, you must choose which tool to apply based on the problem to solve and its context.
```

----

[1]: https://unsplash.com/@patmcmanaman?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText
[2]: https://unsplash.com/s/photos/circle?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText

[image-1]: https://miro.medium.com/max/2100/1*6ViPWVgMAJH5dS2vhsLOOw.jpeg

# article #loop
