---
layout: post
title: "Embedded Resources not so painful anymore."
date: 2006-07-21 20:29:00 -0400
comments: true
published: true
categories: ["Archive"]
tags: ["Blog"]
permalink: "/post/Embedded-Resources-not-so-painful-anymore/"
---
<!-- more -->



<p>&nbsp;&nbsp;&nbsp; Well after a frustrating time trying to figure out how to make embedded resources work, I finally understand. This makes everything much easier. As some of you may know I have been working on a content management tool. (This is not a full blown content management system) Since it is designed to be portable to existing ASP.NET web sites, it is just a dll file. Even though it uses a couple of images, I don&rsquo;t want anyone to have to copy image files just to get the app working correctly.</p>
<p>&nbsp;&nbsp;&nbsp; To accomplish this I decided to use embedded resources, something I had never done before. Starting out I fumbled a lot trying to figure out how to display these, bad idea. Well I started googling for a solution to my problem, and I tried doing what Microsoft said to do. Following what they said to do got me nowhere, and left me a bit more confused. The site makes many assumptions about what I all ready know. Since I did not know these things, I took some guesses. Sadly incorrect ones. I think the authors of those resources need to learn the value of a hyperlink. It would allow them to reference old material so I could <em>learn</em> what they assume I know.</p>
<p>&nbsp;&nbsp;&nbsp; After reading that I had a better reference to start googling. I started looking for the GetWebResourceUrl method, and this led me to other web sites, which had some better explainations. At first I went to an article on codeproject explaining how to access embedded image resources. This was much better than the previous one I read, but I still could not get this one working right. My example didn&rsquo;t quite fit with what they did, and they didn&rsquo;t explain each part of the process.The problem is that even&nbsp;if I had incorrect code in my file, GetWebResourceUrl still returned a url that <em>looked</em> like it was supposed to. Again I needed to find something to get this working, or I would have to go back and start writing a lot of code I did not want to write.</p>
<p>&nbsp;&nbsp;&nbsp; So I tried another link I found on google, and this article on <a href="http://aspalliance.com/726">Embedding Resources in ASP.NET 2.0 Assemblies</a> explained to me&nbsp;very well how to get my embedded resources working. It explicitly told me where each part of code belonged It mentioned some specifics I might need that were not even part of that example. Not only that but it had more than one type of embedded resource that it accessed. If you are ever trying to use embedded resources I recommend it, but I suggest reading this <a href="http://aspalliance.com/726">article</a>&nbsp;first. I may have to start reading more articled written by Mark Hines. If you are interested in this topic,&nbsp;I suggest reading this article&nbsp;as well&nbsp;<a href="http://aspalliance.com/850">Embedding Resources in ASP.NET 2.0 Assemblies - Part 2</a>.</p>
