---
title: "What is Ransomware?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg
  
---

Ransomware has easily become one of the most popular cyber security threats over the last few years(although been around for much longer). It has affected countless individuals and every industry you can think of: education, finance, municipal, etc. it doesn't look like attacks are slowing down anytime soon either. In this article we will dive into what exactly ransomware is and how you can protect yourself from it. 

### Ransom Note

Probably somewhat of an obvious motivation for hackers is financial gain. We've seen countless times in the news (or you may have experienced it yourself) when hackers have stolen credit card information, or other financial documents in order to get some sort of monetary value out of their hack. In fact, it is estimated that by 2025 cybercrime is going to cost the world up to [10.5 trillion dollars annually](https://cybersecurityventures.com/hackerpocalypse-cybercrime-report-2016/). That's not a small number. That's about roughly 1/9th of the world's GDP, and about **half of the United State's GDP**. 

When it comes to hacking, we need to think more broadly about what represents value. In the real world we have things that are worth value depending on who the thing belongs to; jewelry, artifacts, shoes, etc. If we're theives, this is what we may target. In cyber space things change a bit. While there is no physical tangibility, a document that may contain personal information may be considered valuable. In the case of many companies all over the globe, intellectual property stored on a server is a great example of something that is considered a high valued asset. To a hacker, these are all items that stand out as good targets. 

Let's say you woke up one day and were presented with this screen at your desktop:

![Wanacry]({{ site.url }}{{ site.baseurl }}/assets/images/wanacry.png)

Your first reaction would probably be one of shock, but maybe disbelief. You then try to access files on your computer and they are all "locked." You now realize that you've been hit with ransomware. This is the exact prompt many companies and individuals were hit with back in 2017 when the **WannaCry Ransomware** attack made its way into the cyber world. This attack was highly distributed and just one of many ransomwares out there that have affected people. We'll break down the components of ransomware in the next section.

### Get Your Files Back!

There's a lot to unpack from the above screenshot. It claims you can get your files back if you **pay a certain amount in bitcoin**. It also claims the pay amount will raise after a certain amount of days, and after 7 days your files will be gone/unaccessible permanently. This sounds eerily like a normal kidnapping scenario. Much like a kidnapper would demand ransom for the person they just kidnapped, we can see the similiarties in how a hacker may do the exact same thing but with someone's computer files. So how does ransomware work?

We can break down ransomware by first addressing its main component, **encryption**. If you want to learn more about encryption, check out my ["What is Encryption"](https://freshprinceofhacking.github.io/what%20the%20hack/What-Is-Encryption/) article. Essentially, this is the hacker's way to control the entire situation. If they are able to encrypt your files, only they(presumably) would have the key to unlock them. Towards the end of my encryption article, I hinted that this is the main crux of encryption. When implemented correctly it works very well, which may have negative implications for people that need to access that information.

Ransomware falls under the category of a virus. It's a specialized virus that is designed to search through your computer and encrypt as many files as possible. In addition, it also can include any necessary component to have the hack be succesful in the long run; for example this could include some kind of command and control install and a way to propagate throughout the network. 





