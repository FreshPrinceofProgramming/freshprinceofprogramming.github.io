---
title: "What is a VPN?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg
  
---

With the recent increase of people working from home due to COVID-19, I think it's appropriate the first post in this topic be about VPN's. 

## What the hell is a VPN?

**VPN** stands for "Virtual Private Network." You may or may not have heard this term before, but I guarantee you've used one at some point in the past. You might even be using one now. We can talk about VPN's in a couple of different ways, but first let's talk about what a normal computer network is.

Right now reading this article you are connected to the internet! Well...duh, right? More specifically, your computer is part of a **LAN** or Local Area Network. Whether you are connected to the internet at work, home, Starbucks, etc., you are on a LAN for that particular location. The LAN that you are on has every device that connects to the internet, which is why this logical separation of LAN's make sense depending on your location. For example, your home network is one LAN, whereas your neighbor's house across the street is a different LAN. The router/modem in your home network is the device that will connect you to the greater internet or WAN (Wide Area Network). 

Example of a home network LAN
![Home Lan]({{ site.url }}{{ site.baseurl }}/assets/images/HomeLAN3.png)

But how exactly are your devices able to connect to the internet? There has to be some way to identify your device(s) across the internet. This is where IP addresses come into play...

## IP Addresses 

An IP address is an address that gives your device a unique identity. This IP address is usually broken down into 2 categories: your **local IP** (i.e. on your LAN), and your **public IP** (i.e. on the internet). 

Your local IP is used to differentiate devices on a LAN. This is to ensure that the right device gets the appropriate information you request, and not any other device. This also makes it A LOT easier to communicate with other devices on your LAN. For example, if you have a wireless printer, both the printer and your device need to know each other's local IP in order to complete a print job. No WAN/internet forwarding is necessary. 

Your public IP is where things get a little tricky. Believe it or not, your LAN (in most cases) only has one public IP that all your devices use to communicate out to the internet. So that means your phone, laptop, tablet, etc. are all indentified on the public internet with the same IP. The entire process for this is called **NAT** (Network Address translation), and it's the reason why you're able to connect to the internet on your LAN. This is handled by your router, and therefore largely abstracted from the user. Your ISP (Comcast, AT&T, etc.) will asign your router a public IP that is owned by them. I recommend looking up how NAT works on a more technical level, if you're interested. 

#### What do IP Adresses look like?

IP addresses are numerical values in the form "X.X.X.X" where X represents a value from 0-255. More specifically, this notation represents what we call an **IPv4** (Internet Protocol version 4) address. As stated above, this value is a unique identifier for a device on a network. Due to constraints on how many numerical values can be represented with IPv4, only 4,294,967,296 total addresses (2^32) can be used on every single device out there in the world. Obviously, there are more than that amount of devices in existence. To combat this, there are certain reserved spaces for private and public IP addresses. In fact, this is why NAT was invented.

Here are the spaces reserved for private addresses:

![private IP]({{ site.url }}{{ site.baseurl }}/assets/images/privateip.jpg)

If you ever see IP's that fall into these ranges, you are seeing a private IP used to identify yourself on a local network. You can check this value yourself by going into the network settings on your device. It is most likely in that location.

