---
layout: post
title: "Everything is an object - Array method REPLACE. "
date: 2015-10-04 13:14:41 -0400
comments: true
categories: "Flatiron&nbsp;School"
---
One of the first things you learn when dealing with Ruby is that everything is an object. 
(well, except for: def, if, end ).

This seems like a simple concept, but it hides a very important meaning that sometimes we forget when doing a simple operation.
Let's take for example on methods we can use on an array: REPLACE.
Replace, as the word implies, replace the content of an array with the content of another one.
Let's visualize this one in our CLI.

Let's create a new array:

>   a = ["cat", "dog", "mouse"]

=>  ["cat", "dog", "mouse"]

So, now if we want to see what "a" is we type "as" in our terminal we get the following:

>   a

=>  ["cat", "dog", "mouse"]

Let's now create another array which is equal to our original one, so:

>   b = a

=>  ["cat", "dog", "mouse"]

As we can see "b" got assigned to same object of our original array "a".

What happens if we now apply our method "REPLACE" to our array "a" ? and what happens to "b"?

>   a.replace([1,2,3])

=>  [1,2,3]

>   a

=>  [1,2,3]

>   b

=>  [1,2,3]

Cool. Yes that easy. I just replaced the content of "a" and since "b" is pointing to the same object, also his content has changed.

But what happens when I reassign "a"?

>   a = ["I", "am", "another", "object"]

=>  ["I", "am", "another", "object"]

>   a

=>  ["I", "am", "another", "object"]

Is "b" going to change? Remember, everything is an object in Ruby!
Let's see:

>   b

=>  [1,2,3]

At first I got confused, but then I went back to my terminal and looked at the "object_id" of my objects as I was creating them.
Let's do it again.

>   a = ["cat", "dog", "mouse"]

=>  ["cat", "dog", "mouse"]

>   a.object_id

=>  70312125383000 


>   b = a

=>  ["cat", "dog", "mouse"]

=>  b.object_id

=>  70312125383000

"a" and "b" are pointing to the same object (which is an array and it happens to have ID= 70312125383000; the content of this object is ["cat", "dog", "mouse"]).
When I use the method "REPLACE" on "a" I just happen to change the content of the object. Just that. 
So when I assign a variable (in this case "a") to an object I basically point this variable to a bucket (that has the "shape" of an array) which contains a bag (inside this bag I put a "cat", a "dog", a "mouse").

When I apply my method "REPLACE" I basically just replace the bag inside my bucket array with another content (now containing the numbers 1,2,3). But the bucket itself does not change. Infact it's ID is still the same. Let's see:

>   a.replace([1,2,3])

=>  [1,2,3]


>   a

=>  [1,2,3]

>   a.object_id

=>  70312125383000 


>   b

=>  [1,2,3]

>   b.object_id

=>  70312125383000 

Now, instead, when I reassign "a" to another array I basically point "a" to another object, still an object array, with another bag inside which contains "I", "am", "another", "object".
This is now a totally different object. In fact if we look in terminal the object ID associated to this array object is different!

>   a = ["I", "am", "another", "object"]

=>  ["I", "am", "another", "object"]

>   a.object_id

=>  70312117660040 

What happens to b? b is still pointing to the previous object array. It's content hasn't changed. 
In fact:

>   b.object_id

=>  70312125383000 

Which is the same as before!


To recap, everything is an object! an object is like a bucket identified by it's ID and it contains a bag. Inside a bag I can add, remove, replace content.
When I assign a variable I point that variable to an object. If another variable is equal to the first one created, then I assign it to the same object.
The method "REPLACE" change only the content of my object (the bag inside the bucket) and doesn't affect the binding between the two variables.
When I, instead, reassign the initial variable to another object I basically remove the binding between the two variables and now they are pointing to two completely different object.

