---
layout: post
title:      "Mind your Ps and Qs straight at the HEAP!!!"
date:       2021-07-24 13:30:45 +0000
permalink:  mind_your_ps_and_qs_straight_at_the_heap
---



Heaps is a type of tree data structure great for keeping tabs on the greatest and latest data element in a dataset.  
 
To really understand Heaps, here is a reminder of Priority Queues. 


** Revisit this --- Quick look at Priority Queues(PQ)** 

 Queues in general follow the First In, First Out (FIFO) principle allowing for the insertion of data at the end and access or removal only from the Front of the Queues. It behaves like the classic queues as insertion is similar to an array and deleting data occurs at the front of PQ, but when data is inserted, it remains in a specific order.


 PQ is an abstract data type, meaning it is implemented using other data structures such as an array. Its primary function is Deletions 0(1) and Insertions 0(N) because we turn the end of a regular array to be the front of the PQ yielding us Deletion of 0(1). 
 

However, Inserting requires a traversal through each element causing a shift of cells in memory thus 0(N) which seems minute, but in big data, the  situation  leads to a drag.

 **PQ use cases**.
 
An application that manages the triage system for a Hospital emergency room uses PQ data structure. A patient that arrives with a life threatening injury is given a higher level of “priority” and placed in front of the queue, then a patient with a flu or cold even if the flu patients arrived first.

**Enter Heaps.** 

I mentioned how PQ can be a drag when not done properly, this is where Heaps saves the day. 

 Disclaimer: there are many types of Heaps out there with endless implementations. So here we focus on Binary Heap

Note:  Binary search tree is when each node has a maximum of two children nodes
Binary Heaps  is a specific type of Tree.

**2 types of Binary Heap**

1: Binary Max- Heap(we will use for our example).

2: Binary Min- Heaps (simply reverse the rule from the Max-Heap).

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a8056b6a-f519-4d43-a901-dc0aa5125a4c/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T130946Z&X-Amz-Expires=86400&X-Amz-Signature=6f46a84fd79908fd3a04a670d632dca4569c1c372c3a2c3aae9b3c0df9276514&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)


**Binary Max Heap rules**

1: Each node value  must be greater than both its descendants. 

2: The tree must be complete. 

Meaning no nodes are missing on that tree. 

**Heap Properties.**

By nature, Heaps are loosely ordered compared to binary search trees. However, the root node is always the greatest value (referring to max Heap). This is why it is a good  tool for PQ  implementation because we want access to the greatest priority located at the root node. 
Words: Last Node. ( the Rightmost node in its bottom level.)

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4f810def-9d6f-4924-befd-eda005fe0375/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T131109Z&X-Amz-Expires=86400&X-Amz-Signature=5f0c65ec30d27903a42cfcc96a5448f8507a24131b78f7b39b3ed80de7c7a727&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)


**Heap Insertion**

 Inserting into a heap data structure could be interesting as each process influences the other. So here is the process of execution. 

1. Create a node containing a new value & insert it at the next available rightmost spot in the bottom level.
2. Compare new Node with it's parent node
3. If the new node is greater than the parent node, swap the new node with the parent node.
4. Repeat step 3, Thus, moving the new Node up through the heap, till it has a parent whose value is greater than it. (Moving the Node up the Heap is called TRICKLING the node up through the heap.)


> Note: the reverse of this applies to Min Heaps. (Google “min heap insertion process. ”)

 > Keep  in mind that we still need to resolve the last node here. 

**Heap Deletion**


**Rule**: only deletes the root node

** Steps:**

1. Move the last node to where the root node was, thus removing the original root node.
2. Tricklet root node down into its proper place. 

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/44dbf39f-5c74-4b0b-86b2-c32efefa384d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T131221Z&X-Amz-Expires=86400&X-Amz-Signature=474ace2af746f2080ed8fc030f88266e0bc679e9db2f2611a722ec26e28c6cd0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

**What is Trickling down a Node?**

 While it may sound like an easy process, tricking down actually is not a quick task as there are processes involved. 

**Steps**:


1. Check both children of the Trickle node and see which one is larger.
2. If the Trickle node is smaller than the larger of the two child nodes, swap trickle node with Larger child.
repeat Steps 1 and 2 until the trickle node has no children who are greater than it.


