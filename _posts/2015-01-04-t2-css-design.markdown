---
layout: post
title:  Class's and IDs - CSS Tips
subtitle: Sharing my <img src="https://twemoji.maxcdn.com/36x36/1f4a1.png"> moment about classes and IDs.
date:   2015-01-04
categories: technical blog
---

![alt text](https://merrilanil.files.wordpress.com/2014/04/curious-minion-icon.png?w=620 "minion")
        
A *Class* and an *id* in an HTML tag are basically pointers or hooks to that tag. Now, the usual understanding is they are both related to the styling of the website; so related to the *css*. When I started using them (just to make them work), I would randomly add a *Class* or an *id* to identify a particular element of my HTML that I plan to style in a particular way. It did work for what I was trying to do, but it didn't do a whole lot a good. So code wise, it was cluttered, a *Class* or an *id* for every little element on the page.  
        

####So how are we to use these hooks!!!
        
I had the same question for a while and an attitude like Mr. Stuart Minion as seen here. Lets clear the air a bit first. These hooks are primarily on the html side. These are to point at particular elements on the page. So css does not care if its a *Class* or an *id*, as long it finds the element to style. In simpler words, *Class's* and *ids* are not just for css.
        
        
A *Class* is used when we want to identify multiple of elements on the page for the same style. Whereas an *id* is used to pin point one unique element on the page.
        

#### Lets look at some examples. 

#### Class Example  

We have a button with type 'submit' or a type 'button' and we would want them both to be blue, we would use a *Class*. There are three different types of declarations for a button having the same *'.btn'* class associated. So they all get styled the same exact way.
        
![Class Example]({{ site.url }}/assets/Class-example.png)

#### ID Example
Now in the same example above, say we had to point out the submit button specifically to style it differently. This way we can make it stand out as a form submission button. An id is added to that button declaration. Also in the css a specific style is added to the id as well for it to stand out.


![ID Example]({{ site.url }}/assets/id-example.png)

#### Conclusions

A class is used for grouping similar things. An id is used for identifying unique things.



*Now here's the 'AHA' moment.*<br>
The id hook being unique, can also be used to direct a user to a particular part of a page. So if an id hook is used in the url, the browser specifically looks for that hook on the page and scrolls to it automatically. I know, cool right!!! <br>
So for example, in this particular blog page I have added an id to the *Class Example* heading that we just scrolled through to get here. So an url like *'http://theidlemonk.github.io/blog/t2-css-design.html#class-example'* will take you to the this page and then scroll to the part of the page that has this id (class-example). <br>[Click here to try it.](#class-example)       
        
      