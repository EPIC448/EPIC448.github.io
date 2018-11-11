---
layout: post
title:      "Rails Nested Resources"
date:       2018-11-10 23:04:16 -0500
permalink:  rails_nested_resources
---


Nested Resources…
 (For The contest of the this blog. Any blog has an Author, Post, and Comments.)
(For better simplification:
 Author has many Posts  
Posts belong to one Author
Posts has many Comments)



A.	Why should we care for nested routes?
 Well, going based on the example listed above, Let say we want gains access to be able to access Post of a specific author, Normally this is done through /authors/:id/ and the URL version of it will be 
[http://localhost:3000/posts?utf8=%E2%9C%93&author=1&date=&commit=Filter]

⇨	what we want instead is  in the config/routes.rb

⇨	get 'authors/:id/posts'=> Target the posts of a specific author

⇨	get 'authors/:id/posts/:post_id' #target specific post by that the said author.


B.	Creating a nested routes
Then, How do we handle the routes above so we go into the Author controller.
  app/controller/author_controller
1.	def posts_index

2.	@author = Author.find(params[:id]) # find the  author

3.	@posts = @author.posts # find the authors post.
4.	render template: 'posts/index'
5.	end
6.	 
7.	def post
8.	@author = Author.find(params[:id])
9.	 
10.	# Note that because ids are unique by table we can go directly to
11.	# Post.find — no need for @author.posts.find...
12.	@post = Post.find(params[:post_id])
13.	render template: 'posts/show'
14.	
15.	end
16.	
Notes: Normally, A controller action would normally implicitly render a template with the same name as the method, in this case we want to leverage the templates we're already using for posts, so we call render explicitly with a template path. Because we're telling render that we're using a template [‘posts/show’ & ‘posts/index’], we don't need to include the .html.erb extensions. Rails do this for us…


Note: If your IDs are different and you are having trouble with the URLs, try running rake db:reset to reset your IDs to the defaults in the seed file.

C.	Understand The naming of nested resource URL helpers are named

  As you can imagine. How code is not following the DRY principle,
 Following our code, we can conclude that a Post is a child of an Author… thus,
has_many :posts
belongs_to :author

 Thus, Nested Resources allow for the documentation of that parent/child relationship in the routes and ultimately URLs.

 Then in the routes.rb we have

1.	 # config/routes.rb
2.	 
3.	Rails.application.routes.draw do
4.	 
5.	resources :authors, only: [:show] do
6.	# nested resource for posts
7.	resources :posts, only: [:show, :index]
##We can still do things to the nested resources that we do to a non-nested resource, like limit them to only certain actions. In this case, we only want to nest :show and :index under :authors.
8.	end
9.	 
10.	resources :posts, only: [:index, :show, :new, :create, :edit, :update]…   We added this because we still want people to be able to see all posts, create and edit posts outside the context of the author.
11.	root 'posts#index'
12.	end
13.	
Note: previously, we made  the adjustment in the author controller, but because we are shooting for the Post of a certain Authors, So to  accommodate for the revamped code, we alter the app/posts_controller to handle the nested resources instead.

1.	# app/controllers/posts_controller.rb
2.	 
3.	  def index
4.	    if params[:author_id] 
5.	      @posts =     Author.find(params[:author_id]).posts
6.	    else
7.	      @posts = Post.all
8.	    end


#We added a conditional to the posts#index action to account for whether the user is trying to access the index of all posts (Post.all) or just the index of all posts by a certain author (Author.find(params[:author_id]).posts). 
 we checked to see if the hash has an :author_id key, then perform the following code else show all the post.

Simply, whether the user navigated to /authors/:id/posts or simply /posts. We didn't have to create any new methods or make explicit calls to render new templates. We just added a simple check for params[:author_id], and we're good to go.###

9.	  end
10.	 
11.	  def show
12.	    @post = Post.find(params[:id])
13.	  end

Rails take the parent resource's name and appends _id to it for a nice, predictable way to find the parent resource's ID.

The goal of nesting our resources is to DRY up our code. We had to create a conditional for the posts#index action because it renders different sets of posts depending on the path, /authors/:id/posts or /posts. Conversely, the posts#show route is going to render the same information — data concerning a single post — regardless of whether it is accessed via /authors/:id/posts/:id or /posts/:id.



1.	# app/controllers/authors_controller.rb
2.	 
3.	class AuthorsController < ApplicationController
4.	 
5.	def show
6.	@author = Author.find(params[:id])
7.	end
8.	 
9.	end

 So How Do we connect that to our views to find a link to an authors post?

We know the URL is /authors/:author_id/posts, so we can combine the two conventions and use author_posts(author_id). Remember it's the singular author because we are getting one by id.
It stands to reason that a single post for an author would combine the conventions for the single author path and single post path, leaving us with author_post(author_id, post_id)


 Adding a _path or _URL to any of the name under “Prefix”. You’ll give the helper for that route.

   rake routes | grep authors

With that, we can say, 

1.	<!-- app/views/posts/index.html.erb -->
2.	 
3.	<h2><%= post.title %></h2>
4.	 
5.	<!-- change the name to a link -->
6.	<h3>by: <%= link_to post.author.name, author_posts_path(post.author) %></h3> # give a specific authors post
7.	<p><%= post.description %></p>
8.	

This allow the URL to read like book.   author/1/posts = “author number one’s posts”.

*Clear out the confusion:*
Not sure about  path helpers and what they take as arguments.
posts_path => Takes no argument because it refers to all of the posts
post_path(@post) => Takes argument because it referring to a specific post  [ posts/1 as opposed to posts/2.]


Highly recommended!!
 Never nest a route more than 1 level deep
 
 Discliamer: Much more details is available in the Flaitron curriculum, This is a simple mental break down of my understanding of the topic.
 
 
 Now Money dance!!!!
[Money dance](https://i.gifer.com/UcoS.gif)
 
  Cheers 
	
	sam

