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

Now that we've introduced some basic network knowledge, we can finally talk about VPN's! 

## So What the hell is a VPN??!!...forreal this time

We've already establised that a public IP address is how your devices are seen on the internet. When you connect to facebook.com, your device sends out some basic information to a facebook server that is hosting the service, in the form of network packets. These packets include things like source IP (your public IP), destination IP (where is it trying to connect to), and payload (content being sent over in the request). There are many other things sent in packets, but we're keeping it simple. We will call this the client-server model. The client is your device, and the server is the destination that is hosting the content you want to access.

Your device with its public IP connecting to the facebook server
![client server]({{ site.url }}{{ site.baseurl }}/assets/images/clientserver.png)

Facebook now knows your public IP, and can track it to you via your ISP. This seems like a very invasive, almost creepy sort of thing that facebook and anyone else potentially can do. What if there was a way to hide your IP address so that you can effectively stay "hidden" on the internet? 

*cue drumroll

YOU CAN DO THIS WITH A VPN!!! :D

A VPN can effectively be used to hide your IP and further encrypt your data (most of the time). With a VPN, all of your internet traffic is routed through a VPN server that is designated with some external IP which will now be yours to use. Before a VPN, connecting to facebook.com exposed our device's IP. Now with a VPN, facebook only sees the public address of the VPN server.

![client vpn server]({{ site.url }}{{ site.baseurl }}/assets/images/clientvpnserver.png)

## Practical Applications of VPN's

Hiding your IP address is just one of many applications for a VPN. I'll have a separate article on anonymity, privacy, and how to stay safe on the internet in the future. For now, I think it's important to just note why VPN's are useful and why you may want to buy one.

#### Access Of Internal Resources

As mentioned at the beginning of this article, a lot of people are now working from home. Companies around the world now have had to shift their workforce into a virtual space. Employees still need to be able to potentially access internal resources that are otherwise available outside of their work's LAN. If we can mimmick another public IP on the internet, why can't we do the same for a LAN that we want to be a part of remotely? VPN's are exactly how you solved this problem.

A company could set up a VPN server somewhere within the company, usually on the firewall or internal network, and have their employees connect to that VPN. The VPN server would be set up in a way that devices connected to it are allowed to interact and be part of the internal LAN. This way you can still access your companies internal resources from the comfort of your own home. No long commute required to be in the building to do the same thing! 

#### Access Region-locked Content

Remember, your public IP address is how you are identified on the internet. When your ISP assigns you a public IP, that IP is usually in proximity to where you are currently located. Yes, your IP can give away your geographical location! With this in mind, I think it's becoming clear what exactly a public IP is and why it's so important. With a VPN we can actually pretend to be in a different part of the world.

Depending on where the VPN server is hosted, it will adopt that region along with the public IP it has. This means that if you connect to a VPN server in London, your device's public IP is going to look like it's coming from London! It is not uncommon for content on the internet to be region locked. In fact, Netflix is a great example of content that is given to the user based on region. The Netflix people in the United States access is different from the Netflix people in Korea access. There may be exclusive content to both sides that neither can access in a normal situation because they are tied to their regional public IP. VPN's solve this issue. Say goodbye to region locked content on Netflix! 

#### Protection on Public Wifi







