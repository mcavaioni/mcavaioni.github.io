---
layout: post
title: "Mr. Null"
date: 2015-11-08 18:28:43 -0500
comments: true
categories: 
---

Last week Wired magazine had an interesting article, with the title of: "Hello, I’m Mr. Null. My Name Makes Me Invisible to Computers".

<img src="http://imgur.com/nG6basc.png">

Few weeks ago this article would have not attracted my attention, but now that I've been dealing with the exciting world of coding, it totally got my attention and interest!

For "common" people this seems like a silly problem, but knowing a little bit how "NULL" comes into play in programming languages, it appears to be a pitfall taht programmers should take in consideration.
"NULL" is normally used to ensure taht a data field is not empty, so it;s often rejected as an input in a web form.
Simply: 

 if lastname == null then ... 

But if the lastname is really "Null" then it becomes a problem.
Well, most website have a workaround to this, but others loop back to the input screen, telling the user to re-type the last name...

I searched online and found that this problem turns out to be pretty common! and even larger corporations have had issues dealing with this "dilemma".


<img src = "http://imgur.com/Olv0PN8.png" >

<img src = "http://imgur.com/XV0ViZG.png" >

Based on my little experience I found it pretty unrealistic as "null" is quite different from null..being the first one a string.
But apparently the problem exists when it isn't from user input but from a dump of a legacy system sometimes created in the 80's.

Some of those systems just dump text and interpret the string "null" into NULL and transfering those data into a database, causing the above mentioned problem.

