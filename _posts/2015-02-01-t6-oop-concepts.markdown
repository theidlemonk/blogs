---
layout: post
title:  (OOP) Classes vs Modules
subtitle: OOP with Classes and Modules
date:   2015-02-01
categories: technical blog
---

Object Oriented Programming (OOP) is like building your own matrix. Just like 'The Architect' in the Matrix, who created this virtual world called 'The Matrix' with code. It was a replica of the real world but was not the real world. It did behave like the real world as well. But it had its own little tricks.  

Lets try to understand OOP by understanding the Architects way of programming The Matrix. The way he build it, all of the people in the matrix were instances of the person class. The animals and vehicles in the matrix were instances of their own parent classes. I hope I still got your attention so far. Lets move on. So this is the concept of object-oriented programming. We define objects/classes, depicting real world objects. Now we can define a specific thing which is an instance of the object/class we created.

Lets take an example and look at some code to see how this works. Say we want to create our own matrix. But this one is just a little animal shed. In this Matrix shed we have 3 different types of animals; dogs, sheep and bunnies. We start with creating an animal object from which these animals with inherit or be instances of. Here is our animal class.

{% highlight ruby %}
class Animal

  attr_accessor :legs, :type, :color, :diet

  def initialize(color)
    @legs = 4
    @color = color
  end

end
{% endhighlight %}

Lets create a dog, a bunny and a sheep inheriting from <em>Animal</em>.

{% highlight ruby %}
class Dog < Animal

  def initialize(color)
    super
    @type = 'dog'
    @diet = 'omnivore'
  end

end

class Bunny < Animal

  def initialize(color)
    super
    @type = 'bunny'
    @diet = 'herbivore'
  end

end

class Sheep < Animal

  def initialize(color)
    super
    @type = 'sheep'
    @diet = 'herbivore'
  end

end

{% endhighlight %}         

When we create instances of these animals this is what we get.

{% highlight ruby %}
dog = Dog.new('grey')
p dog.legs #=> 4
p dog.diet #=> "omnivore"
p dog.color #=> "grey"
p dog.type #=> "dog"

bunny = Bunny.new('white')
p bunny.legs #=> 4
p bunny.diet #=> "herbivore"
p bunny.color #=> "white"
p bunny.type #=> "bunny"

sheep = Sheep.new('black')
p sheep.diet #=> "herbivore"
p sheep.color #=> "black"
p sheep.type #=> "sheep"                     

{% endhighlight %}          

This is what classes are in OOP. Lets get into Modules now. Modules are more like libraries, or better described as a snippet of code that can be reused across multiple classes. A module is does not really fall into the OOP concept, but its a nice thing to have in ruby that lets you choose your design pattern. Think like a configuration item that we want a class to have if needed. Also, having it as a module, it lets us change the configuration at one place without affecting the class itself.

Say our Matrix animal shed is in springfield, right next to Mr. Burns nuclear plant. So because of the location and how the bunnies and sheep run around the yard and drink from the plant waste; they turn radioactive vampires. Here we can create a module for exactly that and let sheep and bunny use it.

{% highlight ruby %}
module RadioActive

  def mutation
    puts 'Im radio active vampire ...Grrrr'
  end

end              
{% endhighlight %}         

This module will be included for <em>Sheep</em> and <em>Bunny</em> classes as follow:

{% highlight ruby %}
class Bunny < Animal

  include RadioActive

  def initialize(color)
    super
    @type = 'bunny'
    @diet = 'herbivore'
  end

end

class Sheep < Animal

  include RadioActive

  def initialize(color)
    super
    @type = 'sheep'
    @diet = 'herbivore'
  end

end            
{% endhighlight %}          

Lets see what we get when we create the instance of these two possible radioactive animals.

{% highlight ruby %}       
bunny = Bunny.new('white')
p bunny.mutation #=> Im radio active vampire ...Grrrr
p bunny.type #=> "bunny"

sheep = Sheep.new('black')
p sheep.mutation #=> Im radio active vampire ...Grrrr
p sheep.type #=> "sheep"        
{% endhighlight %}  
