---
layout: post
title:      "What is Space Complexity? Layman terms  .."
date:       2020-06-10 21:33:27 +0000
permalink:  what_is_space_complexity_layman_terms
---

 
Space complexity is the total amount of memory space used by an algorithm/program including the space of input values for execution. So to find space complexity, it is enough to calculate the space occupied by the variables used in an algorithm/program. Often, people confuse Space complexity with Auxiliary space. Auxiliary space is just a temporary or extra space and it is not the same as space complexity. In simpler terms.
Space Complexity = Auxiliary space + Space use by input values


**            Confused… …. WTF… does that even mean.   ![](https://media.giphy.com/media/LPdUmwrsRFAli/giphy.gif)
**

**** Picture This:****

  As a little child I remember my nieces getting a easy bake oven. [.insert a picture]. which are awesome by the way.  Let assume that you are 8 years old. And you have been gifted an easy bake oven because you are on track to be the next world Michelin star chef. Small but mighty, you decided to take on the most baked pie challenge all from the comfort of your kingdom a.k.a your room. 

![](https://media.giphy.com/media/fHTd06huYasYo/giphy.gif)

 In this situation looking through the space-complexity perspective, the easy bake oven is the algorithm that  “makes the pie”. The oven takes up a section or a part of your room just as an algorithm take up a space in your “computer memory”, It is much deeper than this, but let just use your computer for now.  Safe to assume that the amount of pies baked would not change the size of the oven. This is what we call the Auxiliary Space. As in no matter what happens, the size of the algorithm stay constant. 


Going back  to our scenario, an easy bake oven is useless without doing its job of baking food, an item or a product.  The size of the pie inserted into the oven is correlated with the size of the pie that comes out.  For all the chefs reading this, I know there are yeast involved, raising of the dough and all. For all tense purposes, we can assume that  once the pie is done, it need to be laid down somewhere to cool down and be counted to determine the total amount of pie baked. In this example, the amount of space taking up in your room by our "preverbal" baked / ready to count pies is  considers space used by input value.  Simply put, the larger the amount of value inputted into the algorithm equals the amount of space needed for the output or final results depending  on how much the input is manipulated going through the algorithm .  This can also impact how fast or slow a program runs. 

*Important Note:*  The best algorithm/program should have the lease space complexity. The lesser the space used, the faster it executes.

**Real-life application:**

If you don't believe me, remember back in the 2000s when the cell phones  seems to heat up after several hours of use as or the more gigabyte are used the more the phone become slower. ![](https://media.giphy.com/media/JVUJwAeMlXwmQ/giphy.gif)

This is equally applicable to the reject of the computer world, HP laptop. I recollect burning through two of those within 4 years college period as they overheat and were very slow. This is another instance of space complexity at play. As i write papers and conducting research  which we're stored  on my computer at that time, the slower it became .
![](https://media.giphy.com/media/3og0INAY5MLmEBubyU/giphy.gif)



**Why do you need to calculate space complexity?**

Similar to Time Complexity, Space complexity also plays a crucial role in determining the efficiency of an algorithm/program. If an algorithm takes up a lot of time, you can still wait, run/execute it to get the desired output. But, if a program takes up a lot of memory space, the compiler will not let you run it.
Algorithm Tradeoffs
With previous information, we can determine that space and time complexity play a huge part in The efficiency of an algorithm. the holy grail of algorithm is one that is taking less time and less space, but that is a unicorn. There is a trade-off between time and space. If you want to reduce the time, then space might increase.
 ![](https://media.giphy.com/media/xT9IgusfDcqpPFzjdS/giphy.gif)
Similarly, if you want to reduce the space, then the time may increase. So, you have to compromise with either space or time.  If I have lost you by now, we covered Time complexity last week , go  check out that article. (http://techuture.com/time_complexity_mask_party_humanbrain_smh
)


**Rules of thumbs [for the techie].**  

![](https://media.giphy.com/media/ma4msCmcHpAoBLU6hl/giphy.gif)

 Most **primitives**(Booleans, numbers, undefined, null) are constant space. No matter the size of the input , 1 or 1million, it take up the same amount of space.  Yes, though I mentioned that the larger the input size the out put will match it. In some situation such as primitives the output size stays constant. 
 
while  **Strings** on the other hand require O(n) space (where n is the string length).  As the input size or length increase, the output increase to match it so those the space it takes up. For example: if  you put in 50 unbaked pie in the oven, 50 baked pies would come out and take 50x space then a single pie baked pie will take up in your room. 

  Furthermore, **Reference types** which are generally known to be O(n), where N is the length of an array(or :Length of each pie) or number of keys in an object( or: Numbers of available  Flavor of pie ). Thus if an array.length (or: diameter of a pie) is 4 time longer compared to array.length (or: diameter of pie) that is 2, the array or pie with the length or diameter of 4 takes up twice the space of the others that are measured to be 2.
	
	
 This is just a surface level of Space complexity as this topic span much further then covered here.  Comment on LinkedIn if you would like to see more. 


