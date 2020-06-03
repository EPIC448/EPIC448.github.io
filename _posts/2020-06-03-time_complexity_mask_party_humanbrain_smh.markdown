---
layout: post
title:      "Time Complexity/ Mask Party/HumanBrain SMH"
date:       2020-06-03 15:36:43 +0000
permalink:  time_complexity_mask_party_humanbrain_smh
---


 If you ever come across a group of developer and hear them talk about Big O [which i covered last week … 
 [Lame man Big O]( http://techuture.com/big-o_notation_in_lame_man_terms…]) you probably heard of time complexity. 

 Now to the regular human, “because developers are special creatures or at least we think we are” you may assume, Time Complexity deals with the number of time it take for a program to execute or  how many times a program can run a specific task without breaking. Which is part of the story with some missing pieces.

   "In computer science, the time complexity is the computational complexity that describes the amount of time it takes to run an algorithm. Time complexity is commonly estimated by counting the number of elementary operations performed by the algorithm, supposing that each elementary operation takes a fixed amount of time to perform. Thus, the amount of time taken and the number of elementary operations performed by the algorithm are taken to differ by at most a constant factor.”
  by 'https://www.geeksforgeeks.org/understanding-time-complexity-simple-examples/'


**Confused**
	I can feel the head rolling back already accompanied with a confused look of what does that even mean. 

  ![](https://media.giphy.com/media/O4IntqGDGeFzi/giphy.gif)

	
	Allow me to expand on the topic a little using an example that was explained to me  a while back as we bring a lame man understanding to the topic of Time complexity .

Summary [https://www.geeksforgeeks.org/understanding-time-complexity-simple-examples/]


 **Keep In mind: **
 
Time Complexity of algorithm/code is not equal to the actual time required to execute a particular code but the number of times a statement executes.



** Breaking down with Real life examples. 
**

![](https://media.giphy.com/media/xUOwGixePQo3pGmsNy/giphy.gif)  

No, not that break it down....  Smh.
	Imagine you hosted a dinner party for 50 people in your grand dining room of your massive  castle. With all the guests masked or wore masks just like the medieval times. 
	
	
![](https://pbs.twimg.com/media/DdUiPWPW0AAjPhH.jpg)
		 
		 
 And you  gave a key of your wealth vault to one of the guests. Due to the mask, you have no idea who the individual is.  You were sitting at the long dinner table and the food were served. Suddenly, you realized you do not have a spare key to the vault, thus, you want the key back or it is lost forever including the wealth in the vault. 

**Time complexity in this situations**:


**O(n2):**  you asks the first person seated to your left if they have seen the key or  if they are aware whom else of the 49 guests has the key.

**O(n):** The host walks around the dining table to each person to ask  if there have seen the key. 

**O(log n):** In this scenario, all the guests are divide into 2 halves(25 guest in room A and 25 in room B). Then further subdivided by 2 again for each group on-till  each room in the castle is filled with only one guest. Then each guest can be asked for the key.



 There are many more Time Complexity beyond the above examples, this is just to list a few. Now some of you may be thinking why not just check each person on the way out. Which seem reasonable task as a human using the human brains to think. 

However, time complexity and algorithms runs on your computer, thus your computer does not think like you the reader who is a human. This is the reason for computer languages  such as java, javascript, ruby and C++ just to name a few as a means of communication between a human brain and a computer.And that is what make software developer so special as they bridge this gap.  

![](https://media.giphy.com/media/11U4Aj0WMoruyA/giphy.gif)

**Conclusion:**

  Time complexity is  how well a  program Scales.  It not about the raw power of a program rather how well a program maintains it performances when giving large data. Thus,  you can perceive Time complexity as  the  measuring of actual time required in executing each statement in the code combined with how many times each statement executes. Hopefully, this shade some light on time complexity topic.  

For resource on the topic: 
https://medium.com/@ariel.salem1989/an-easy-to-use-guide-to-big-o-time-complexity-5dcf4be8a444

