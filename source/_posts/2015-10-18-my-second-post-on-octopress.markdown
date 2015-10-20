---
layout: post
title: "Going to the web!"
date: 2015-10-18 15:05:00 -0400
comments: true
categories: 
---

So we wrote our awesome app in Ruby! It does all the things we need: generates data, access that data and spits out a response.
We also have it written in the MVC schema, where we have:
- the router: which "manages" the specific resources and send us to 
- the controllers: which "take care" of all the actions and have 
- the models: which "perform" the tasks/methods that they are entitled for.
- the views: which "display" any "form" to the user.

That sounds great but how do I get this great application visible to the public???
I want other users to access it!
Oh, great there is this thing called "internet" that should do the trick!
...yeah but how..???
How can my application receive a request and send a response?
Let's see how my application interacts with the World Wide Web...

Here below is an over-simplified flow:

<!-- <img class="center" src="http://imgur.com/LjY6U7a"> -->
{% img center ./images/flow.png  %}


When the user sends a request to the server, this comes in the form of a string with several data (such as the get request, URL, user info,..).
All these data are "transformed" by rack in the form af a hash which can then be sent to our router.
Here the flow between the router, controllers and views is the typical MVC flow. What changes is now the view which need to display the response in an html form.
That's when ERB comes to help.
ERB is a templating system written in Ruby.
ERB takes a templating string and some configuration options.

i.e.

string = File.read ("app/views/template.html.erb")

Where the file "template.html.erb" is our view "form" where the pattern that gets evaluated by ERB is written within <% %> or <%= %> where in addition to evluate this, ERB also displays it.

When the "result" method is eventually called on the ERB object then all the lines of code containing the specific pattern mentioned above get evaluated with a given "binding".
"Binding" includes all the Ruby local variables. It basically points to all the local variables that are in my scope.

i.e.

template = ERB.new (string)
output = template.result(binding)

Finally the response that is sent to the server gets "transformed" into the form af an array, which contains 3 information:

1- the response code: basically a code that machines use to communicate with eachother (i.e. 200 = everything is ok; 400= there is a problem from the client side; 500= there is a problem from the application side)

2- the header: the content type, explaining how the body shall be interpreted (i.e. JSON, html, text,..)

3- the body: the response!

i.e.

[200, {"Content-type" => "text/html"}, ["Hello World!!!"]]









