---
layout: post
title:      "Another Binary Search Trees!!1"
date:       2020-07-24 01:14:05 +0000
permalink:  another_binary_search_trees_1
---


#  *Facts*:
 This Topic has being discussed so much. It like talking to a dead horse. So why the heck do you need one more explanation.  As you know, the goal is to make it so simple even the layman can understand it.    This is very important for those that a learning or have a small interest in  software development. 



### *The following is the definition of Binary Search Tree(BST) according to Wikipedia*

Binary Search Tree, is a node-based binary tree data structure which has the following properties:

* The left subtree of a node contains only nodes with keys lesser than the node’s key.
* The right subtree of a node contains only nodes with keys greater than the node’s key.
* The left and right subtree each must also be a binary search tree. There must be no duplicate nodes.

The above properties of Binary Search Tree provide an ordering among keys so that the operations like search, minimum and maximum can be done fast. If there is no ordering, then we may have to compare every key to search a given key.
   

**** Notice: ****

![](https://media.geeksforgeeks.org/wp-content/uploads/BSTSearch.png)

If you pay close attention to the Tree you notice that the left side is greater than then the Right, thus in the mid we have 8. The purpose of this is to search the keys of the tree to get the values. 

![](https://media.giphy.com/media/J0WtGU7W9knOo/giphy.gif)
	

*** Let me explain. ***
      
 ![](https://media.giphy.com/media/Yo8q8MFBmyKLyQt6lJ/giphy.gif)
 
  Binary search tree works differently  from other algorithm in that when given a value to find in the array, the computer first define the complete list as our search space, the number can exist only within the search space. 
 Sidebar: Search space meeting the numbers that are only in out table. 

 Now we compare the number to be searched or the element to be searched with the mid element (mid-way of the search) of the search space or the median and if the record being searched is lesser we go searching in the left half else we go searching in the right half, in case of equality we have found the element. 


![](https://media.giphy.com/media/hTNakNKHf8aaOM9sGt/giphy.gif)
 
 
  In binary search we start with ‘n’ elements (given number) in search space and then if mid element is not the element that we are looking for, we reduce the search space to ‘n/2’ and we go on reducing the search space till we either find the record that we are looking for or we get to only one element in search space and be done with this whole reduction.


Let go back to our Picture. 



![](https://media.geeksforgeeks.org/wp-content/uploads/BSTSearch.png)





Say you are looking for Number 7.  The “N" element 

1.  Step 1, N = 7,  is compared to the root value of (8) which is a no, because 7 is less then 8 so our search goes to      the left side of the tree. 

2.   Then “N" = 7 is compared 3  which is a no because 7 is greater than 3, so it move to the Right side of the tree
3.   Then “N" = 7 is compared 6  which is a no because 7 is greater than 6, 
4.    so it move to the Right side of the tree landing on 7.
5.    Turn Up and Celebrate..... 

### Limitation of this article:


 There more to the Binary search method as we did not explore topics such as  inserts and other methods.
 Code was not included in the article to peek the content light.  
 Resources You can check out: Has lots of good information on it 

https://algs4.cs.princeton.edu/32bst/

