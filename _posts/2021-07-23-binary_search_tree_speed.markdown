---
layout: post
title:      "Binary Search tree Speed"
date:       2021-07-24 01:38:13 +0000
permalink:  binary_search_tree_speed
---



Coding out a HashMap of a hash-table is no doubt fast, specifically 0(1) with search, insertion, deletion. There is no doubt that it yield us amazing speed only if we do not care for order (alphabetization, or smallest to largest and vice-versa).

**Welcome to Tree**

Tree is a Data structure that maintains order yet, has a fast search, insertion, and deletion for instance binary search tree. This data structure is node based of which a node can link to multiple nodes.


![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/3e9a211a-e4a8-4e7a-ba42-ffc3d8d8c2c3/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T005938Z&X-Amz-Expires=86400&X-Amz-Signature=a8f929ba6e58ff558aaba5429c7079062f328bfe5c22b0080687f72fe9945f30&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)



**Ackwords parts** about trees can be seen in the way it reads. Looking at the diagram above. Pay attention to how it reads.

>The uppermost Node "20" is the root. this is how trees are depicted. 

> In the picture above, 20 is a parent of "100" & "3", thus, "100" & "3" are children of "20".
 
> "50 & 15" and "250 & 35" are children of "100" & "3".

 > In the tree, a NODE can have descendants and ancestors. A descents are all the nodes that stem from a nose, while a Node's ancestors are all the nodes that is stems from. 
 
> In our example, "20" is the ancestor of all the others nodes in the trees, And all the other descendants of the "20


**Levels to these Trees.** 
Trees have levels by default which is not always apparent from the offset.  

