# Infinite loop - Wikipedia

This article is about the programming term. For the street named after this term, see [Infinite Loop (street)](/wiki/Infinite_Loop_\(street\)). For the book by Michael S. Malone, see [Infinite Loop (book)](/wiki/Infinite_Loop_\(book\)).

"Endless loop" redirects here. For EP by Eiko Shimamiya, see [Endless Loop](/wiki/Endless_Loop).

[Loop constructs](/wiki/Control_flow#Loops)

  * [Do while loop](/wiki/Do_while_loop)
  * [While loop](/wiki/While_loop)
  * [For loop](/wiki/For_loop)
  * [Foreach loop](/wiki/Foreach_loop)
  * Infinite loop
  * [Control flow](/wiki/Control_flow)

  * [v](/wiki/Template:Loop_constructs)
  * [t](/wiki/Template_talk:Loop_constructs)
  * [e](https://en.wikipedia.org/w/index.php?title=Template:Loop_constructs&action=edit)

In [computer programming](/wiki/Computer_programming), an **infinite loop** (or **endless loop**)[1][2] is a sequence of instructions that, as written, will continue endlessly, unless an external intervention occurs ("pull the plug"). It may be intentional. 

## Contents

  * 1 Overview
  * 2 Details
  * 3 Intended vs unintended looping
    * 3.1 Intentional looping
      * 3.1.1 Multi-threading
    * 3.2 Unintentional looping
  * 4 Interruption
  * 5 Language support
  * 6 Examples of intentional infinite loops
  * 7 Examples of unintentional infinite loops
    * 7.1 Mathematical errors
    * 7.2 Rounding errors
  * 8 Multi-party loops
  * 9 Pseudo-infinite loops
    * 9.1 Very large numbers
    * 9.2 Impossible termination condition
    * 9.3 Infinite recursion
    * 9.4 Break statement
    * 9.5 Alderson loop
  * 10 See also
  * 11 References
  * 12 External links

## Overview

This differs from: 

  * "a type of computer program that runs the same instructions continuously until it is either stopped or interrupted."[3]

Consider the following [pseudocode](/wiki/Pseudocode): 
    
    
    how_many = 0
    while is_there_more_data() do
        how_many = how_many + 1
    end
    display "the number of items counted = " how_many
    
    
    
    
    
    _The same instructions_ were run _continuously until it was stopped or interrupted_ . . . by the _FALSE_ returned at some point by the function _is_there_more_data_.
    
    
    By contrast, the following loop will not end by itself:
    
    
    
    
    
    
    birds = 1
    fish = 2
    while birds + fish > 1 do
        birds = 3 - birds
        fish = 3 - fish
    end
    
    
    
    
    
    _birds_ will alternate being 1 or 2, while _fish_ will alternate being 2 or 1. The loop will not stop unless an external intervention occurs ("pull the plug").
    
    
    
    
    
    ## Details
    
    
    
    
    An _infinite loop_ is a sequence of instructions in a [computer program](/wiki/Computer_program) which loops endlessly, either due to the [loop](/wiki/Control_flow#Loops) having no terminating condition,[4] having one that can never be met, or one that causes the loop to start over. In older [operating systems](/wiki/Operating_system) with [cooperative multitasking](/wiki/Cooperative_multitasking),[5] infinite loops normally caused the entire system to become unresponsive. With the now-prevalent preemptive multitasking model, infinite loops usually cause the program to consume all available processor time, but can usually be terminated by the user. [Busy wait](/wiki/Busy_waiting) loops are also sometimes called "infinite loops". Infinite loops are one possible cause for a computer "[freezing](/wiki/Hang_\(computing\))"; others include [thrashing](/wiki/Thrashing_\(computer_science\)), [deadlock](/wiki/Deadlock), and [access violations](/wiki/Segmentation_fault).
    
    
    
    
    
    ## Intended vs unintended looping
    
    
    
    
    Looping is repeating a set of instructions until a specific condition is met. An infinite loop occurs when the condition will never be met, due to some inherent characteristic of the loop.
    
    
    
    
    
    ### Intentional looping
    
    
    
    
    There are a few situations when this is desired behavior. For example, the games on cartridge-based game consoles typically have no exit condition in their main loop, as there is no operating system for the program to exit to; the loop runs until the console is powered off.
    
    
    Modern interactive computers require that the computer constantly be monitoring for user input or device activity, so at some fundamental level there is an infinite processing [idle loop](/wiki/Idle_loop) that must continue until the device is turned off or reset. In the [Apollo Guidance Computer](/wiki/Apollo_Guidance_Computer), for example, this outer loop was contained in the Exec program,[6] and if the computer had absolutely no other work to do it would loop run a dummy job that would simply turn off the "computer activity" indicator light.
    
    
    Modern computers also typically do not halt the processor or motherboard circuit-driving clocks when they crash. Instead they fall back to an error condition displaying messages to the operator, and enter an infinite loop waiting for the user to either respond to a prompt to continue, or to reset the device.
    
    
    
    
    
    #### Multi-threading
    
    
    
    
    In multi-threaded programs some threads can be executing inside infinite loops without causing the entire program to be stuck in an infinite loop. If the main thread exits all threads of the process are forcefully stopped thus all execution ends and the process/program terminates. The threads inside the infinite loops can perform "housekeeping" tasks or they can be in a blocked state waiting for input (from socket/queue) and resume execution every time input is received.
    
    
    
    
    
    ### Unintentional looping
    
    
    
    
    Most often, the term is used for those situations when this is not the intended result; that is, when this is a [bug](/wiki/Software_bug).[7] Such errors are most common among novice programmers, but can be made by experienced programmers as well, because their causes can be quite subtle.
    
    
    One common cause, for example, is that the programmer intends to iterate over sequence of nodes in a [data structure](/wiki/Data_structure) such as a [linked list](/wiki/Linked_list) or [tree](/wiki/Tree_\(data_structure\)), executing the loop code once for each node. Improperly formed links can create a _reference loop_ in the data structure, where one node links to another that occurs earlier in the sequence. This makes part of the data structure into a [ring](/wiki/Ring_\(data_structure\)), causing naive code to loop forever.
    
    
    While most infinite loops can be found by close inspection of the code, there is no _general_ method to determine whether a given program will ever halt or will run forever; this is the [undecidability](/wiki/Undecidable_problem) of the [halting problem](/wiki/Halting_problem).[8]
    
    
    
    
    
    ## Interruption
    
    
    
    
    As long as the system is responsive, infinite loops can often be interrupted by sending a signal to the process (such as [SIGINT](/wiki/SIGINT_\(POSIX\)) in Unix), or an [interrupt](/wiki/Interrupt) to the processor, causing the current process to be aborted. This can be done in a [task manager](/wiki/Task_manager), in a terminal with the [Control-C](/wiki/Control-C) command,[9] or by using the [kill](/wiki/Kill_\(command\)) command or [system call](/wiki/System_call). However, this does not always work, as the process may not be responding to signals or the processor may be in an uninterruptible state, such as in the [Cyrix coma bug](/wiki/Cyrix_coma_bug) (caused by overlapping uninterruptible instructions in an [instruction pipeline](/wiki/Instruction_pipeline)). In some cases other signals such as [SIGKILL](/wiki/SIGKILL) can work, as they do not require the process to be responsive, while in other cases the loop cannot be terminated short of system shutdown.
    
    
    
    
    
    ## Language support
    
    
    
    
    See also: [Control flow](/wiki/Control_flow)
    
    
    
    
    Infinite loops can be implemented using various [control flow](/wiki/Control_flow) constructs. Most commonly, in unstructured programming this is jump back up ([goto](/wiki/Goto)), while in structured programming this is an indefinite loop (while loop) set to never end, either by omitting the condition or explicitly setting it to true, as while (true) ....
    
    
    Some languages have special constructs for infinite loops, typically by omitting the condition from an indefinite loop. Examples include Ada (loop ... end loop),[10] Fortran (DO ... END DO), Go (for { ... }), Ruby (loop do ... end), and Rust (loop { ... }).
    
    
    
    
    
    ## Examples of intentional infinite loops
    
    
    
    
    A simple example (in [C](/wiki/C_\(programming_language\))):
    
    
    
    
    
    
    #include <stdio.h>
    
    int main()
    {
      for (;;) // or equivalently, while (1)
        ;  
      return 0;
    }
    
    
    
    
    
    The form for (;;) for an infinite loop is traditional, appearing in the standard reference _[The C Programming Language](/wiki/The_C_Programming_Language)_, and is often punningly pronounced "forever".[11]
    
    
    This is a loop that will print "Infinite Loop" without halting.
    
    
    A similar example in 1980s-era [BASIC](/wiki/BASIC_programming_language):
    
    
    
    
    
    
    10 PRINT "INFINITE LOOP"
    20 GOTO 10
    
    
    
    
    
    A similar example in [DOS](/wiki/DOS) batch files:
    
    
    
    
    
    
    :A
    echo Infinite Loop
    goto :A
    
    
    
    
    
    Here the loop is quite obvious, as the last line unconditionally sends execution back to the first.
    
    
    An example in [Java](/wiki/Java_\(programming_language\))
    
    
    
    
    
    
    while (true) {
        System.out.println("Infinite Loop");
    }
    
    
    
    
    
    An example in [Bourne Again Shell](/wiki/Bourne_Again_Shell)
    
    
    
    
    
    
    for ((;;)); do
    	echo "Infinite Loop"
    done
    
    
    
    
    
    An example in [Rust](/wiki/Rust_\(programming_language\))
    
    
    
    
    
    
    loop {
        println!("Infinite loop");
    }
    
    
    
    
    
    ## Examples of unintentional infinite loops
    
    
    
    
    ### Mathematical errors
    
    
    
    
    Here is one example of an infinite loop in [Visual Basic](/wiki/Visual_Basic):
    
    
    
    
    
    
    dim x as integer
    do while x < 5
      x = 1
      x = x + 1
    loop
    
    
    
    
    
    This creates a situation where x will never be greater than 5, since at the start of the loop code x is given the value of 1, thus, the loop will always end in 2 and the loop will never break. This could be fixed by moving the x = 1 instruction outside the loop. Essentially what this infinite loop does is to instruct a computer to keep on adding 1 to 1 until 5 is reached. Since 1+1 always equals 2, this will never happen.
    
    
    In some languages, programmer confusion about the mathematical symbols may lead to an unintentional infinite loop. For example, here is a snippet in [C](/wiki/C_\(programming_language\)):
    
    
    
    
    
    
    #include <stdio.h>
    
    int main(void)
    {
       int a = 0;
       while (a < 10) {
          printf("%d\n", a);
          if (a = 5)
             printf("a equals 5!\n");
          a++;
       }
       return 0;
    }
    
    
    
    
    
    The expected output is the numbers 0 through 9, with an interjected "a equals 5!" between 5 and 6. However, in the line "if (a = 5)" above, the programmer has confused the = (assignment) operator with the == (equality test) operator. Instead, this will assign the value of 5 to a at this point in the program. Thus, a will never be able to advance to 10, and this loop cannot terminate.
    
    
    
    
    
    ### Rounding errors
    
    
    
    
    
    
    
    
    
    
    _C output on an [AMD Turion](/wiki/AMD_Turion) processor:_
    
    
    
    
    
    
    x = 0.10000000149011611938
    
    
    
    
    
    
    x = 0.20000000298023223877
    
    
    
    
    
    
    x = 0.30000001192092895508
    
    
    
    
    
    
    x = 0.40000000596046447754
    
    
    
    
    
    
    x = 0.50000000000000000000
    
    
    
    
    
    
    x = 0.60000002384185791016
    
    
    
    
    
    
    x = 0.70000004768371582031
    
    
    
    
    
    
    x = 0.80000007152557373047
    
    
    
    
    
    
    x = 0.90000009536743164062
    
    
    
    
    
    
    x = 1.00000011920928955078
    
    
    
    
    
    
    x = 1.10000014305114746094
    
    
    
    
    
    
    x = 1.20000016689300537109
    
    
    
    
    
    
    ...
    
    
    
    
    Unexpected behavior in evaluating the terminating condition can also cause this problem. Here is an example in [C](/wiki/C_\(programming_language\)):
    
    
    
    
    
    
    float x = 0.1;
    while (x != 1.1) {
      printf("x = %22.20f\n", x);
      x += 0.1;
    }
    
    
    
    
    
    On some systems, this loop will execute ten times as expected, but on other systems it will never terminate. The problem is that the loop terminating condition (x != 1.1) tests for exact equality of two [floating point](/wiki/Floating_point) values, and the way floating point values are represented in many computers will make this test fail, because they cannot represent the value 0.1 exactly, thus introducing rounding errors on each increment (cf. box).
    
    
    The same can happen in [Python](/wiki/Python_\(programming_language\)):
    
    
    
    
    
    
    x = 0.1
    while x != 1:
        print(x)
        x += 0.1
    
    
    
    
    
    Because of the likelihood of tests for equality or not-equality failing unexpectedly, it is safer to use greater-than or less-than tests when dealing with floating-point values. For example, instead of testing whether x equals 1.1, one might test whether (x <= 1.0), or (x < 1.1), either of which would be certain to exit after a finite number of iterations. Another way to fix this particular example would be to use an [integer](/wiki/Integer_\(computer_science\)) as a [loop index](/wiki/Control_flow), counting the number of iterations that have been performed.
    
    
    A similar problem occurs frequently in [numerical analysis](/wiki/Numerical_analysis): in order to compute a certain result, an iteration is intended to be carried out until the error is smaller than a chosen tolerance. However, because of rounding errors during the iteration, the specified tolerance can never be reached, resulting in an infinite loop.
    
    
    
    
    
    ## Multi-party loops
    
    
    
    
    An infinite loop may be caused by several entities interacting. Consider a server that always replies with an error message if it does not understand the request. Even if there is no possibility for an infinite loop within the server itself, a system comprising two of them (_A_ and _B_) may loop endlessly: if _A_ receives a message of unknown type from _B_, then _A_ replies with an error message to _B_; if _B_ does not understand the error message, it replies to _A_ with its own error message; if _A_ does not understand the error message from _B_, it sends yet another error message, and so on.
    
    
    One common example of such situation is an [email loop](/wiki/Email_loop). An example of an email loop is if someone receives mail from a no reply inbox, but their auto-response is on. They will reply to the no reply inbox, triggering the "this is a no reply inbox" response. This will be sent to the user, who then sends an auto reply to the no-reply inbox, and so on and so forth.
    
    
    
    
    
    ## Pseudo-infinite loops
    
    
    
    
    A pseudo-infinite loop is a loop that appears infinite but is really just a very long loop.
    
    
    
    
    
    ### Very large numbers
    
    
    
    
    An example in [bash](/wiki/Bash_\(Unix_shell\)):
    
    
    
    
    
    
    for x in $(seq 1000000000); do
    #loop code
    done
    
    
    
    
    
    ### Impossible termination condition
    
    
    
    
    An example [for loop](/wiki/For_loop) in [C](/wiki/C_\(programming_language\)):
    
    
    
    
    
    
    unsigned int i;
    for (i = 1; i != 0; i++) {
      /* loop code */
    }
    
    
    
    
    
    It appears that this will go on indefinitely, but in fact the value of i will eventually reach the maximum value storable in an unsigned int and adding 1 to that number will wrap-around to 0, breaking the loop. The actual limit of i depends on the details of the system and [compiler](/wiki/Compiler) used. With [arbitrary-precision arithmetic](/wiki/Arbitrary-precision_arithmetic), this loop would continue until the computer's [memory](/wiki/Memory_\(computers\)) could no longer hold i. If i was a signed integer, rather than an unsigned integer, overflow would be undefined. In this case, the compiler could optimize the code into an infinite loop.
    
    
    
    
    
    ### Infinite recursion
    
    
    
    
    Infinite recursion is a special case of an infinite loop that is caused by [recursion](/wiki/Recursion). 
    
    
    The following example in [VBA](/wiki/Visual_Basic_for_Applications) returns a [stack overflow](/wiki/Stack_overflow) error:
    
    
    
    
    
    
    Sub Test1()
        Call Test1
    End Sub
    
    
    
    
    
    ### Break statement
    
    
    
    
    A "while (true)" loop looks infinite at first glance, but there may be a way to escape the loop through a [break statement](/wiki/Break_statement) or [return statement](/wiki/Return_statement).
    Example in [PHP](/wiki/PHP):
    
    
    
    
    
    
    while (true) {
        if ($foo->bar()) {
            return;
        }
    }
    
    
    
    
    
    ### Alderson loop
    
    
    
    
    _Alderson loop_ is a rare slang or [jargon](/wiki/The_Jargon_File) term for an infinite loop where there is an exit condition available, but inaccessible in the current implementation of the code, typically due to a programmer's error. These are most common and visible while [debugging](/wiki/Debugging) [user interface](/wiki/User_interface) code.
    
    
    A C-like pseudocode example of an Alderson loop, where the program is supposed to sum numbers given by the user until zero is given, but where the programmer has used the wrong operator:
    
    
    
    
    
    
    int sum = 0;
    int i;
    while (true) {
       printf("Input a number to add to the sum or 0 to quit");
       i = getUserInput();
       if (i * 0) { // if i times 0 is true, add i to the sum. Note: ZERO means FALSE, Non-Zero means TRUE. "i * 0" is ZERO (FALSE)!
          sum += i; // sum never changes because (i * 0) is 0 for any i; it would change if we had != in the condition instead of *
       }
       if (sum > 100) {
          break;    // terminate the loop; exit condition exists but is never reached because sum is never added to
       }
    }
    
    
    
    
    
    The term allegedly received its name from a programmer (last name Alderson) who in 1996[12] had coded a [modal](/wiki/Modal_window) [dialog box](/wiki/Dialog_box) in [Microsoft Access](/wiki/Microsoft_Access) without either an OK or Cancel button, thereby disabling the entire program whenever the box came up.[13]
    
    
    
    
    
    ## See also
    
    
    
    
    
      * [Cycle detection](/wiki/Cycle_detection)
    
    
      * [Deadlock](/wiki/Deadlock)
    
    
      * [Divergence (computer science)](/wiki/Divergence_\(computer_science\))
    
    
      * [Fork bomb](/wiki/Fork_bomb) (an infinite loop is one of two key components)
    
    
      * [Goto](/wiki/Goto)
    
    
      * [Infinite regress](/wiki/Infinite_regress)
    
    
      * [Recursion (computer science)](/wiki/Recursion_\(computer_science\))
    
    
    
    ## References
    
    
    
    
    
    
      1. **** ["Endless loop dictionary definition"](https://www.yourdictionary.com/endless-loop). [Archived](https://web.archive.org/web/20200801213748/https://www.yourdictionary.com/endless-loop) from the original on 2020-08-01. Retrieved 2020-01-22.none
    
    
    
      2. **** ["What is infinite loop (endless loop)"](https://whatis.techtarget.com/definition/infinite-loop-endless-loop). [Archived](https://web.archive.org/web/20190715101446/https://whatis.techtarget.com/definition/infinite-loop-endless-loop) from the original on 2019-07-15. Retrieved 2020-01-22.none
    
    
    
      3. **** Denise Caruso (August 16, 1999). ["Overload of Hangers-On Creates Bumpy Ride for Internet Stocks"](https://archive.nytimes.com/www.nytimes.com/library/tech/99/08/biztech/articles/16digi.html). _[The New York Times](/wiki/The_New_York_Times)_. [Archived](https://web.archive.org/web/20191227145519/https://archive.nytimes.com/www.nytimes.com/library/tech/99/08/biztech/articles/16digi.html) from the original on December 27, 2019. Retrieved December 27, 2019.none
    
    
    
      4. **** ["Codes and Modes: The Character of Documentary Culture"](http://www.flowjournal.org/tag/loop-media/?print=print-search). _Flow Journal_. November 2014. [Archived](https://web.archive.org/web/20200801213624/http://www.flowjournal.org/tag/loop-media/?print=print-search) from the original on 2020-08-01. Retrieved 2020-01-23. an infinite loop is one that lacks .. an exit conditionnone
    
    
    
      5. **** also known as non-preemptive-multitasking: ["Non-preemptive Multitasking"](https://www.pcmag.com/encyclopedia/term/48051/non-preemptive-multitasking). _[PC Magazine](/wiki/PC_Magazine)_. [Archived](https://web.archive.org/web/20190726232111/https://www.pcmag.com/encyclopedia/term/48051/non-preemptive-multitasking) from the original on July 26, 2019. Retrieved August 15, 2015.none
    
    
    
      6. **** David Hoag (September 1976). ["The History of Apollo On-board Guidance, Navigation, and Control"](http://klabs.org/history/history_docs/mit_docs/1711.pdf) (PDF). Charles Stark Draper Laboratory. [Archived](https://web.archive.org/web/20161105060425/http://klabs.org/history/history_docs/mit_docs/1711.pdf) (PDF) from the original on 2016-11-05. Retrieved 2020-01-23.none
    
    
    
      7. **** ["New York Times Crossword Answers"](https://nyxcrossword.com/2013/10/1013-13-new-york-times-crossword.html). October 13, 2013. [Archived](https://web.archive.org/web/20200802040416/https://nyxcrossword.com/2013/10/1013-13-new-york-times-crossword.html) from the original on August 2, 2020. Retrieved January 22, 2020. computing .. a defect .. which .. to loopnone
    
    
    
      8. **** ["Halting Problem in Theory of Computation"](https://www.geeksforgeeks.org/halting-problem-in-theory-of-computation). 3 October 2018. [Archived](https://web.archive.org/web/20200809100104/https://www.geeksforgeeks.org/halting-problem-in-theory-of-computation/) from the original on 9 August 2020. Retrieved 22 January 2020.none
    
    
    
      9. **** ["A Buffer Overflow Exploit Against the DameWare Remote Control software"](https://pen-testing.sans.org/resources/papers/gcih/buffer-overflow-exploit-dameware-remote-control-software-104168). December 19, 2003. [Archived](https://web.archive.org/web/20200724200739/https://pen-testing.sans.org/resources/papers/gcih/buffer-overflow-exploit-dameware-remote-control-software-104168) from the original on July 24, 2020. Retrieved January 22, 2020. As soon as the command shell is closed with a control-c combination ...none
    
    
    
      10. **** [Ada Programming: Control: Endless Loop](https://en.wikibooks.org/wiki/Ada_Programming/Control#Endless_Loop)
    
    
    
      11. **** ["Endless loop in C/C++"](https://stackoverflow.com/questions/20186809/endless-loop-in-c-c). [Archived](https://web.archive.org/web/20160803202212/http://stackoverflow.com/questions/20186809/endless-loop-in-c-c) from the original on 2016-08-03.none
    
    
    
      12. **** Lee Dohm (May 24, 2013). ["Alderson loop"](https://www.lee-dohm.com/2013/05/24/alderson-loop). [Archived](https://web.archive.org/web/20200619200434/https://www.lee-dohm.com/2013/05/24/alderson-loop/) from the original on June 19, 2020. Retrieved January 22, 2020.none
    
    
    
      13. **** ["Alderson Loop"](http://www.catb.org/~esr/jargon/html/A/Alderson-loop.html). _[The Jargon File](/wiki/The_Jargon_File), Version 4.4.7_. [Archived](https://web.archive.org/web/20060515053043/http://www.catb.org/~esr/jargon/html/A/Alderson-loop.html) from the original on 2006-05-15. Retrieved 2006-05-21.none
    
    
    
    
    
    
    
    ## External links
    
    
    
    
      * [Make an infinite loop](http://www.programming-idioms.org/idiom/50/make-an-infinite-loop) in several languages, on [programming-idioms.org](http://www.programming-idioms.org/).
    
    
    
    
    
    
    
    
    
  *[[v]: View this template
  *[[t]: Discuss this template
  *[[e]: Edit this template


___

#article 