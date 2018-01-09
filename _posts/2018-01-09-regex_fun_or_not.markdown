---
layout: post
title:      "Regex .... Fun or Not!"
date:       2018-01-09 20:14:39 +0000
permalink:  regex_fun_or_not
---


The content of your blog post goes here.

Regex. Short for regular expression, a regex is a string of text that allows you to create patterns that help match, locate, and manage text. Put another way,   Regex is the configuration of characters or search patterns (i.e, /, : ,"' ", {},[],)  to filter out what you would like to see in  an email . Languages such as pearl, ruby, javascriopt uses regex. 


As first it was a challenge, but once you undersand the purpose of each character, you can chain them together to get a certain search pattern. It also can be used in editing work or search an replace tools. For Example :/ \b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b/.  note that each character means something in this process.

Most used Regex Characters

Character classes
.	any character except newline
\w \d \s	word, digit, whitespace
\W \D \S	not word, digit, whitespace
[abc]	any of a, b, or c
[^abc]	not a, b, or c
[a-g]	character between a & g


Anchors
^abc$	   start / end of the string
\b \B	    word, not-word boundary



Escaped characters
\. \* \\	   escaped special characters
\t \n \r	   tab, linefeed, carriage return
\u00A9	unicode escaped ©


Groups & Lookaround
(abc)	   capture group
\1       	backreference to group #1
(?:abc)	  non-capturing group
(?=abc)	 positive lookahead
(?!abc)	  negative lookahead


Quantifiers & Alternation
a* a+ a?   	0 or more, 1 or more, 0 or 1
a{5} a{2,}	 exactly five, two or more
a{1,3}	        between one & three
a+? a{2,}?	 match as few as possible
ab|cd	          match ab or cd





