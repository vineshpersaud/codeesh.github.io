---
layout: post
title:  "Scraping With Nokogiri"
date:   2016-08-06 10:07:39 -0400
---



Scraping is a very useful resource to get live up to date information from other website through there HTML information.

The first step is to tell your program what tools it will be requiring 

```
require 'open-uri'

require 'nokogiri'
```

Open URI is a module which is included in ruby which give to acess to live pages as if it is a local file.
To access this files I will be using the Nokogiri gem to phrase the HTML data which we get from open uri.

The first line of code below creates a temp file with the HTML from the url and assigns it to the variable.
The second line of code uses Nokogiri to phrase the HTML files so you can access it using CSS selectors.

```
html = open("https://www.rottentomatoes.com/")
doc = Nokogiri(html)
```

This is a more efficient way of doing the steps above in one line of code using  Nokogiri::HTML constructor.

```
doc = Nokogiri::HTML(open("https://www.rottentomatoes.com/"))
```

To find out what how to grab the information you want to scrap you can right click and inspect to find the the CSS tags to use to grab info.

<a href="http://tinypic.com?ref=344ckkk" target="_blank"><img src="http://i66.tinypic.com/344ckkk.png" border="0" alt="Image and video hosting by TinyPic"></a>

The first line of code Is used to select the current top movies names in theaters on rotten tomatoes and assign them to a variable called movies .

```

movies = doc.css("#Top-Box-Office")[0].css("a")

movies.each {|movie| puts "#{movie.text}"}

```

This is the output I received.

<a href="http://tinypic.com?ref=dm7gd3" target="_blank"><img src="http://i64.tinypic.com/dm7gd3.png" border="0" alt="Image and video hosting by TinyPic"></a>


For more info on how to scrape using nokogiri and using css selectors I recommend the following great reference which I used  -http://ruby.bastardsbook.com/chapters/html-parsing/










