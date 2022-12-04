# Infinite Loops in Javascript

While working with loops in JavaScript, there is always the danger of your loop not terminating and running forever. Such a loop is called an infinite loop. In this article, we are going to see how to detect and escape infinite loops.  
  


## Table of Contents

  * What are infinite loops
  * How to avoid running into infinite loops?
  * Other Related Concepts
  


## What are infinite loops?

An infinite loop is a piece of code that keeps running forever as the terminating condition is never reached. An infinite loop can crash your program or browser and freeze your computer. To avoid such incidents it is important to be aware of infinite loops so that we can avoid them.  
  
Let us see some examples of how we can run into infinite loops.  
  
One of the most common infinite loops is when the condition of the while statement is set to true. Below is an example of code that will run forever.  
  

    
    
    // Initiate an infinite loop
    while (true) {
    
        // execute code forever
    
    }
    
    
      
    
    
    Another classic example will be of the for loop where the terminating condition is set to infinity.  
      
    
    
    
    
    // infinite loop with the terminating condition set to infinity
    for (var i = 0; i < Infinity; i++) {
    
    
    }
    
    
      
    
    
    Though of little practical significance, you may also end up in an infinite loop by omitting all parts of the head of a for() block.  
      
    
    
    
    
    
    for (;;) {}
    
    
    
    
      
    
    
    
     
    
     
    
     
    
     
    
    ## Join our Network of Top Engineers and Work with Top Startups & Companies!
    
     
    
    
      
    
    
    
    ## How to avoid running into infinite loops?
    
    
    
    
    ### In for() loop:
    
    
    
    
      * To avoid ending up in an infinite loop while using a for statement, ensure that the statements in the _for()_ block never change the value of the _loop counter variable._ If they do, then your loop may either terminate prematurely or it may end up in an infinite loop.
    
    
    
    
    ### In while and do-while loops:
    
    
    
    
      *  Ensure you have at least one statement within the loop that changes the value of the comparison variable. (That is, the variable you use in the loop’s comparison statement.) As otherwise, the condition might always return true and the loop will never end.
      
    
    
     
      * Never leave the terminating condition to be dependent on the user.  As the user might cancel the prompt box etc. which might prevent the loop from terminating.
    
    
    
    
    In general, if by accident, you do end up with an infinite loop, and you’re not sure of the cause,  insert one or more debugger and/or console.log() statements within the loop statement block to display the current value of the counter variable. This might help you understand what happens to the variable when it passes through the loop each time.  
      
    
    
    
    
    
    
    


___

#article #infiniteloop