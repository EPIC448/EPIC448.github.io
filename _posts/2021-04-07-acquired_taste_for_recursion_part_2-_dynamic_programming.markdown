---
layout: post
title:      " Acquired Taste for Recursion Part 2- Dynamic Programming"
date:       2021-04-07 22:20:13 +0000
permalink:  acquired_taste_for_recursion_part_2-_dynamic_programming
---


  The last post I shared about recursion may have you jumping out of your seats, but however, I will say not so fast. 
Did you know that recursion can slow your code down? No that is not a typo. 

The fact of the matter is, recursion opens up a  new world to us and while it can solve a ton of problems, it can certainly create new ones as well.  Lucky us, some of these issues can be avoided. And, don't worry, some of this approach will be simple to implement

 I hope....  ![](https://media.giphy.com/media/fGL80gGa1scfCXfzoo/giphy.gif)
 

Look at this Sample of code here. 


 Problem:  Find the max number in the given array 
 
  ```
arr = [1,2,3,10,4,5]

// Ruby implementation 

def max (array)
    return array [0] if array.length == 1

our recursive line  with a condition 

    if array[0] > max(array [1, array.length - 1])          
       return array[0]
    else
		
   // returning our recursive line  

        return max(array[1, array.length - 1])
    end
    
end

puts max(arr)   ##  =>  10
 
 ------------------- Code break down --------

arr = [1,2,3,10,4,5] 

def max (array)
 
// BaseCase.  
   return array [0]  if array.length == 1 

     if array[0] > max(array [1, array.length - 1])  // Note that this line is repeated below

 ## ----- Start of break Down

 // Due to recursion, This  creates Sub-Problem for us to solve each time that line is called. 

     #### call stack view 
        
          We know max array[1] will always give us  2,
           Now we worry about [3,10,4,5] 
          When the call is made for the remaining elements in the array. You have something like. 

          -----Stack call.

                max(array [1,                array.length - 1])
                   max(array [2,                                5 - 1]) = 4
                    max(array [2,                                4 - 1]) =3
                      max(array [2,                                3 - 1]) =2
                        max(array [2,                                2 - 1]) = 1
                          max(array [2,                                1 - 1]) =0

                       Then,  the computer will start to work it way back up the stack by computing the results to these sub equations. 

## ------end of Break Down


      return array[0] 
 else 
    return 
        max(array[1, array.length - 1]) // Note that this line is repeated above 

## ------ Start of break Down------------------------------

                    ### the Stack call above repeats here again
                         max(array [1,                array.length - 1])
                            max(array [2,                                5 - 1]) = 4
                              max(array [2,                                4 - 1]) =3
                                 max(array [2,                                3 - 1]) =2
                                   max(array [2,                                2 - 1]) = 1
                                      max(array [2,                                1 - 1]) =0

 as you can see, the code is not efficient at all

##------------- -End of  break Down---------------


  end 
end 

puts max(arr)

BigO => O(N ^2)

```


 So how do we Fix this? 
 
If I have not lost you yet The truth is that we need some of these calls, but not all of it. 


#### ---------- Code Refactored-----------------

 ```
 arr = [1,2,3,10,4,5]

def max (array)
    return array [0] if array.length == 1
    
//Hint, we only want to focus on the  Max Number.  
 We can have a variable here of which we compare all of our calls too, thus calling the recursion  line only once.  

max_of_remainder  = max(array [1, array.length -1])  


    if array[0] > max_of_remainder 
		
        return array[0]
				
    else
		
        return max_of_remainder 
				
    end
    
end

puts max(arr)     =>  10

BigO =>  O(N)

```

 We went from calling the recursive line twice in our algorithm to calling it onces and just using that all over again. 


 
 
### Overlapping  Subproblems

 Another area of which recursion can slow down  code is when we have overlapping subproblems.  If you have participated in any code interview, you may have came across Fibannic sequence problems.

 In Javascript, our code for Fibannic often look something thing like this: 

```
const fib =(n) => {
  
  if (n == 0 || n == 1) return n
  
  return fib (n -2) + fib (n -1) 
  }
  
  
  console.log(fib(10))  //>  55
	
 ```

--------------Code Break- Down------

 ```
 const fib =(n) => {
  
      if (n == 0 || n == 1) return n
  
           //note: that we are calling our function twice at the line below. Not efficient at all. 
					
  return fib (n -2) + fib (n -1) 

As fib(n-2) is called, then  fib(n-1 ) , the  picture below depicts what is going on. 
As you can see, there are similar calls executed for  fib(n-2) and  fib(n-1 ).

Look at the Picture below. 
  }
	
	console.log(fib(10) )   //>  55


	```
	
	
	
	

![](https://i.stack.imgur.com/O2Ecw.jpg)

As you can see, it's a no brainer that some of those sub-problem are identical and yield the same result when computed, thus calling them just takes up extra space in memories which slows down our algorithm. Giving use  O(2^N) which is not efficient at all. 
  


#### --- So what do we do here.--------

Remember we are solving for  fib(n-2) and fib(n-1) lines of code. We need a way to check if a sub-problem we are about to solve  already has a solution and if it does, we need not solve it again , but instead just find and use the stored answer.  There are several approaches  to the problem but the one I will focus on is memoization.

 
 ##### Definition: 
 
  Memoization has many use cases, but a common use case is with Recursion.
 Memoization works by remembering previously computed  functions.  It stores the  result inside  a Hashtable or Dictionary which are great for fast lookups for later use in our code. 
 For those of you who don't know what a hashmap is, it is a type of collection of data that has two parts: a key and a value, the idea is  you store a certain value in a location in memory with a certain key. By giving the hashmap the correct key, you then get the corresponding value at the said key.
 
  Our code in memory would look something like this. 
	{4: 3} will be the  computed value for  fib( n - 1) = 3. That is if "n" was 4 in the case.

  Normally, our function calls goes:

 fib(4 -1) = 3
 fib(3-1) =1
 fib(2-1) =1
 fib(1-1) = 0
  .... And so on.

 And the same repeats for  fib(n -2).

Ironically enough, the quantity of redundant code appears in a fibonacci sequence. This means that if we can assume the following:

if we call fibonacci(7), we will be calling fibonacci(2) 8 times.
if we call fibonacci(8), we will be calling fibonacci(2) 13 times
if we call fibonacci(9), we will be calling fibonacci(2) 21 times


With the computed results stored in a HashMap, our function checks the HashMap to see if fib(n)  for specific numbers (n) has been computed. Those numbers are stored as Keys with the computed result stored as values to those keys and If it is not, then the unfound key in the HashMap would be computed and its result will be stored in the HashMap for the next iteration. 

 You may be asking how do we access the hashmap, it can be passed in as a Second Parameter to the function giving us access later in the code.  
 
#### Fibonacci Code Skeleton

```

function fib(n, hashMap = {}){

  if n <=2 return 1// base case
 else
 return  // recursive code i.e  fib(n-1, hashMap) + fib(n-2,hashMap)
 
}

```


 
Using sample of  code from earlier.

```
const fib =(n) => {
  
  if (n == 0 || n == 1) return n //base case
  
  // Redondant recursive line that needs to be refactored due to overs  OverLapping subProblems.
	 return fib (n -2) + fib (n -1) 
  }
 
)

  console.log(fib(10))  //>  55


```

----------------- RefactorCode using Memorizations-------------------------

Note: Memorization is labeled  memo in the function

Javascript Implementation

```
function fib(n, memo = [ ]){
    //     Check if we the computed  in our  Memo

		
     if(memo[n] != null){
       return memo[n]
       }    
    let result
    
     if(n <= 2){
		 
       result =  1
			 
       }else{
			 
         // We add memo as an parameter to our recursive functions, so it can be  accessed at each iteration level.
				 
         result =    fib(n -1, memo) + fib(n -2, memo)
  
         }
         memo[n] = result // store Results into memo
				 
         return result
    }
     console.log(fib(40))
		 
		 ```
		 
There you have it folks, JavaScript is an awesome language, and this are just my thought and understanding on some concepts that are simple, but often explained with a lot of confusion.  Look out for the three part of this article to wrap up recursion. 

#####  Resources:

Look here for the break down of Memorization and hashMap with a Java Implementation.
https://www.reddit.com/r/ProgrammingBuddies/comments/1v1nxf/tutorial_memoization_and_hashmaps/

  