With a few exceptions to some more ranges, every other IP address is used as a public IP. You can check your public IP by going to [sites like these](https://whatismyipaddress.com/). 

Due to the limitation of IP's available for IPv4, **IPv6** is now starting to be implemented more widely in networking. IPv6 is cable of representing 2^128 numerical values, which is...hella big. In fact, you may see your public IPv6 address on the websites you use to look up your public IPv4 address. They look something like "X:X:X:X:X:X:X:X" Very cryptic looking, but it's the future, so we'll roll with it for now.


## So What the hell is a VPN??!!...forreal this time

We've already establised that a public IP address is how your devices are seen on the internet. When you connect to facebook.com, your device sends out information to a facebook server that is hosting the service in the form of **network packets**. These packets include things like source IP (where it's coming from), destination IP (where it's going to), and payload (content being sent over in the request). We will call this the **client-server model**. The client is your device, and the server is the destination that is hosting the content you want to access.

Your device with its public IP connecting to the facebook server
![client server]({{ site.url }}{{ site.baseurl }}/assets/images/clientserver.png)

Facebook now knows your public IP, and can track it to you via your ISP. This seems like a very invasive, almost creepy sort of thing that facebook and anyone else potentially can do. What if there was a way to hide your IP address so that you can effectively stay "hidden" on the internet? 

*cue drumroll

YOU CAN DO THIS WITH A VPN!!! :D

A VPN can effectively be used to hide your IP and further encrypt your data. With a VPN, all of your internet traffic is routed through a VPN server that is designated with some external IP which will now be yours to use. Before a VPN, connecting to facebook.com exposed our public IP. Now with a VPN, facebook only sees the public IP of the VPN server.

![client vpn server]({{ site.url }}{{ site.baseurl }}/assets/images/clientvpnserver.png)

## Practical Applications of VPN's

Here are some ways in which VPN's are useful in their applications.

#### Staying Anonymous on the Internet

This is the big selling point of a lot of VPN vendors. For the most part, they're correct in the sense that this will keep you anonymous on the internet. By websites never seeing your real public IP address, they cannot properly identify who you really are. However, the major draw back is that the VPN companies themselves know your real public IP address. In order for you to use their software, you need to connect to the VPN server, which means they see your public IP in the network packets.

They are also getting all of the traffic you are requesting over the internet. They could potentially be storing all of your network activity in logs. In choosing a VPN service, look to see if the company offers to not keep any logs of activity. It's hard to find one that doesn't, but this is another major selling point in my opinion. 

#### Access Of Internal Resources

As mentioned at the beginning of this article, a lot of people are now working from home. Companies around the world now have had to shift their workforce into a virtual space. Employees still need to be able to access internal resources that are otherwise not available outside of their work's LAN. If we can mimmick another public IP on the internet, why can't we do the same for a LAN that we want to be a part of remotely? VPN's are exactly how you solve this problem.

A company could set up a VPN server somewhere within the company, usually on the firewall or internal network, and have their employees connect to that VPN. The VPN server would be set up in a way that devices connected to it are allowed to interact and be part of the internal LAN. This way you can still access your companies internal resources from the comfort of your own home. No long commute required to be in the building to do the same thing! 

#### Access Region-locked Content

Remember, your public IP address is how you are identified on the internet. When your ISP assigns you a public IP, that IP is usually in proximity to where you are currently located. Yes, your IP can give away your geographical location. With a VPN we can actually pretend to be in a different part of the world if we wanted to. This means that if you connect to a VPN server in London, your device's public IP is going to look like it's coming from London! 

It is not uncommon for content on the internet to be region locked. In fact, Netflix is a great example of content that is given to the user based on region. There are shows in other parts of the world that we cannot access here in the United States. VPN's solve this issue. Say goodbye to region locked content on Netflix! 

More so than just accessing region-locked Netflix content, VPN's can also be used to potentially view any content that is restricted by your ISP. This has come up largely when dealing with countries that restrict certain parts of the internet from their citizens. China is a great example of this particular problem. There are many things online that are restricted by the Chinese government, and therefore not reachable by the user. If you're someone who wants to view more content or get around the restrictions in place, a VPN might be your best bet.

#### Protection on Public Wifi

We've all used public wifi before, but what devices are actually on that public wifi LAN? At home it's more or less easy to know what devices are part of your home network, but in public places, this constantly changes. Think about the hundreds, if not thousands of people going in and out of coffee shops, airports, malls, etc. There's no way to personally know every device on that wifi.

Let's suppose someone were able to sit on a public wifi and "listen" to all of the traffic over it. What information could they see? They could potentially see what websites you are visiting, and any personal information being sent over wifi that is not encrypted. 

**Warning:** You should always make sure that you are connecting to websites with "https" and not "http."
{: .notice--warning} 

"How the hell is that possible?" 

Remember, information over the internet and beyond is sent in network packets. These packets effectively contain all of the information associated with the content you are either sending or receiving. From a network management perpsective, it would be nice to be able to see these packets in transit in order to see what is actually going during these connections. There are packet analyzing tools for this exact purpose. A hacker could use one of these tools to sniff traffic over wifi and steal information. 

One thing that is important for any VPN to have is a strong encryption standard. VPN's will use a variety of ways to further encrypt traffic, which for us is important if we want to be able to stay secure on non-safe networks. VPN's will encrypt our data before reaching the VPN server itself. Any attempt to sniff the traffic will be seen as giberrish, and might deter a hacker from attempting to target your machine. 

## Should I Buy a VPN?

This seems to be the million dollar question. I would say that overall no matter your level of internet activity and what information you send out online, VPN's will always add benefit to your security stack. With that said, you as a user of the internet also need to be aware of the dangers and how to protect yourself regardless of any extra security tools. VPN's are not 100% secure, but neither is anything else. It's said that if you want to have ultimate security, turn off your computer and never use it. Obviously, this isn't ideal or practical. 

VPN's also cost money, usually in the form of a monthly/yearly subscription. Every VPN provider is going to market that they have the best secure VPN, and that this is why it costs X per year for the service. They aren't typically super expensive, but I would do research prior to committing to a VPN service and see what they are offering. Here's what I'd look for:

1. Price
2. Do they keep logs of activity? (very important)
3. What kind of encryption do they use? (also very important)
4. Misc. offers within the subscription (support for UDP, double VPN, TOR, etc.)

Here is a list of [the top VPN services out right now](https://www.techradar.com/vpn/best-vpn)

Thanks for reading! :D
