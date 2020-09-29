---
title: "What is BitTorrent?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg
  
---

Torrenting, although somewhat of an old concept, is still very much relevant today. Often it is brought up in terms of illegal activity where you might torrent a new movie, video game or piece of softwware. While this can be true, the workings behind torrenting and how it functions are largely left unnocticed to the end user. In this article, I'll attempt to explain what torrenting is and how it affects cyber security.

### The Shortest Distance Between Two Points Is...

Let's talk about the most common way devices connect over the internet: the **client-server model**. This may sound very familiar if you read my [VPN](https://freshprinceofhacking.github.io/what%20the%20hack/What-Is-A-VPN/) article. To recap, essentially the way that we are used to seeing our devices connect to websites on the internet is through this method. The client machine(our device) connects to a server, which hosts the content we want to see. Very simple. 

![Csmodel]({{ site.url }}{{ site.baseurl }}/assets/images/csmodel.jpg)

This means that when we are also downloading content, we follow this same model. But let's think about this for a bit. Imagine if we wanted to download a file from a popular website. We would need to A) connect to the website and then B) request the download from the server it's hosted on. This works normally, except that this particular day the website is experiencing some slow down due to the high volume of traffic going to it. We're still able to request a download for the file, but it's taking forever. What could be happening is that the server is experiencing overload, and it is bottlenecking your request for the download, which causes the slow speed. Even though we have a direct download from the website itself, this looks to be the slowest way possible to get the file. I'm sure we've all been in this situation. It would help if there was an alternative way to download the file...

### Put A Ring On It

It turns out we're in luck! We notice that the site is also hosting a torrent of the file. All we have to do is download the torrent, fire up our old torrenting software, and BAM we have the 50gb file in only 1 hour. 
