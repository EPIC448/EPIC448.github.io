---
layout: post
title:      "'SCRAPPING that HTML ... You Bet!!!. '"
date:       2018-02-04 02:23:33 +0000
permalink:  scrapping_that_html_you_bet
---


	    In the kickstarter Scraping Lab, I used scraping to scrap a website that contain projects in New York  city area collecting  information for each project and build a hash for the project. 
			
***			
Wait !!!  What in the World is Scrapping???.... Chill out Lisa, let me explain.. *


    Think of it like opening you old cabinet filled with files, then picking out certain folder that has important documents in them such as the paperwork for your taxes, the documents for the house your live, your year book and even old pick picture to show to the grand kids.   Scraping is used to "scrap" data from the web that is later used to instantiate or create your Ruby project. 
	 
	
	The step I followed included: 
	
	   1: require Nokogiri at the top of the documents and set up the variable inside the method.
		 
		 2:  Discover a selector that allows use to collect the project file entirety.  [Hint: Every Project has other small Project within it]
		 
		 3: Open up the site and use the "Inspect Element" to find what information’s your looking for. For instance, if your using Google Chromes "inspect element" you click the arrow to the left of the bar. As you navigate through the site, You will notice certain codes are highlighted indicating the code that corresponds to your cursor.
		 
		4: Then I used binding  'pry' to find the necessary information about a project such as locations, cost, funding, durations, and company  thanks to the power of Nokogiri. [Note: Nokogiri, well return a bunch of nested nodes that return to the same methods of which we add CSS to it. 
		
		5:  We start to collect and store our working code in the project file. As we play around in the "Inspect Element", we come upon a CSS selector that we try in pry and if it works we store it
		
	6: We set up a loop to iterate over through the projects and create an empty projects hash that encapsulate our code. Then, we want to turn our titles into strings in the process as well.
	
	7: In conclusion, we grab each of the data points using the selectors we've already figured out and add them to each projects hash.
			
			
			
			
	
	
	 
	

