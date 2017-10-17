---
layout: post
title:      "**Refactoring/Speeding up my Cli gem**""
date:       2017-10-17 17:13:51 -0400
permalink:  refactoring_speeding_up_my_cli_gem
---


I've been working on my cli gem and about done all functionality is there, I just need to speed it up and maybe later improve the look/formatting of the output.But for now this blog post is about speeding up my gem.The purpose of my gem is to show current top movies and coming soon movies and it gives you the option to find out more about the movie.

The problem I ran into my gem was it was taking a little long to load the top ten movies.

<div style="width:100%;height:0;padding-bottom:59%;position:relative;"><iframe src="https://giphy.com/embed/3o7aDcX4cCi5WV9yhi" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/3o7aDcX4cCi5WV9yhi">via GIPHY</a></p>

My solution was to add that loading message.At the time I thought that was the best solution.

<a href="http://tinypic.com?ref=okacl" target="_blank"><img src="http://i63.tinypic.com/okacl.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

The reason the top ten list was taking so long was the depth of my each statment to retrive the infomation and that I had to open and scrape each movie page.

As you can see the "scrape_now_showing" method is populating the a array of "@@all" with instances of show with movies and there attributes.My soultion to speed up my load time was instead of scraping all the movie links for there metascore and about I would not retrieve that info until the user ask for it.

<a href="http://tinypic.com?ref=2iapeg0" target="_blank"><img src="http://i68.tinypic.com/2iapeg0.jpg" border="0" alt="Image and video hosting by TinyPic"></a>

Not only did it speed up my load time but it made my code less messy. I was able to get rid of the ".metascore" and ".about" method and I replaced it ".more_info" method which did both these thing and can be call upon when needed.

<div style="width:100%;height:0;padding-bottom:60%;position:relative;"><iframe src="https://giphy.com/embed/3ov9jPnpyzaHqxsZm8" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/3ov9jPnpyzaHqxsZm8">via GIPHY</a></p>