![](https://qph.fs.quoracdn.net/main-qimg-49af4ff081b2dff66d1f41dd6f695b96)

**Important concept to grasp about a tree. ** 

Trees property suggests that nodes or “subtrees” on both sides of the root should be balance or have the same number of nodes, giving use a balanced tree. 

![](https://helloacm.com/wp-content/uploads/2016/04/balanced-tree-or-not.png)
 
 **Binary Search Trees**
Binary Search Trees (BST) is a tree in which the node has zero, one, or two children

### BTS RULES:

. A nodes "left' descendants can only contain values that are LESS than the node itself, While a node "right" descendants can only contain values that are greater than the node itself.

. Each node most have a one "left" and one "right" child

```
PYthon Implementation. 
class TreeNode:
	def_ini__(sellf,val,left=None, right=None):
						self.value = val
						self.leftChidl = left
						self.rightChild = right

// we can build a tree like this
node1 = TreeNode(25)
node2 = TreeNode(75)
root = TreeNode(50, node1, node2)

// with this, we can search for any value very quickly
```


**Searching A BST**

  As usual, you have the tree. 
The Algorithm to search with a binary search tree is a follows:

1. Designate a node to be the "current node". (At the start of the algorithm, the root node is the first "current node"). Everything goes from here. 
2. Inspect the value of the current node.
3. If we found the value we are looking for . 😉, we may return it
4. if the value we're looking for is less than the current node, search for it in its left subtree.
5. if the value we're looking for is greater than the current node, search for it in its right subtree.
6. repeat Steps 1 through steps 5 until we find the value we're searching for. Or until we hit the bottom of the tree, meaning our value is not in the tree.

**Efficiency of Searching a Binary Search Tree
**

![Searching in a Binary Search Tree](https://static.javatpoint.com/ds/images/searching-in-binary-search-tree.png) 

**Note**:

Each step eliminates half of the remaining nodes from our search if it does not meet our requirements making BST O (log N). Which is the appropriate description for any algorithm that eliminates half of the remaining values with each step. Only works in a Balances BST.

```
Python Searching a BST.. We use Recursive Calls here. 

def search (searchValue, node):


if node is None or node.value == searchValue:
    return  node


elif searchValue < node.value:
	return search(searchValue, node.leftChild)

else:
	return search(searchValue, node.rightChild)



```

 
 
 **Insertion for BST**
  
	BST is best where we are inserting something.

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/89849365-441a-43b4-8aee-c71ecf582d62/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T010134Z&X-Amz-Expires=86400&X-Amz-Signature=e54889bc7e7147df64151fb3febc2067a1dcdd9876af879a17fb11974f030895&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

Keep in mind that there is always N steps it take to search the Nodes, Then +1 step to insert into the Tree (Log N) + 1 steps. Simply O(log N).

```
Python implementaion Inserting into a BTS Trees

def insert(value, node):

	if value < node.value:


	if node.leftChild is None:
		node.leftChild = TreeNode(value)

	else:
	insert(value, node.leftChild)
	elif value > node.value:
	


if node.rightChild is None:
	node.rightChild = TreeNode(value)
else: 
		insert(value, node.rightChild)
		
```

**Note**: 

🤔Only when creating a tree out of randomly sorted data do we get balanced trees. Else, if we insert sorted data into a tree, it becomes unbalanced giving use a leap sided tree.
Only a balanced tree does O (log N) the picture below will give use O (N) because it is linear

![](https://qph.fs.quoracdn.net/main-qimg-61f940ac3024035312e258262c8945fe)

> thus, If you want  to convert ordered array into a binary search tree, you better randomize the order of the data. 

In typical scenario, in which data is inserted in random order, a tree will be pretty  well balanced and search will take about O(log N).

**Deletion for BST**
 
 > The least straight forward of the bunch.
 
  Deletion here is tricky in for several reasons.
	
- If the node being deleted has no children, simply delete it.

- If the node being deleted has a children, delete the node and plug the child into the spot where the deleted node was. 

Note how 18 has no child [Referig to the digram earlier]

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/72f4cb2c-5a2d-41a4-8796-2366b7a32066/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T011354Z&X-Amz-Expires=86400&X-Amz-Signature=643600b2baadb9198654e7cb3a58b8a7a8e7c25fc247747bd80597f624d42fb0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

**Deleting a node with Two Children**

 * In Relation to the picture above.*
 
- When deleting a node with two children, replace the deleted node with the SUCCESSOR node. The Successor node is the child node whose value is the least of all values that are greater than the deleted node.
- Simply put, if we were to put the deleted node, and all its descendants in ascending order, the successor node would be the next number after the one we just deleted.

**Finding the Successor Node.** 

- Algorithm for this: visits the **right child** of the deleted value, and then keep on visiting the **left child** of each subsequent child until there are no more left children. The bottom value is the successor.

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7ec6891b-7576-4381-8ce4-84fac306cfa5/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T011424Z&X-Amz-Expires=86400&X-Amz-Signature=70da22d66d3c4cf239cfc7022677efc3c37f9fd392f50a22917afb37dc147dbd&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)


** So what happens with the successor Nodes. **

In case where we have Successor Node with Right Child?

- If the successor node has a **right child**, after plugging the successor node into the spot of the deleted node, take the former **right child** of the successor node and turn it into the **left chid** of the **former paren**t of the successor node.

![](https://cdn.guru99.com/images/1/020820_0600_BinarySearc6.png)

 Code Implementation 

```



CODE IMPLEMENATAION: USING RECUSRUTION 

 
 
Def delete(valueToDelete, node)


   if node is None:
      return None

   elif valueToDelete < node.value:
        node.leftChild = delete(valueToDelete,node.leftChild)
	       return node

  elif valueToDelete > node.value
        node.rightChild = delete(valueToDelete, node.rightChild)
		      return node

  elif valueToDelete == node.value:

 if node.leftChild is None:
    return node.rightChild

 elif node.rightChild is None:
	 return node.leftChild
 
  else:
	  node.rightChild = lift(node.rightChild, node)
 return node

 def lift(node, nodeToDelete):

  if node.leftChild:
		  node.leftChild = lift(node.leftChild, nodeToDelete)
		 return node

   else:
	    nodeToDelete.value = node.value


```

**The Efficiency of Binary Search Tree Deletion**

**Example**:  Let's say we're creating an application that maintain a list of book titles.  We want our application to have the following functions.

- Our program should be able  to print the list of book titles in alphabetical
- Our program should allow the user to search for a title within the list
- Our program should allow the user to  constantly change the list.

If we are not required to frequently change the list, an ordered array would be a nice data structure. But since, we need to be able to handle a lot of  changes in real-time,  If we have a million titles, a binary search tree may be a better choice.

I realize this post is very long at this point and  Delete operation for BST may be confusing, i employee you to explore othe resource that expand on this topic. 

Areas  skipped, includes **Traversal of a node Tree** .
For a deep dive on this subject and others, access this resources . 
[Binary-search-tree by isacccomputerscience.org](https://isaaccomputerscience.org/concepts/dsa_search_bst)

[geeksforgeeks-binary-search-tree](https://www.geeksforgeeks.org/binary-search-tree-data-structure/)

