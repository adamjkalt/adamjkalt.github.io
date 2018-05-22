---
layout: post
title:      "The Helpful Nature of Ruby Hashes"
date:       2018-05-22 16:49:57 +0000
permalink:  the_helpful_nature_of_ruby_hashes
---

 
 ![]( http://www.nintendojo.com/wp-content/uploads/2010/09/ducktales-528x360.jpg)
 
 Random note: Lots of Ruby collecting in Ducktales on the NES.
 
When first learning about "organizing" in coding, Arrays were the go to way to get things done.  However, the ability of Hashes to keep things organized and structured definitely becomes helpful when more data is being organized and stored.

Essentially, the Hash allows you to keep track of a greater "array" of information.  See what I did there?

![](https://vignette.wikia.nocookie.net/disney/images/6/69/Scrooge_winking.jpg/revision/latest?cb=20170913042956)

Made up of Key and Value pairs, your hashes help to make for easier to follow code.
 
An Example: ` hash = {"key" => "value", "another_key" => "another value"}`

The data in your hash relates to the hash itself, but instead of just listing items of an array, the Hash allows for better organization and structure.

Let's stick with Ducktales.

![](https://vignette.wikia.nocookie.net/disney/images/a/aa/Ducktales.jpg/revision/latest?cb=20180327080900)

An Array: `ducktales characters = [Scrooge, Donald, Launchpad, Huey, Dewey, Louie, Webbey, Beakley]`

A Hash (just listing two items here, although could easily list more):

```
ducktales characters = {
  "Scrooge McDuck" => {
    name: "Scrooge",
    voiced by: "Alan Young", 
		NES game appearance: "yes"
    
  },
  "Launchpag McQuack" => {
    name: "Launchpad",
    voiced by: "Terry McGovern",
		NES game appearance: "yes"
  }
}
```


So, as you can see, with the Hash, instead of just listing characters, we can list the characters, the shortened name, and any other data we want to.  Arrays are obviously helpful in coding, but our Hashes just allow for more depth and structured when needed.
 
 
 


