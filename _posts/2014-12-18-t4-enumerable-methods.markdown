---
layout: post
title:  "Enumerable#cycle"
subtitle: "Enumerable#cycle...WHAT?"
date:   2014-12-18
categories: technical blog
---
        
Before we begin to understand *'Enumerable#cycle'*, lets talk about *Enumerable* first. As per the [definition](http://www.oxforddictionaries.com/us/definition/american_english/enumerable?searchDictCode=all) of the word *Enumerable* is *'Able to be counted by one-to-one correspondence with the set of all positive integers.'* Thats a Mathematics definition, what does it mean in Ruby! Well, the idea is the same. But in programming we deals with integers and strings. So in Ruby, we would define an *Enumerable* as *'Able to be counted by one-to-one correspondence with a set/List/Collection'*.
        
        
Lets take an example of the frequently used *#each* enumerator from ruby enumerables. The *Enumerable#each* lets us enumerate though a list of array/hash collection and performs a task that is passed in the block for each element in the collection. As this is an enumerator, it conceptually behaves the same way for any collection (array or a hash). 
        
        
Now that we have an idea of *Enumerables* in ruby, lets see what the *Enumerable#cycle* does. Keeping in reference to the *Enumerable#each*, this enumerator *#cycle* almost behaves the same way. Only in this case, it does not stop after it enumerates through the collection unless specified. The *Enumerable#cycle* when called on a collection, it enumerates through the collection *n* times. Here *n* is a parameter passed in when the *#cycle* enumerator is called. So when n is blank or not passed, the collection is enumerated though infinitely.
        
        
In simple terms we can say, *Enumerable#cycle* cycles though a collection *n* times. lets see an example.

{% highlight ruby %}
my_collection = ["I", "Love", "Pizza"]
[
    [0] "I",
    [1] "Love",
    [2] "Pizza"
]

my_collection.cycle { |x| print x}
#=> ILovePizzaILovePizzaILovePizzaILovePizzaILovePizzaILovePizza ... ∞ ... (infinitely)

my_collection.cycle(3) { |x| print x}
#=> ILovePizzaILovePizzaILovePizzanil
{% endhighlight %}
        
In the example above, the first time I call cycle on my_collection without a parameter, it keeps printing till I hit the break/^C.<br>Whereas, when I pass the parameter (3) to the enumerator cycle, it prints it 3 times and quits.

        