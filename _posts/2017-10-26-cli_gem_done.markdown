---
layout: post
title:      "CLI Gem done"
date:       2017-10-26 14:49:37 -0400
permalink:  cli_gem_done
---

<h6>Getting started</h6>
 This was the first program or code that I would be writing myself and the hardest part seemed like it just figuring out how to get started. Looking at a blank text editor finding out where do I start was a bit of a challenge.But after watching a few cli gem walkthroughs reading some documentation helped prepared.Looking back I feel that I should have prepared a little less and learned while doing which seems like the best way for me, lesson learned I guess.

<h6> What is my gem and what it does it do? </h6>

So  "Now Showing "  is a CLI gem that is able to look up a movie in theaters and give you a list of this weeks top ten movies and movies which are opening this week.Once you are able to pull up the list of movies you can find out more about each of these by selecting a movie. The info which you will receive is name , metascore, a little about the movie.

<a href="http://tinypic.com?ref=eb21d3" target="_blank"><img src="http://i66.tinypic.com/eb21d3.jpg" border="0" alt="code"></a>


<h6> How does the gem work</h6>

All the data from the gem is received by scraping imdb.com using nokogiri.I have created two class methods one for the top ten movies another for movies opening this week each of these is scraped from a different web page. Each of these methods are very similar but require different attributes as opening movies don't yet have earnings.  

<a href="http://tinypic.com?ref=15u6wz" target="_blank"><img src="http://i65.tinypic.com/15u6wz.jpg" border="0" alt="opening code"></a>

Here is the process of the code when user ask for opening movies.

1. NowShowing::Opening.scrape is called 
2. Nokogiri parses the website
3. Iterate over each movie and grab the name, about, and metascore and initialize an opening and add it to the array @@all.
4. Than I iterate over that NowShowing::Opening.all i created and output the info.

<h6>

<h6>Lessons learned</h6>
By building this gem I gained some confidence that I am able to make something and I learned a lot and I have much more to learn.On the technical side, I learned that one way to make my program run faster and more efficient is to have it only run a process when its needed instead of doing everything at once to find out more about I mean you can read my blog post on refactoring my code at the link below.

Speeding up CLI Gem - http://codeesh.github.io/refactoring_speeding_up_my_cli_gem

My Gem - https://rubygems.org/gems/now_showing

Git Repo - https://github.com/codeesh/now-showing-cli-app




