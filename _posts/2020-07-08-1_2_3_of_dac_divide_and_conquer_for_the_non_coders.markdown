---
layout: post
title:      "1,2,3 of DAC(Divide and Conquer ) For the non coders.  "
date:       2020-07-08 13:55:10 +0000
permalink:  1_2_3_of_dac_divide_and_conquer_for_the_non_coders
---




>   In computer science, divide and conquer is an algorithm design paradigm based on multi-branched recursion. A divide-and-conquer algorithm works by recursively breaking down a problem into two or more sub-problems of the same or related type, until these become simple enough to be solved directly. The solutions to the sub-problems are then combined to give a solution to the original problem. 
	
	By Wikipedia..


# * It is Good for..* 


This divide-and-conquer technique is the basis of efficient algorithms for all kinds of problems, such as sorting (e.g., quicksort, merge sort), multiplying large numbers (e.g. the Karatsuba algorithm), finding the closest pair of points, syntactic analysis (e.g., top-down parsers), and computing the discrete Fourier transform (FFT)


# DAC  3 parts.  

1. Divide: This involves dividing the problem into some sub problem. However, is the problem is small, we can solve it directly.

2. Conquer: Sub problem by calling it recursively until sub problem solved.
     Hint: We cover recursion later on in the text.

3. Combine: After the  sub problem is solved, it is combined together  so that we will get a solution to the problem.
 
Now you may not like what you have read so far due to little programming experience or bored. let change that as this article is designer with the non coders in mind. Here are some visual representation of what this may look like on paper.  

![](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fbigdata.ices.utexas.edu%2Fwp-content%2Fuploads%2F2014%2F03%2Fdivide-and-conquer1.png&f=1&nofb=1)


# or 


![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2Fe%2Fe6%2FMerge_sort_algorithm_diagram.svg%2F220px-Merge_sort_algorithm_diagram.svg.png&f=1&nofb=1)



** Why does it break down in parts? **

Image …    Why.
 
   Great question!!!!  If DAC was a person, her  favorite quote would be:
	 
> 	 “Inch by inch, life’s/it’s a cinch,  yard by yard, life’s/it’s hard,” or  “Mile by mile, life’s/it’s a trial” 
> 	 has been cited in print since at least 1977.  "
> 	 
  
	The Goal of DAC is to break down a problem to its absolute lowest element to solve it, and then add that back up to make the total solution .
	
This process is done through recursion.
 
** what is Recursion. **
 
   Detour {Picture}…
 
Recursion is a function that call its self. Now, that may not make much sense if you're not in the programming world.

# *Picture this.*
    The hope of the world rest on your shoulders as you are task to find the keys to lunch a missile to strike a meteorite  else it would  make contact with earth and would be bad. The key is located in a Matryoshka dolls, thus you  need to go through or open each doll to get to it. 
       
			 ![](  https://media.giphy.com/media/X8HbeXDF7nzaM/giphy.gif)
			 
   
 We do not know how many dolls are there, but we would need to keep looking till we get to the key else no more ice creams for all of us. 

* Code representation:* 
 
 
 ```
   def findKey(doll):
	item = doll.open()
    if item == key:
    	return key
	else:
    	return findKey(item)
findKey(doll)


```

 As you can see, we keep call the same function (findKey(doll) ) till we get to the key.
 

In conclusion, DAC is an awesome tool and when used properly can open the flood gates of creativity in programming. Just understanding this concept can help you make better software related decision even as a non- coder or programmer.  

This is just a quick over view of how Divide and Conquer (DAC) works in programming with non-coders in mind. Below are further resources for your reading pleasures. 

Cheers.    

 Further Resources: 

https://www.geeksforgeeks.org/divide-and-conquer-algorithm-introduction/

https://skerritt.blog/divide-and-conquer-algorithms/
