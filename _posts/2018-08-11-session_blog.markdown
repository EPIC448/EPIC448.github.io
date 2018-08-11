---
layout: post
title:      "SESSION BLOG"
date:       2018-08-11 07:13:12 +0000
permalink:  session_blog
---


Session is an object like hash that stores data describing a clients interaction with a website as a given point in time. It stores information such as users id, which the web application uses to identify who the user of the web application is.


What are we doing when we set a session scoped variable?  & Why is it useful? 

   When you log in or sign-up into a website, you have started a duration od a session. Simply put, the period of time in which you, the client, are interacting with the web application. This is usually the time in between logging in and logging out.

 Since all web page treats a user like a new visitor whenever they submit a request, session cookies allow the website to track your movement from one page to the next so your don’t have to re-enter the same information multiple times.    Without it every time you open a new web page the server where that page is stored will treat you like a completely new visitor that means you have log in every time you move to an-other page


 For instance:


post '/signup' do
      if params[:name] == "" || params[:email] == "" || params[:password] == ""
        redirect to '/signup'
      else
        @user = User.new(:name => params[:name], :email => params[:email], :password => params[:password])
        @user.save
        session[:user_id] = @user.id 
        #tells us who is using the session...
        redirect to '/apartments'
      end
    end
  

This is a great example of how sessions are used in the highlighted code above


 Recap
A session is a hash that lives in your application in the server. The session hash can be accessed in any controller file of your application. 
 We love session because it prevent use from repeatedly logging into our website when we change pages.


