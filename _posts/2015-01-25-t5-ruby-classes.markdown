---
layout: post
title:  Classes and Objects
subtitle: Are classes objects?
date:   2015-01-25
categories: technical blog
---

A class is like a blueprint of a process or a thing. It contains the shell of the properties and behaviors of the process or the thing for the class. So a class is a way of grouping properties and behaviors of an object. 

For example, lets say we have an object 'Dog' whose properties and behaviors we want to group. One of the properties of our object 'Dog' is its color; 'Black'. Another one could be its breed; 'Labrador'. A behavior of this object 'Dog' is that it barks. This is one of those scenarios we would consider writing a class. 

Classes can contain just behaviors or just properties of an object as well. For example, if we are considering an object 'Faucet'. In this case all we need is the behavior; when 'turned on' and 'turned off'. This is another good scenario for making a class. 

If you look at the two examples above, its always good to write a class when grouping things together. Things or better known objects. Lets take our first example. The Dog object. Lets write a class for the object dog, so we can inherit from it for defining any type of dog, or just instantiate it as a specific dog. Our dog object would look like this.

{% highlight ruby %}
class Dog
  attr_accessor :color, :breed
    
  def speak
    puts 'The ' + @color + ' ' +@breed + ' says - Woof Woof !'
  end
    
end
{% endhighlight %}

The object dog has the properties color and breed which we can set and it has a behaviour 'speak'. Lets create a dog.

{% highlight ruby %}
new_dog = Dog.new
new_dog.breed = "Husky"
new_dog.color = "white"
new_dog.speak

#=> The white Husky says - Woof Woof !

{% endhighlight %}

Classes or obects can also be inherited. Inheritance lets us take every propery and behaviour from the inherited class and we can add our own to this new one as well. For example, if I had to create one for 'Underdog', who can fly. I would want to add a fly behaviour to this.

{% highlight ruby %}
Class UnderDog < Dog

  def speak
    puts 'i am UnderDog'
  end

  def fly
    puts 'Whoooosh....!'
  end

end

{% endhighlight %}

In this case, I can instantiate underdog, and make it do the new overrides to the dog methods.  

{% highlight ruby %}
super_hero_dog = UnderDog.new
super_hero_dog.speak
super_hero_dog.fly

#=> I am UnderDog
#=> Whoooosh....!
{% endhighlight %}
