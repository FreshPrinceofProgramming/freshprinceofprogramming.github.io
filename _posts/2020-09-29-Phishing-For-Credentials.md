---
title: "Stealing Facebook Credentials"
categories:
  - Hacking
---

In this article we're going to see how we can use some hacking tools to create a fake website in order to gain user credentials for Facebook. This is just a proof of concept more so than an actual hack. I'm not trying to go to jail ;)

### Scenario

We want to gain a user's Facebook login credentials. If we get these credentials, we can potentially log in (if 2FA isn't enabled), and find out all there is to know about our victim on their facebook page. With this information, we can possibly form more attacks for our benefit at a later stage. 

### Concept

**Social engineering** is the art using deception for the purpose of fraudulently gaining sensitive information. An example of social engineering is pretending to be someone in order to illicit a certain response. This can be in real life OR in cyber space. 

Example: If I'm working in the front building of a company, I may let through a wide variety of people throughout the day. Suppose a hacker came into the building, announced to me that they were trying to get further into the building to find a server room to do their malicious deed. I'm probably not going to let them through, and most likely I'm going to call the police. 

Now let's say this same hacker pretended to be a UPS delivery driver. They could easily walk in and say they have to deliver a package for a certain floor. If I'm not doing my job correctly and verifying their identity properly, they could gain access. They would have effectively bypassed the physical security protocol of not allowing any unauthorized people in the building. 

Of course there are more clever ways of using social engineering. In this case, we want to fool the user in believing that the request for logging into their facebook account looks legitimate. Easier said that done...


### Tools Used

* Operating System: Kali Linux 
* VirtualBox for emulation of Kali Linux
* SET (Social Engineering Toolkit) for creating our phishing scam 

### The Attack



