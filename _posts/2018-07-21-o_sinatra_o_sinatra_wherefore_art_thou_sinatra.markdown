---
layout: post
title:      "O Sinatra, O Sinatra, wherefore art thou Sinatra?"
date:       2018-07-21 13:26:23 -0400
permalink:  o_sinatra_o_sinatra_wherefore_art_thou_sinatra
---


Never in a million years would I have thought that I could create something like the Fwitter app or my own Sinatra project. But guess what ladies and gentle men I did. And this article would be a short one on what I learned from my Sinatra project. 
   Sinatra is simple pre-written methods that we can include in our application to turn them into Ruby Web application. 

 Now, Sinatra has a lot of small concepts in it that helps the app function as a whole. For instance, we have the CRUD, MVC, Corneal and Active Record just to name a few. However, to save time, I would dive into some major concepts here and feel free to read more about the other concepts on the web. 

Let roll….

MVC in Sinatra A.K.A (Models, Views, Controllers) 
** 
   No Sinatra application is complete without the MVC.  Why???
Thought you will never ask. I would explain this with an undertone of a restaurant operation so it applicable to the real world.
   
  Models: (Chief in the Kitchen of a restaurant) this is the Logic area of the web application.  Data is manipulated and saved here.

 Views: (The food on the plate the costumer sees) this is the only part of the app that the user interacts with directly. It normally consists of HTML, CSS, and JavaScript.

Controllers: (The Waiter for each table that take food orders from the costumer) controller is the shuttle between the models and the views. It relays on data from the browser to the application, and from the application to the browser.




 Sinatra used CRUD or Create, Read, Update, Delete.  
*
 This helps us to understand which controller is connected which views. It helps to know how your website flow staring from when the user input a request into your application to what webpage is delivered to the user.  Here is a quick breakdown of the CRUD…

**Create** 
	Create a new.erb in views with necessary controller /POSTS action
     This should render index.erb (you might need to create an index .erb)

**Read**  
    It reads what is being passed in and in most cases, two different controller show and index.  i.e.

 Show renders the show.erb
  Index renders   the index.erb.

Create the get '/posts' controller action. This action should use Active Record to grab all of the posts and store them in an instance variable, @posts. Then, it should render the index.erb view. The code would look something like this: 

  Get '/posts' do #take in all the input
    @posts = Post.all
    erb :index
  end


**UPDATE**


Create a controller action, get '/posts/:id/edit', that renders the view, edit.erb. This view should contain a form to update a specific blog post and POSTs to a controller action, patch '/posts/:id'.
DELETE
The Delete CRUD action corresponds to the delete controller action,delete '/posts/:id/delete'. To initiate this action, we'll just add a "delete button" to the show page. This "button" will actually be a form, disguised as a button (intriguing, I know). The form will send a POST request to the delete controller action, where we will identify the post to delete and delete it. Then, the action should render a delete.erb view which confirms that the post has been deleted. It looks something like this: 

 

```
<form  action="/posts/<%= @post.id %>/delete" method="post">

  <input type ="submit" value="delete">input>
  <input type="hidden" id= "hidden"  name ="-method" value = "delete">delete</input>
</form>
```





**Sinatra Restful Routes
**
      There was a time when the Internet was so disorganized that creating contents was a pain in the backside.  This was because there was no pattern that allows easy data manipulation.  So a convention was developed called Restful Routes which is a type of standard for creating a web app. It best quoted by Flatiron school quote “Restful routes provides a design pattern that allows for easy data manipulation. It's nicer for users and nicer for developers to have everything consistent”. 

  It a clear road map between the HTTP verbs (get, post, delete) and the controller (create, read, update, and delete). This is why, when a user request an HTTP or a website, that HTTP method and URL is connected to a proper controller action that has the method and the URL, It executes the code in the action and determines which response gets sent back to our user.  Super Neat…. Yi.

 If we were to draw out the Restful Routes, it would look like this.  Details can be found at (https://learn.co/tracks/full-stack-web-development-v5/sinatra/activerecord/sinatra-restful-routes)


> ```
> HTTPVERB	     ROUTE	                  Action	                        Used For
> 
> GET       	     '/posts'	                       index action	         index page to display all posts
> GET              '/posts/new’ 	           New action 	         displays create post form                        
> POST	        '/posts'  	                     create action	         creates one blog post
> GET    	         '/posts/:id'                	 show action  	         displays one blog post based on ID in the url
> GET	             '/posts/:id/edit'	       edit action	         displays edit form based on ID in the url
> PATCH	        '/posts/:id'	                edit action	         edits an existing blog post based on ID in the url
> GET          	   '/posts/:id/update'	 update action	         displays update form blog post based on ID in the url
> PUT	             '/posts/:id'	                  update action	         replaces an existing blog post based on ID in the url
> DELETE	    '/posts/:id/delete'	    delete action	         deletes one blog post based on ID in the url
> ```


 

