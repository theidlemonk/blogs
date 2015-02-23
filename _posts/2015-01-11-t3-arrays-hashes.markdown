---
layout: post
title:  Ruby Arrays and Hashes...&iquest;
subtitle: My two cents on Arrays and Hashes in Ruby
date:   2015-01-11
categories: technical blog
---

To put it in simple terms they are both a kind of Lists. An Array contains a list of stuff. A Hash also contains a list of stuff. The way they store the stuff in them is what makes them different.

Lets take an example to see the differences a little more clearly.<br>
Say we have a small media collection (The only 3 physical disks I own now) that we want to add to a list. A game, an audio cd and a movie.

For an array, we would do it like this.
{% highlight ruby %}
media_collection_array = ["God Of War","Pantera - Mouth of War", "Trainspotting"]
[
    [0] "God Of War",
    [1] "Pantera - Mouth of War",
    [2] "Trainspotting"
]
{% endhighlight %}
 So when we declare an array in *irb* called *media_collection_array* with the three disks in it. Ruby stores them in the array *media_collection_array* indexing them starting at zero. We can get the item stored in a particular index location by calling the array and passing the index number to it. So to get my movie I would have to call the array *media_collection_array* and pass in the index 2.
{% highlight ruby %}
media_collection_array[2]
#=> "Trainspotting"
{% endhighlight %}

For an hash, we would do it like this.
         {% highlight ruby %}
media_collection_hash = { "game" => "God Of War", "audio" => "Pantera - Mouth of War", "movie" => "Trainspotting"}
{
    "game" => "God Of War",
    "audio" => "Pantera - Mouth of War",
    "movie" => "Trainspotting"
}
{% endhighlight %}
See how ruby stores the hash *media_collection_hash*. The are actually tagged with the key I provided and the value for it. Another noticeable thing is also the brackets. An array by convention is always the square brackets where as for an hash its the curly. In this case, in order to get my movie, I would have to call the hash with my key "movie" in this case.
{% highlight ruby %}
media_collection_hash["movie"]
#=> "Trainspotting" 
{% endhighlight %}

The difference in them as I see it, they are both lists. Arrays stores them in an *indexed* order. Where as the hashes are stored in a *key,value* pair. But in case of hashes, ruby does want us to provide the key. So in my example i would rather have a hash to store them so I dont have to remember an index number in order to get my movie out. But did you notice something, when we called them to get the movie out, the parameter (index for array or key for hash) passed in was in a square bracket both times. Well, food for thought.
          
