---
layout: post
title:      "Solving algorithm Problem and pattern.  Multiple Pointers"
date:       2020-07-02 13:52:24 +0000
permalink:  solving_algorithm_problem_and_pattern_multiple_pointers
---


   Bringing simplicity to code. This week we chat on another pattern of code solving namely Multiple pointers.  If you're an advance programmer, and you know this concept, you may skip on by. However, there are people like us that we're not born coders, so here I breakdown the simple logic behind Multiple pointers. 
 
 **Definition:** 
 
  Creates pointers, values or Markers that correspond to an index or position and move towards the beginning, end or middle based on a Certain condition. Efficient for solving problems with minimal space complexity as well. 
When can i use it?
   Great for linear structure (i.e array, string), linked-list(  single or double linked-list), search for pair of values, and searching for an element that meets a condition. 


 **Example:**
 
 Here,  i give a very popular example in regards to this topic. Seriously, type (Multiple pointers ) in to google and you can find its .
 Write a function called sumZero which accepts a sorted array of integers. The function should find the first pair, where the sum is 0. Return an array that includes both values that sum to zero or undefined if a pair does not exist. This will only work with a sorted array. You move one pointer at a time, one side at a time. You move one pointer and test, then if the test is returns false, you move the other pointer and test.



![](https://miro.medium.com/max/1400/1*6LL51IhpUnJlnvfVgkq5yg.png)


 

If your not a code-head [yes… its a word now] like i was, you may not understand with all the above mean.  Well lucky for you, I am here. 

![](https://media.giphy.com/media/UPOsAgqtBq0Ug/giphy.gif)

**Simplification: **
 
So you're a big shot contractor in your home town and you are contracted to build the next city Hall.   From personal experience, 
![](https://media.giphy.com/media/l3vQYe7l1TInypnYA/giphy.gif)

I know  one of the tools you need to complete this task of building the town hall is what we call a “High precision flat water ruler” or Spirit level
   
	 
	 
 If you're unfamiliar with this tool. Here is a quick definition. 

![](https://i2.wp.com/www.diy-extra.co.uk/wp-content/uploads/2018/10/using-spirit-level.jpg?resize=800%2C445&ssl=1)

 *  "A spirit level, bubble level or simply a level is an instrument designed to indicate whether a surface is horizontal (level) or vertical (plumb)."    by Wikipedia*


 
And the point of this tool is to get a balanced, flat, precise surface as our human eye tend to fool us all.  For this tool to function, you the contractor or user “must" adjust the ruler in parallel to a surface for the bubble to get in the middle hence “ZERO”.  Now While this picture does not have numbers or indicators on it, similar tools like the picture above has them. 

 

  
 As you can see in this picture, 
 ![](https://t3.ftcdn.net/jpg/02/43/40/18/240_F_243401831_4Mu2vvdnhr5xRwZy9V9immtuwNaPRqOM.jpg)
 The user or you the contractor in our story must identify multiple pointers on your surface on the right and left side to make sure that your bubble stays in the middle, thus "ZERO" 







Just like our code, we are comparing element in our code from both right side and left side in an array  according to the code  example above to find the ZERO-SUM ground , then we return that answer . 


I want to hear for you, Comment below if this was helpful, and how have you applied it in your code or job interview. 

Cheers

