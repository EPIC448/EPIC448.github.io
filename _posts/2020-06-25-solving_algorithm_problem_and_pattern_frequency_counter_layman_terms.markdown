---
layout: post
title:      "Solving algorithm Problem and pattern. Frequency Counter LayMan Terms. "
date:       2020-06-25 13:32:18 +0000
permalink:  solving_algorithm_problem_and_pattern_frequency_counter_layman_terms
---


* This is not a Cure a.l, But it is certainly helpful pieces. to Keep in Mind when Solving a code Challenge. 
*
 Several things we will cover.:
  Frequency Counter:  Means what it sounds like, However, it can be used in a lot of situation. It can be used at comparing two data sets to each-other. It often uses an Object  or Sets and collect values or  frequencies of values. 

  ![](https://media.giphy.com/media/lz9lPkqddgoec/giphy.gif)

**Pitcure This **:

    You are a college student tasked with finding the 3 textbook for a course that you're would  be taking. The caveat is you need to find this text book in a brick and mortar stores with there prices, then find the same book online for half of the price of the brick and mortar store. Also, you are to keep track of the number of time you find the same price for both online and brick and mortar store.   
  
**Rant**: 
> College textbook are pure scam. You mean to tell me that there is a new edition every 24 month with 2-3 new pages added. And I have to pay $200+ for a new edition of the same book purchased at the school book store  that I would only use 3 times a year in the same class. And I can’t even get my money back because the same book returned to the same school book store would offer you $35.98  for the same book they sold you 2 months ago..SMH. 
>  ![](https://media.giphy.com/media/NRtZSQqTSCt5gyebtH/giphy.gif)
>    [Comment below on  if you had this experience  ]

   Back to the subject, You with the smarts would  look on line and search local stores to check out the  prices for the books. Also, you will have a method to track, book title, prices, location of the book etc.  The frequency counter part of this situation would be how many time did you see the same price of the book come up, either online or at a brick and mortar store. 
Then you compare the two collected data ( Online book prices, and amount of time the same price occurred ) VS ( Brick and Mortar book store  prices, and amount of time the same price occurred )


Using this pattern of problem solving  mostly result in O(n) notation and it helps us to avoid the need for nested loops or  O(Nˆ2) operations with arrays/strings

 When to use and Code representation:
 As mentioned, It it is amazing at comparing 2 datas to each other. 
 Example:  Write a function called Same, which accepts Two arrays. the functions should return True if every values in the array has its corresponding value squared in the second Array. it may not be in order. The frequency of Values must be the Same.  Frequency is Important.  





**Example** 

same([1,2,3]), (4,9,1) // true;

same([1,2,3]) , [1,9]) //   false because the length of second array is shorter than the first. 


![](https://miro.medium.com/max/1400/1*HK2y9ozZ5ikuuq1HRTUnqQ.png)


![](https://miro.medium.com/max/1400/1*BmOYTCI86NUoHVUK59Fvrw.png)




If you enjoy content such as this, let us know.
 
Comment below or linked-in where you have used this Pattern in your career, Job interviews, projects, or showing off to a group of friends. 


Cheers

sam.

Resources to Learn more. : 
https://www.google.com/search?q=Frequency+counter+algorithm+problem+solving&oq=Fre&aqs=chrome.0.69i59l2j69i57j69i60j69i65l2j69i60j69i61.1592j1j1&sourceid=chrome&ie=UTF-8



