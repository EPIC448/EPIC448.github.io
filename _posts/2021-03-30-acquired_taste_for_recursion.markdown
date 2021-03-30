---
layout: post
title:      " Acquired Taste for recursion "
date:       2021-03-30 10:30:23 -0400
permalink:  acquired_taste_for_recursion
---

 
 Okay im just gonna say it because I know you all were thinking it. Most beer tastes bad, barely next to shit i may add. By this point I think beer pong games and cheap college lifestyle is the only thing keeping the industry alive because it's definitely not the flavor. Thus, an acquired taste is required to enjoy a nice brew.
 
*Sidebar:
One way to make beer taste better is to add any light colored soda. This is what everyone in the alcohol community calls a Shandy, and it makes beer taste better because it makes the beer sweeter without getting rid of the carbonation*

 *This would  possibly be a  3 part topic on recursion to make sure I share enough details to help you understand it, but not too much to overwhelm you.*

It is almost similar to Regex in that, when understood you can do a lot of amazing things with it, but on the flipside if  misused, you can wreck a code base. However, that is why you have articles such as this. 

> your are welcome!!!


 Just like drinking beer, Recursion requires an acquired taste or rather an acquired way of thinking because reading a recursion code is one thing, but writing it is another thought process on its own. When implemented wrongly,  it can make your code read like shit and cause stack overflow, but with some acquired thinking process and some problem solving, it is amazing.  

This article focuses on writing recursion and possible other intricate parts of it that are not often explained very well. 

### The name says it all 

 Recursion in code  simply means “re-occurring” code. Better defined as a function that calls itself over and over again.  By the giving definition, it is used in algorithms that repeatedly execute a task .

*  For example:
 
 A counterDown time in a Track meet race assuming that it starts from 10 - 0 would often go something like
10,9,8,7,6,5,4,3,2,1,0

Javascript representation using a function : 
```
function counterDown (number) {
  
     console.log(number) // keep track of the number decreasing. 
    
  if (number === 0 ) {    //Base case  of the function 

    return "counterDown complete"

  }else{
	
  counterDown(number -1 )  // Recursion line of code that executes. 
  
  }
}
counterDown(10)

 Result// 
10
9
8
7
6
5
4
3
2
1
0

```

-------------------------------------------------------------------------------------------------------------------------

Following the code above, you will notice two things: a  “Base Case” and “recursion line”. They both play an important role together 

Definition: 
A base case is a specific condition that causes the function to return a value instead of calling itself again. Base cases must exist in order to prevent the recursive function (recursion line) from calling itself infinitely. Which can lead to stackover flow .

!!! yes… Your computer will explode
![](https://media.giphy.com/media/nv99yd56AMNDa/giphy.gif)

### Another Trick in implementation

  A trick we can use to make our code more concise is adding another parameter in the argument at the start to keep track of the counter. 

Javascript representation using the arrow function expression : 

```
const counterDown = (number, counter = 0) => {
  // We are setting our argument to zero and we add our number values to counter as it changes       along the iteration of the code.  

   Removed---  console.log(number) // keep track of the number decreasing. 

  if (number === 0 ) {
    return "counterDown complete"
  }else{
  counterDown(number -1 )
   counter+= number
  }
  console.log (counter)
}
counterDown(10)


 // => same answer. 
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

```
--------------------------------------------------------------------


#### Other use cases for Recursion that you didn't know . 

> Note: I will only cover a few use cases with code samples of recursion, a quick Google search with your preferred recursion usage should yield ample results. 


**Calculation**:   Recursion is great here as it performs a calculation based on a Subproblem.  In code, we often work with problems that have an arbitrary level of depth.

 * Example: 

The popular subproblem that focuses on this is the  Factorial problem.  

The  Factorial of 6  = 6 x 5 x 4 x 3 x 2 x 1 x 0

Javascript representation using the arrow function expression : 

```
const factorial = (number) => {
    
  if (number === 1 ) { // base case
    return 1
  }else{
  return number * factorial(number -1 ) // recursion line
  
  }
}
console.log( factorial(6) )

//=> 720

Break down of recursive line. 

  return number * factorial(number -1 )
          6 x  factorial(6 -1 ) = 5 ---[6 x 5]
           5 x  factorial(5 -1 ) = 4---[5 x 4]
             4 x  factorial(4 -1 ) = 3---[4 x 3]
               3 x  factorial(3 -1 ) = 2---[3 x 2]
                 2 x  factorial(2 -1 ) = 1---[2 x 1]
                    1 x  factorial(1 -1 ) = 0 ---[1 x 0]


```


Most likely, you have implemented one of this methods below without knowing it. In instances involving sub-problems, we can use 2 approaches. 

 ### 2 approach to the same problem (Bottom Up VS Top down)

####  Bottom Up

If you have worked on code for a while, you have come across a function or pieces of code that uses “LOOPS” . This approach can be considered a “Bottom Up ” approach  which often looks something like this: 

```
 Javascript code :
 
  Function dummyFunc () {
 for(let i = 0, i < array.length, i++) {
    Do something…...
  } 
 Return result

}


// In Recursion, It will look something like this. 

Ruby implementation. 
 
Def dummyFunc(N, i =1, product =1)
 Return product  if i > N  //  base case
 Return dummyFunc(N, i + 1, product * 1) // recursion line.
End

Note: we are implementing the trick we mentioned early in which now, we have  3 parameters in our function.  

N : Number whose factorial we’re computing.

i =1: simple varble that start at  1 and increments by one in each successive call until  it reaches N.

product =1:  is a variable which we store the calculation as we keep multiplying each successive number, thus keeping track of it as we go.

```


#### Top-Down Approach : 

  This is a favorite of mine, as it allows us to mentally kick the problem down the road or better yet dissolve the problem from its highest point to the lower part that we understand. 
This can be helpful while in an interview situation because you don't necessarily need to know the solution to the whole thing, just solving for part of it can make a huge difference. 
  

 As I use  this approach, Three things I learned that I believe would help you. 
 
1. Imagine the function your writing is already implemented by someone else
2. Pick out the sub-problem of the giving problem
3. See what happens on the subproblem and go from there.

```
 Ruby Code Implementation. 

def sum(array)

# Base Case: only one element in the array
    return array[0] if array.length == 1

# recursive line code. 
   return array[0] + sum(array[1, array.length - 1 ]) 

end

print sum([1,2,3])  #> 6

```

 
 To keep this short, other situation that we can use the Recursive  Top-Down approach includes but not limited to:
 
String reversal  (hello -- olleh)

Counting X  (find the number of X in string “xbxcxd”)

Famous Staircase problem 

Remember, a google search on the implementation of this problem using the Top-down method will help. Better yet, you can put your problem solving chops to use here.  Drop me a line at samrey2018@gmail.com incase i missed something. I appreciate it in advance. 

