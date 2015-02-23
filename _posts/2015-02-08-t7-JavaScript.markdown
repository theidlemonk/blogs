---
layout: post
title:  Javascript Stuff...
subtitle: Ruby Hashes vs. JavaScript Objects
date:   2015-02-08
categories: technical blog
---

Javascript objects are almost the same as a Ruby hash. I say *'almost'* just because I have just started learning both, so maybe there are possiblities I have not yet come across. But lets see the similarities in both. 

Here is one of the basic ways of defining a java script object.

{% highlight javascript %}
  var vehicle = new Object;     // creating a new object vehicle
  console.log(typeof vehicle);  //--> object
  vehicle["name"] = "Mustang";  // adding property 'name' to the object and assigning value
  console.log(vehicle["name"]); //--> Mustang

{% endhighlight %} 

Lets look at the Ruby side of creating a new Hash.

{% highlight ruby %}
  vehicle = Hash.new          # creating a new hash vehicle
  p vehicle.is_a? Object      #--> true
  vehicle["name"] = "Mustang" # adding a key 'name' to the hash and assigning value
  p vehicle["name"]           #--> "Mustang"

{% endhighlight %}

Lets look at another way of creating a javascript object. This method is probably used more often. Try to see the similarities.

{% highlight javascript %}
  var vehicle = {};             // creating a new object vehicle
  vehicle["name"] = "Mustang";  // adding property 'name' to the object and assigning value
{% endhighlight %}

Lets look at the Ruby side of creating a new Hash in the same way.

{% highlight ruby %}
  vehicle = {}                # creating a new hash vehicle
  vehicle["name"] = "Mustang" # adding a key 'name' to the hash and assigning value

{% endhighlight %}

Other than the *var* in javascript, they look identical. I know; the semicolon as well. They are pretty much the same in syntax too. At this point I think its a fair assumption to say that *Javascript Objects are same as a Hash in Ruby*.       

Lets look at a few more syntatic comparisons between the two languages. This is getting interesting.<br>
Here is a way we can declare a new object in Javascript and assign a property as well. We will look at the Ruby side right after so we can compare.

{% highlight javascript %}
  var vehicle = {
    name: "Mustang",
    make: "Ford"
  };
{% endhighlight %}

Lets look at the Ruby side of it now.

{% highlight ruby %}
  vehicle = {
    name: "Mustang",
    make: "Ford"
  }
{% endhighlight %}

Do you see the difference. I know, interesting huh.<br> Here's is where I think the Javascript side does a little more than a Ruby hash. Defining a behavior/function in the Object. I am not sure if a ruby hash can contain a method. I will have to research on that a bit more. Also, maybe if a ruby hash can hold an object then that would do it too. Anyways lets see the part in javascript I was taking about that I think a ruby hash might not be able to do. Its not that a ruby hash is not capable, but they are totally different things compared here. 

{% highlight javascript %}
  var vehicle = {};
  vehicle.drive = function() {
    return "Vrooom...";
  }
{% endhighlight %}                    