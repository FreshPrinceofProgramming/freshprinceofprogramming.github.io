---
title: "Phishing for Credentials"
categories:
  - Hacking
---

In this article we're going to see how we can use some hacking tools to create a phishing campaign in order to gain user credentials for an email platform. This is just a proof of concept more so than an actual hack. I'm not trying to go to jail :(

### Scenario

We are notorius hackers that want to gain a users gmail credentials. We want these credentials because the user we're after is a big target for important information. If we can get credentials, we can potentially view emails that they've sent that could have information we can use against them later in our larger hacking campaign. In order to do this we're going to be crafting an email to the victim posing as the Interal IT team. Hopefully, the user will fall for our scheme and click the link in the email, which will direct them to a fake login page. Once they enter in their credentials, we will be supplied with the username and password for the account. Pretty simple ;) 

### Tools Used

* Operating System: Kali Linux 
* VirtualBox for emulation of Kali Linux
* SET (Social Engineering Toolkit) for creating our phishing scam 

### The Attack