[Details of trickling down a node](https://discourse.opengenus.org/t/max-heap-and-min-heap/3388)

[Video explanation of this concept](https://youtu.be/jHZu1GV27tI)

Time complexity for deletion in heaps is O (log N) because as we trickle down the node, the root goes down through all logs (N) levels of​​ the Heaps. Which begs the question how Insertions and deletion are influenced by the last node.


**Why insertion & Deletion depends on the last node**

Inserting a new value elsewhere other than the root makes the heap becomes incomplete. Thus, completeness is important to keep our Heaps balances. Keep in mind that deleting causes the last node into a root else the heap becomes imbalance.

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a64e72b6-1bb9-4772-86c4-0a69630d2641/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T131706Z&X-Amz-Expires=86400&X-Amz-Signature=fca63fd5f4d1f91488c7e93c55574c9a759f77214ca4473942b13422d65c39b1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

**Tree representation of Heaps as Array**

To make the “finding the last Node”  efficient as related to the heap game. We can use an Array to implement a heap. To, we assume that a Tree consists of independent nodes connected to each other with links.

 > Balance is so important  because it's what allows us to achieve O(log N) operations. If is not balances, It could take O(N) steps instead.

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/70ff1b00-7237-42e6-9097-a370b5795820/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T131855Z&X-Amz-Expires=86400&X-Amz-Signature=2d4d65c61a9726a39e3cf9d1a0161761a4fad14878dbef7ddab929deda0c9710&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)



![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/deee1378-62e7-4261-93ca-4f0a769d2a3a/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210724%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210724T131753Z&X-Amz-Expires=86400&X-Amz-Signature=e53cbdbdb782a5d2a3298886ef84bed3a45724427254ad6db8b330efa8cf0120&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)


**Notice:** 

 Root node is always at Index 0
 
Move down to the next Level going from left to right, assigning each node to the next available index in the array.

The second levels, it left node (19) index 1 and right node(36) index 2. When we reach the end of a level, we move down to the next level and repeat this pattern.

> Hint: Array solves the problem of the last node. Because the last node always stored as the final value in the array. 

This makes it easy to trivial to find the last node by just accessing the last element in the array. Also, when inserted into to heap, we do so at the end of an array in order to make the last node


```
Ruby 

class Heap
	def initialize
			@data = []
	end

 def root_node
    return @data.first
	end

 def last_node
	return @data.last
 end
end

```


**Traversing an array - based Heap**

While normally we are used to Nodes with links. How to know which Nodes are connected to each other?
Because we assign the indexes of the heap nodes according to the pattern described earlier, the following traits of a heap are always true:

To find the left child of any node, we use the formula (index * 2) + 1
To find the right child of any node, we use the formula (index * 2) + 2
With the above formula we can treat our array as a tree.

Insert code. 

```
Ruby  implementation

class Heap
	def initialize
			@data = []
	end

 def root_node
    return @data.first
	end

 def last_node
	return @data.last
 end

  ## new addition

	def left_child_index(index)
			return (index * 2) + 1
	end

		def right_child_index(index)
			return (index * 2) + 2
	end



end. # end of Heap class
```




Insert code formula to find the Node parent.

```
# this goes inside the heap class

def parent_index(index)
		return(index -1) /2
end

```



Insert code here Heap Insertion. 

```

def insert(value)
 #turn value into last node by inserting it at the end of the array. 
 @data << value

 #keep  track of the index of the newly inserted node:

new_node_index = @data.length - 1

# the following loop executes the  "trickle up" algorithm.

#if the new node is not the root position. 
# and it's greater than its parent Node:

		while new_node_index > 0 &&
		@data[new_node_index] > @data[parent_index(new_node_index)]
		
		
		#swap the new node with the parent node:
		 @data[parent_index(new_node_index)], @data[new_node_index]= 
		@data[new_node_index], @data[parent_index(new_node_index)] 
		
		 #update the index of the new Node: 
		
		 new_node_index = parent_index(new_node_index)
		end
		
end


Implementation: Heap Deletion. 
 Note: we use to helper method in this process to get things in place. 
has_greater_child and calculate_larger_child_index.


# does not take in any argument 
def delete
			#we only ever delete the root node from a heap, so we pop the last node from the
		# array and make it the root node:
		 
		@data[0] = @data.pop
		
		#track the current index of the "trickle node": 
		
		trickle_node_index = 0
			
		# the following loop executes the "trickle down" algorithm:
		#we run the loop as long as the trickle node has a child
		# that is greater then it:

		while has_greater_child(trickle_node_index)
			#save larger child index in variable:
		
				larger_child_index = calculate_larger_child_index(trickle_node_index)

				#swap the trickle node with its larger child:

					@data[trickle_node_index], @data[larger_child_index] = 
					 @data[larger_child_index], @data[trickle_node_index]

			#update trickle node's new index
				trickle_node_index = larger_child_index

		end
end

 #Helpers Method

  def has_greater_child(index)
      #we check whether the node at index has left and right
			# children and if either of those children are greater
			# then the node at index: 

     (@data[left_child_index(index)] &&
			@data[left_child_index(index)] > @data[index]) ||
			(@data[right_child_index(index)] &&
			 @data[right_child_index(index)] > @data[index])
	end

	def calculate_larger_child_index(index)
    #if there is no right child:
    if !@data[right_child_index(index)] > @data[left_child_index(index)]
    #return right child index:
		return right_child_index(index)
		else #if the left child value is greater or equal to the right child:

     #Return the left child index:
				return left_child_index(index)
	
	end
		
```




As always, I like to give resouces  to explore beyond what is here. 


[Heaps Articule](https://discourse.opengenus.org/t/max-heap-and-min-heap/3388)

[GeeksforGeeks on heaps](https://www.geeksforgeeks.org/heap-data-structure/)


