---
title: "Google Hacking"
categories:
  - Hacking
---

What if I told you that you've been searching on google the wrong way all this time? Ok, maybe not the wrong way, but what if I told you that you can significantly enhance your google searches with just a few changes in your search queries, and a little bit of creativity? That sounds like a reasonable skill to have, and it's actually something that is easier than you'd think. In this article I'm going to go over google "hacking" and how you can use it to enhance your searches, as well as the implications it has on cyber security.

### You're such a Dork

It's no secret that google is one of the largest and most popular search engines in the world. People rely on google every second to find resources related to their search queries. What other search engine can find you the best cat memes or best places to download $100+ textbooks for free? If you've read my [dark web](https://freshprinceofhacking.github.io/what%20the%20hack/What-Is-The-Dark-Web/) article, you'll remember that google and every other search engine are just indexing the various pages it finds, and organizes them for us to view. I hinted at the notion of how much information is actually indexed on the web for us to be able to simply search for. Hmm...this could be very valuable for hackers, but how?

Let's think about this. If google simply indexes all of the information it can find, surely some of that information is sensitive, right? Forget about the deep web. All of that information is more or less "protected."  What about the stuff that isn't? This information could include websites that might have vulnerabilities on them, internet facing webcams/cameras, and even plaintext lists that contain username/password information. If google indexed it, it's out there to find. 

"Wait, wait, wait Taylor. I can't just type in 'usernames and passwords for X site' into google, and it will give me the information."

Well, no. And not because the information isn't out there. You just typed it in the wrong way. Google has advanced search operators or **dorks** that you can enter into a search query, and potentially find more specific results. This makes sense from a management perspective. Google is a very powerful search engine, and it's completely reasonable that they included advanced search operators in order for people to narrow search results from the billions upon billions of resources out there. Unfortunately, this means that it also applies to finding out sensitive information that is very useful to hackers. 

### Try Searching For...

Let's back up for a second and talk about normal searches. When we go to google, we generally have an idea of what we want to search for. Suppose we want to look election news coverage. You might type in "election 2020" on google. Here are the results:

![Search1]({{ site.url }}{{ site.baseurl }}/assets/images/search1.png)

As you'd expect, there are numerous hits from a variety of sources that all have election coverage. This isn't unlike any search we've all done before. Now let's suppose that we only wanted results from a specific website. We might enter this search below...

![Search2]({{ site.url }}{{ site.baseurl }}/assets/images/search2.png)

If you notice, our search string begins with "site:cnn.com" and then we use our search term we are looking for. This is an example of using one of the advanced operators mentioned above to narrow our search results. Specifically, the "site" operator was used in this example. This operator searches based on the specific website associated with it in the search. In fact, there are tons more of these operators. Here they are:

![Dork]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_dork.png)

As you can see, these operators all have some purpose in enhancing a search. Most of them can be combined as well to provide even greater granularity. With the right amount and set of operators, and a bit of creativity, we can probably imagine how hackers and other curious people could use this for their own benefit.

### Site:pentagon.gov Filetype:pdf Aliens Exist

As silly as that search query may sound, it's not based too far off of what you can actually attempt to search for on google. Also I'm not going to jail for putting a real query out there like that. Remember, google indexes **whatever information it can find**, which can sometimes includes government related documents. In this simple search, all we're looking for is any pdf document on pentagon.gov (not a real website btw) that contains anything related to aliens existing. As simple as this search is, we can see how powerful this could be if it were used applicably. 

The point of these searches are to find what may be hidden deep in google's indexes. We could easily flip this search and say "filetype:txt @gmail.com username and passwords" This would potentially give us usernames and passwords that are stored in text files relating to gmail.com email addresses. Of course, these sites hosting the information could be malicious in nature and/or old in which the information on it is no longer valid. Realistically, most of the credit card and social security information is going to be on the dark web, but you may find this information with a simple google dork! 

It's safe to say if you're a hacker, google is probably going to be more useful than people give it credit for. In fact, there's a whole "google hacking database" hosted by [exploit-db.com](https://www.exploit-db.com/google-hacking-database) This website has a section that has user submitted google dorks that all do something different. The website also contains information about any recent exploits found by security researchers/security enthusiasts, as well as other varied cyber security content. I encourage you to take a look through it. 

![GHD]({{ site.url }}{{ site.baseurl }}/assets/images/ghd.png)

I think this goes without saying, but please do not try to do anything malicious, even unintentionally, by using google dorks to try to access sensitive information. This is purely educational, and I hold no responsibility in what you choose to do with this knowledge. 

Thank you for reading! 
