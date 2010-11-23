Each.asnc
========
This plugin provides a mechanism for running iteration loops asynchronously. How this works is that instead of directly calling the provided function, the function sets a very small timeout before calling it. This in turn lets the browser run several of the iterations at the same time, potenialy increasing the speed on large itratable objects.


How to use
----------


#### Object
    
    #JS
    Object.each.async(obj,func[,bind[,time]]); 
    

#### Array

    #JS
    Array.each.async(arr,func[,bind[,time]]); 
    

Both method work just like the normal each loops, but can also receive a 4th paramater - time - that tells the function how long to set the delay before execution (set to 50 milisecs as a default).