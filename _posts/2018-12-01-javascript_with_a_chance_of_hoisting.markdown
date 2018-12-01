---
layout: post
title:      "JavaScript With A Chance Of Hoisting."
date:       2018-12-01 21:34:11 +0000
permalink:  javascript_with_a_chance_of_hoisting
---


In layman terms Hoisting Means rising up in Programming.


# Quick tips:
*  Follow two simple rules and you will be saved. You can thank me later.

* 	Declare all your functions at the top of their scope. Meaning[ if the functions are declared in the global scope,     simple put them at the top of the JavaScript file. & If they’re declared inside another function, put the declaration at the top of the function body]

* 	ONLY use const & let. NOT var


 For Instance: 

function myFunc () {
                 return 'Hello, world!';
         }
 
myFunc();
     // => "Hello, world!"
		 

 TIP:  myFun(); can be put at the top and it will still work just fine. Also keep in mind that: 

⇨	When this code runs. Remember the two- way JavaScript runs code. [Compilation & Execution.]

⇨	 PART 1 => JavaScript engine ignores all FUNCTION invocations in compilation phase. A.K.A Simply looks over myFunc().

⇨	PART 2=>  When is starts allover, JavaScript has already created myFunc() in memory.  And execute each line, but during execution Phase,  it will ignore the function declaration that was already carried out in the compilation phase.

⇨	And Run.



1.	function myFunc () {
2.	return 'Hello, world!';
3.	}

This is the term called **HOISTING**.

*  The term for this process is hoisting because it feels a bit like your declarations are being hoisted (“**lifted**”) to the top of the current scope. Your declarations are being evaluated before the rest of your code gets run, even if the location of the code didn’t change at all.
* The best way to avoid any confusion brought on by function hoisting is to simply declare your functions at the very top of your code.
 (This will save you from looking crazy at Starbucks as you talk to yourself while debugging)
[Talking to yourself](https://goo.gl/images/eDGJdU)

**Variable Hoisting.**

For instance, looking over the code below, 

function myFunc () {
         console.log(hello);
 
     var hello = 'World!';
}
  // => undefined
 
⇨	we get undefined because hoisting only applies to variable declarations; not variable assignments.


*The Break Down….
*
The Difference between Declarations and Assignment.

// Declaration:
     let hello;
           Note: compilation phase, JavaScript initialize the variable ‘hello’ but assign it NO value yet #=> why we get     undefined.

// Assignment:
        hello = 'World!';
 
// Declaration and assignment on the same line:

      let goodnight = 'Moon';

 How this Play out in real life code..

function myFunc () {
      console.log(hello);
 
      var hello = 'World!';
 
return hello;
}
 
myFunc();
      // LOG: undefined
        // => "World!"

*  	The declaration of hello (var hello) is evaluated during the compilation phase, and the identifier, hello, is stored in memory as undefined.
*  	The execution phase starts, and the JavaScript engine begins stepping through the code, executing each line in turn.
*  	At the first line, console.log(hello);, the value of hello is still undefined, and that's exactly what gets logged out to the console.
*  	At the second line, the value 'World!' is assigned to the variable hello. From this point on, all references to hello in this scope will evaluate to 'World!'.
*  	At the final line, we return the value of hello, which by now has been assigned and evaluates to 'World!’
* 

Conclusion,
 - If you most keep Javascript from hoisting your variables. 

-	Declare your variable at the top of a function.


Happy coding. 




