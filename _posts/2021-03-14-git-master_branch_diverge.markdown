---
layout: post
title:      "Git-Master Branch "DIVERGE""
date:       2021-03-15 02:21:46 +0000
permalink:  git-master_branch_diverge
---


 
As I worked on a project I was looking to submit for an application, my computer terminal keep return to me the following. 

*'master branch and 'origin/master' have diverged, how to 'undiverge' branches'*


![](https://poanchen.github.io/img/2020/09/19/what-to-do-when-git-branch-has-diverged/branch%20diverged.JPG)


Which i have to tell you was annoying as hell. So after Hours of debugging, Here are what is important and learned. 

When you get a message such as "

 ** "Your branch and 'origin/master' have diverged, # and have 12 and 3 different commit(s) each, respectively."**
 
###  What is going on here?

This happens when you are trying to merge your changes to ‘origin/master’ and someone else on your team pushed some other changes after you sync with ‘origin/master’ and before you merge your changes. This can also occur if you worked two difference branches (branched G and Q)referring to the same project. 

```

o----------o ------f-------origin/master(upstream work)
                 /  \
		         G   Q  (Updated branches)
```
																		

 Assume you updated Branch G, then Q. but you push branch Q to the origin before G, it will work, then issue is when you attempt to push branch G now, you will get the error mentioned above. 

```
 o----------o ------f-----Q--origin/master(upstream work)
                   /  
			      G     (Updated branches)
	```
 
 This will give a similar error. 
 

### View the differences? (using a different example)

Using command

`git log HEAD..origin/master`

```
o ---- o ---- A ---- B origin/master (upstream work) 
               \ 
                C master (your work)
```

Your based commit C on commit A because that was the latest work you had fetched from upstream at the time.
However, before you tried to push back to origin, someone else pushed commit B.
Development history has diverged into separate paths.



### Several steps to take to solve this issue.

 
 **Merge**
 
  Using command
	
	` git merge origin/master`
 
 This tells Git to integrate the changes from origin/master into your work and create a merge commit.

The graph of history now looks like this:

```
 ... o ---- o ---- A ---- B origin/master (upstream work) 
                   \       \ 
                    C ---- M master (your work)
```

 The new merge, commit M, has two parents, each representing one path of development that led to the content stored in that commit, keep in mind that the history behind M is now non-linear.

**Advantages**:  Easier and quicker to resolve conflicts.

**Disadvantages**:  Non-linear git history.


**Rebase**

Using command

 `  git rebase origin/master`

This tells git to replay commit C (your work) as if you had based it on commit B instead of A.
 
Concurrent Versions System (CVS) and Subversion users routinely rebase their local changes on top of upstream work when they update before commit.
Git just adds explicit separation between the commit and rebase steps.
 
The graph of history now looks like this:

```
... o ---- o ---- A ---- B origin/master (upstream work) 
                          \ 
                           C' master (your work


```

Commit C' is a new commit created by the git rebase command.
 
It is different from C in two ways:

It has a different history:  B instead of A.
Its content accounts for changes in both B and C; it is the same as M from the merge example.

Hint:  that the history behind C' is still linear.
 
We have chosen (for now) to allow only linear history in cmake.org. Can visit [cmake.org](https://cmake.org/) for details.
 
This approach preserves the CVS-based workflow used previously and may ease the transition. An attempt to push C' into our repository will work (assuming you have permissions and no one has pushed while you were rebasing).
The git pull command provides a shorthand way to fetch from origin and rebase local work on it:

Run the command

`git pull --rebase`

**Advantages**: More clean/linear git history that would help people to find what caused the regression quicker and easier if any.

**Disadvantages**: Merge conflict may become more frequent with possibilities of losing your commit history if done wrong.

**Rule of thumb**: Frequently rebase your feature branch to make the process of resolving conflict easier in the future.
