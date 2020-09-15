---
layout: post
title:      "Last installment  on Graphs [How do we Store them]"
date:       2020-09-15 16:15:15 +0000
permalink:  last_installment_on_graphs_how_do_we_store_them
---


  This would be the last installment of what we have being chatting about in regards to Graphs.  We now know how they  function.  However, what is the use of all that knowledge if we cant store them or represent them in code. 

![](https://media.giphy.com/media/26FLfBuFp3SZBypFe/giphy.gif)

 Calm down, you will not be writing code for this. Rather,  I would give a visual representation  of what is going on behind  your console. 

### P.S if you missed the last 2 articles, you can access them here.  (Include the 2 links)


http://techuture.com/types_of_graphs

http://techuture.com/your_online_information_collected_with_graphs_p


As you are well aware by now, Graphs are implemented in many ways, but the most common formats are Adjacency List and Adjacency Matrix. 
As represented in the picture below of both methods shows the same Vertices and Nodes and there connections.


## Figure 1:1
![]( https://algorithmtutor.com/images/graph_representation_directed.png)
 

 [ What does that mean .] ![](https://media.giphy.com/media/j5KUmGQGlQRlU2VQWY/giphy.gif)
 

 ### In Simple Terms

**Adjacency Matrix**

  This method is interesting in that it is Implemented with nested arrays, Usually in role and column or what is referred to as two – dimensional array.  Almost like the multiplication table we all were thought in elemerty school only without the multiplication part. 

***For Instances:***

  If you look at figure 1:1, 
  Roll 5 - Column 2  has 1 indicating that there is a connection (lines between those nodes). On the other hand, if  is has a 0, it has no Lines or connection. 
 
Note: Rolls and Column though represented by 1. However, You can also add True  or false, or Yes or No indicating the connection (edges) between the nodes (vertex).



Look Picture on Wikipedia for more details .

https://en.wikipedia.org/wiki/Adjacency_matrix 
 
 Often look like this ![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Symmetric_group_4%3B_Cayley_graph_4%2C9_%28adjacency_matrix%29.svg/250px-Symmetric_group_4%3B_Cayley_graph_4%2C9_%28adjacency_matrix%29.svg.png)

## **Now on to it  Twin brother,**


**Adjacency Lists.**

 Though very quick, often uses an array, list or Hash table with [ key value peer data structure ] to pair store the edges or connection.  As indicated in the Figure 1:1 above.

*** ….. Still confused……. ***   ![](https://media.giphy.com/media/11DFuwckOK9mdG/giphy.gif)
 
 Here,  we use an array or list to store the edges in  Figure 1:1 diagram. 
 
 Further, we can store these Adjacenc y List 2 ways. A hash table (Using a key value pairs) Or Arrays. 
    
Look to image Figure 1:2 to simplify the method further. 
Image address: 

## **Figure 1:2**

![](https://www.oreilly.com/library/view/learning-javascript-data/9781788623872/assets/268857bd-bb32-4fa5-88c9-66d7787952e9.png)


 
**Note:**  
The A-I column on the far left of the table are referred to as  Keys and the remainder letter in the second table are Values.
  Taking a closer look, you will notice that when a Key has a value in it, when that Same value is used as a key, it has a values of its former key pair. 
	

#### ---- Super confusing I know.----- ![](https://media.giphy.com/media/4JVTF9zR9BicshFAb7/giphy.gif)

 **This should help **
 
  Looking up Letter D in the Table on the Key section has the letters(A,C,G,H) as it value.  Now, let take letter C on the Keys, You notice that it has letters(A,D,G). As you can see, letter "D" and letter "C" are connected because they have each other as a key value pair and vice versa. 

 *Yo'll all GRAPHED UP*  ![](https://media.giphy.com/media/JLtQeoVXD5yKI/giphy.gif)

 For those that want a little bit more flavor, below is a Picture of  How adjacency matrix and Adjacency list perform in regards to Big O notation. 
 
 Remember 
 E = Edges[lines connecting the nodes],  V = vertices[Nodes]


If interested . 

![](https://images.slideplayer.com/23/6837230/slides/slide_47.jpg)
 
 For more reading on the topic you can Drop by :

https://www.geeksforgeeks.org/comparison-between-adjacency-list-and-adjacency-matrix-representation-of-graph/#:~:text=Adjacency%20Matrix%3A%20Adjacency%20Matrix%20is,of%20vertices%20in%20a%20graph.&text=Adjacency%20matrix%20for%20undirected%20graph,vertex%20j%20with%20weight%20w.

