---
title: "Ports & Protocols"
categories:
   - Capture The Flag/Pentesting
---

This article is supplementary to the Nmap section in [Kali Tools](https://freshprinceofhacking.github.io/capture%20the%20flag/pentesting/Kali-Tools/). If you're going to be following the CTF guide on here or elsewhere, you're still going to have to know about ports and protocols. 

### So what are Ports and Protocols?

If you think about your computer and the various tasks it does, there has to be a reason why it all works. Your computer not only has to know what it's communicating with, but more importantly HOW to communicate with other devices/services. Establishing a communication method or protocol, will allow devices to interact with each other in a meaningful way. For humans, it's a similar structure. We need to have some sort of communication method with each other in order to accomplish some goal. We've all probably experienced a time where we couldn't understand what the other person way trying to say, which made the conversation difficult. Luckily, we don't have to teach our computers any languages... 

Probably the most common communication protocols we as computer users see are HTTP and HTTPS. These 2 protocols are responsible for making sure that data communication over the world wide web is possible. To the user of a device, we largely don't care or are concerned with how data is flowing to and from places over the internet. It just works. However, your browser on the computer had to interpret a lot of data to make sense of what it is being asked to do. More importantly, it had to use a port to send that data over. You can think of a port as a channel or gateway for data to flow over. Internet traffic has specific ports it uses, whereas email uses a different port. The purpose of these ports are to organize data flows. 

Here's a list of the most common ports and what services/protocols they are associated with:

![Ports]({{ site.url }}{{ site.baseurl }}/assets/images/ports.png)



