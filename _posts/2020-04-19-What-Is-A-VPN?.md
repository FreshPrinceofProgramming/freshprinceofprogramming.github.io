---
title: "What is a VPN?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg
  
---

With the recent increase of people working from home due to COVID-19, I think it's appropriate the first post in this topic be about VPN's. 

## What the hell is a VPN?

VPN stands for "Virtual Private Network." You may or may not have heard this term before, but I guarantee you've used one at some point in the past. You might even be using one now. We can talk about VPN's in a couple of different ways, but first let's talk about what a normal computer network is.

Right now reading this article you are connected to the internet! Well...duh, right? More specifically, your computer is part of a LAN or Local Area Network. Whether you are connected to the internet at work, home, Starbucks (this is will come up later), etc., you are on a LAN for that particular location. The LAN that you are on has every device that connects to the internet, which is why this logical separation of LAN's make sense depending on your location. For example, your home network is one LAN, whereas your neighbor's house across the street is a different LAN. The router/modem in your home network is the device that will connect you to the greater internet or WAN (Wide Area Network). 

Example of a home network LAN
![Home Lan]({{ site.url }}{{ site.baseurl }}/assets/images/HomeLAN3.png)

But how exactly are your devices able to connect to the internet? There has to be some way to identify your device(s) across the internet. This is where IP addresses come into play...

## IP Address?

An IP address is an address that gives your device a unique identity. This IP address is usually broken down into 2 categories: your local IP (i.e. on your LAN), and your public IP (i.e. on the internet). 

Your local IP is used to differentiate devices on a LAN. This is to ensure that the right device gets the appropriate information you request, and not any other device. This also makes it A LOT easier to communicate with other devices on your LAN. For example, if you have a wireless printer, both the printer and your device need to know each other's local IP in order to complete a print job. No WAN/internet forwarding is necessary. 

Your public IP is where things get a little tricky. Believe it or not, your LAN (in most cases) only has one public IP that all your devices use to communicate out to the internet. Yes, you read that right. So that means your phone, laptop, tablet, etc. are all indentified on the public internet with the same IP. The entire process for this is called NAT(Network Address translation), and it's the reason why you're able to connect to the internet on your LAN. This is handled by your router, and therefore largely abstracted from the user. Your ISP (Comcast, AT&T, etc.) will asign your router a public IP that is owned by them. I highly recommend looking up how NAT works on a more technical level, if you're interested. 

So now that we've introduced what an IP address is, we can 


