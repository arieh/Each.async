Each.asnc
========
This plugin provides a mechanism for running iteration loops asynchronously. How this works is that instead of directly calling the provided function, the function sets a very small timeout before calling it. 
I've run some tests on this class, and came to some interesting conclusions:

1. Comparing normal Array.each to Array.each.async, the later was v slightly slower - 10 milisec on a 500 element iteration on avarage. This means that for real world applications, this method can be used safely, and it should affect your loop's performance.
2. Comparing the execution of following code, async was about *15 times faster*. This means that if you want the rest of your code to go on running - this is a very good way of doing this.

How to use
----------


#### Object
    
    #JS
    Object.each.async(obj,func[,bind[,time]]); 
    

#### Array

    #JS
    Array.each.async(arr,func[,bind[,time]]); 
    

Both method work just like the normal each loops, but can also receive a 4th paramater - time - that tells the function how long to set the delay before execution (set to 0 milisecs as a default).

Benchmarking
--------------------

To see the results for yourself, run the demo with your console open. The results names mean:

1. each - when the normal Array.each iteration's last functions finshed running.
2. each-done - when the Array.each iteration was complete and it's following code was first executed.
3. async - when the Array.each.async iteration's last functions finished running.
4. async-done - when the Array.each.async iteration was cmplete and it's following code was first executed.