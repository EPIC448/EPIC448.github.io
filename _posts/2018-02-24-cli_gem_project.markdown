---
layout: post
title:      "CLI GEM Project."
date:       2018-02-24 13:01:47 +0000
permalink:  cli_gem_project
---



 
The Project was about:
	Command line interface for suits deals using MenWareHoues website.
This CLI will spit out to our user what’s suit are available and on sales indicating price of the items, availability, the name of the item, and it would say, which product will you like to learn more about. 

My process.
I set up the environment of what I want the project to look like using fake data.
Then I created a structure and patterns using bundler to obtain the proper gems with pre-created fill connections. Some of the file permissions we changed allowing us to use them at will.
 Also, in the process of creating the files, the permissions on the files were changed using the chomd +X command. 
    The website I used were Blacklapel and Macys, but I changed them as it was JavaScript heavy sites. Thus, the MenWearHouse site was used instead. 

Then I use the black lapel file in the lab folder as my environment a.k.a. execution point. To create a visible representation of what I want the project to look like, I added some comments and data to the project to get something’s working. Once that was in places, I stub out some representation of the price and item descriptions. Also added the deal file and CLI file with the proper classes to get it working.  Then I added in the scraper elements and codes as needed.

Then, Started the program from where the user would interact with it.  Which was the bin_blacklapel file located in the bin file.  The user would type in suits and should return what suits are accessible to us with the proper information of the suits. 

Conclusion
This project is interesting because we do not have test suites to indicate where our errors are. Thus, for every change made, we had to test our project to make sure it works. I learned a lot in the process especially the importance of git hub and commit often. 



