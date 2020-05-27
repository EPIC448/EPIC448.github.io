---
layout: post
title:      "Big-O Notation in lame man terms."
date:       2020-05-27 17:07:12 -0400
permalink:  big-o_notation_in_lame_man_terms
---

  
   A little mind snack for the Non- techie individuals on this blog . Please keep in mind, this is just a surface level explanation on the Big O topic. More resources are provided at the bottom for you to explore at your leisure. 

 **What**
 
 For the non tech enthusiast here, Big O can be considered the measuring of the  "Horse-power "in your coded algorithm. In insight,  you can have 2 codes side to side and they both solve same issue which may seem unimportant. But when you start working with large data sets, this becomes very important to the developer, shareholders and even you're server provided. If I have lost you, there is more to come later on. 

> "Big O notation (with a capital letter O, not a zero), also called Landau's symbol, is a symbolism used in complexity theory, computer science, and mathematics to describe the asymptotic behavior of functions. Basically, it tells you how fast a function grows or declines." 
    ' According to  "https://web.mit.edu/16.070/www/lecture/big_o.pdf"

   Lame terms: Big O is the horsepower in you code, kinda!!!  As most cars are categories by the amount of horse power they produce. Big O is like that but cooler in that  it combines a lot of components with it. And you don’t need a car or a mechanical team to make it work.

**Why**:

 Why do we even need Big O?  That is a great question.  Let us go back to our car Horse power analogy. Imagine being on a racing strip and watching 2 race cars going at it. we can assume that this cars are going fast by default and  would probably look identical speed-wise as perceived by the human eyes.

 Now assume, That we are gonna race in a formula one(F1) race of which the best racers in the world are present.  To give our self a winning chance, we can’t depend on the human eye-ball to select which of our two fast cars to take to the F1 race. Rather, as an hypothetical owner or manager in this race, we most look at data such as run time, speed, horsepower,  and other factors(weather, tires, etc..) you get the point. 

 One of the key features that would make this decision easier would be the horsepower of each car in relation to speed and amount of time each car  took to complete a full circle around the track.  This is what Big O does for your code. It helps to collect data on which function or algorithm is best for a product or feature in a product.

  This relate to the real world as Big O can down right be the differences between a website that is responsive to its users or costumer or same website with a poor coded algorithm that take 2+ minute to load which often lead to losing costumers. you guessed it, the company button line would take a tank at this point. 



 **where **:  
 
   Often can be found in a code base, It is a way to quantify how efficient our code is. And this can be the difference between a code execution that run for 5 seconds or  1 hour. Which is a big difference. Also, the memory and storage required for the code to run often is the difference maker between a company or business owner paying thousand or millions of dollars for this services i.e amazon clouds, or Google clouds to name a few.

**Cruzando: **

  For a regular non-developer, this article may not make  much sense to you which is okay. However, Big O affects you too. How you ask? 

 Analogy 2:  Imagine a scenario where you type  find Number "9” in you google search  bar with assumption that the google search system uses what we call a Binary Search algorithm looking through a collections of number 1,2,3,4,5,6,7,8,9,0. or arrays of numbers .  Well,  thanks to Big O, we can get a visual illustration of what happens below. 


![](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.computerhope.com%2Fjargon%2Fb%2Fbinary-search.jpg&f=1&nofb=1)


Big O allows us to measure  how effective this algorithm is and help us choose the Binary search algorithm vs it counter part Loop algorithm. Simply because the Binary search algorithm completed the task in less operations then its counter part Loop alogorithm.

![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.cdn.geeksforgeeks.org%2Fwp-content%2Fuploads%2Floops.png&f=1&nofb=1)

To the common eye, they both work just fine, but any developer would tell you that when you are working with a big data set such as E-Commerce website, BlockChain network , or Streaming services company, Binary search algorithm would always win, why?

Going back to our “9"search analogy & diagram,  the For-Loop algorithm would compare the input “9” to all the letters in the given array while Binary search on the other would simply chop the data in half every time comparing the location of the number “9" to the other numbers,  till it get the number “9”.  This make for a quicker snappier responses than the latter which is the Loop algorithm .


**Limitation of  This article :** 

This article does not cover time and space complexity as this are important topics in relation to Big O. You can read about those topics below. We may cover them in the future


**resources**:
  https://web.mit.edu/16.070/www/lecture/big_o.pdf
	
https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/

https://www.tutorialspoint.com/time-and-space-complexity-in-data-structure



