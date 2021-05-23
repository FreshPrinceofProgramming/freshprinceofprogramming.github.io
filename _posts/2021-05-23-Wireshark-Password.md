---
title: "Finding Passwords with Wireshark"
categories:
  - Hacking
header:
  image: assets/images/hack.jpg

---

So we've already seen how we can collect credentials through using SET (Social Engineering Toolkit). Now let's see how we can get credentials using a network packet analyzer. In this article we'll take a brief look at Wireshark and how it can be used to gather information. 

### Back to the Basics

If you've read my ["What is a VPN"](https://www.freshprinceofhacking.com/what%20the%20hack/What-Is-A-VPN/) article, I mention the term **network packets** a few times. To recap: network packets are the form in which all connections to and from various devices either locally or on the internet are sent. This makes sense because there has to be some agreed upon format for information to travel over. You may have heard the terms **TCP** or **UDP** used in describing network packets. Both are protocols within themselves, but they are forms of network packets that are responsible for getting information from point A to point B. From a network management perspective, being able to view these connections over various protocols can be quite useful for doing things like troubleshooting for example. If you're able to look into a connection at the packet level, it can provide insight to what may be going wrong.

On the flip side, packet analysis can also provide information such as the actual content being sent over (aka the **payload**). What information can be in the payload? If you authenticate to a website, once you hit enter, your credential information is passed through the wire into the backend of whatever server is responsible for logging you in. Essentially, your login information is in packets! This means your username and password are out there to view if you have a packet analyzer. 

Now before you panic, the good news is that you've probably (hopefully) only authenticated to sites via **HTTPS**. This is the Hypertext Transfer Protocol Secure protocol. It means that information sent back and forth between your device and the site you're on is encrypted. The payload in the network packet cannot be viewed in plaintext so as to steal login information with a packet analyzer. This is a good thing, but unfortunately everything on the internet is not encrypted. Prior to HTTPS there was HTTP, which is still very commonly used. Through some quick thinking I think we can figure out that the missing "S" means the connection is not secure. This is where our packet analyzer comes in handy.

### SHARK!!!

Let's open up Wireshark to see what it looks like:

![Wiresharkmain]({{ site.url }}{{ site.baseurl }}/assets/images/wireshark.jpg)

Looks confusing, right? Well, it is...but we'll get through this! This is Wireshark. It is an all purpose network packet analyzer that can show you connections being made over different interfaces. These interfaces can be a wireless card for example. For the purpose of this particular article, I'm only using my wireless card built into my machine. This means I can monitor network traffic coming from my device only, which for this example is more than enough. I captured network traffic on my wireleses card for about a couple of minutes to get the results.  

What do you notice in the picture? Even if you don't understand the intricacies of the content, there are some key indicators that Wireshark is showing us. We can see the source, destination, protocol and information regarding the individual packets. This is highly useful in viewing the content we want to see. With Wireshark, we can inspect every single individual packet of a connection that has been captured. So let's do some investigating! 

We want to be able to view unencrypted credentials that are being sent over for authentication. For testing purposes, I found a website that is basically created to simulate insecure logins and other vulnerabilities:

![testvuln]({{ site.url }}{{ site.baseurl }}/assets/images/packetexample.jpg)

I've gone ahead and put some test credentials in there.

* Username: Vulnerableuser
* Password: ?

Now remember, this information needs to get to the server for us to authenticate. This means that this connection will be picked up by Wireshark. You can probably imagine that there are thousands of packets we need to look through to find the specific one that has our credentials. Because of this we need to narrow our search and find the right one. How can we do this? Well we know that the connection is unencrypted. And we know this because we see "Not secure" in the top next to the site name in the address bar. Typically this means that connections going back and forth are going to be open to see. We also know that the HTTP protocol is insecure for this reason. So let's search for all connections that are using the HTTP protocol, and we might have some luck.

![http]({{ site.url }}{{ site.baseurl }}/assets/images/http.jpg)

Here are all the observed HTTP connections being made during the capture of network traffic from my device. If we notice towards the bottom we can see the packets that are responsible for logging in and collecting information from the user (Packet 337: GET /login.php HTTP/1.1). Now all we have to do is simply view the packet details and find the username and password. This is done by viewing the HTTP or TCP stream, which will show us in plain text how that connection looked.

![creds]({{ site.url }}{{ site.baseurl }}/assets/images/exposedpassword.jpg)

In the yellow highlight, we can see the username and password! The password ended up being "Wowyoucanseethis." Not the most complicated password, but hey we didn't need to crack any hashes to reveal it. The above is the full conversation between the browser and the server making sure that they are getting the right details needed for authentication. And unfortunately, it is unencrypted for anyone to see listening over the WiFi.

### The "Starbucks Wifi" Network is Available

Let's recap what we did. We used Wireshark to capture our network traffic and viewed information in the payloads of packets. We were able to simulate an insecure login to view sensitive credential information passed over the wire. Essentially, we did a **man-in-the-middle**(MITM) attack. These attacks take advantage of vulnerable communications where someone is able to observe them that probably shouldn't. More advanced MITM attacks involve the attacker actually modifying the information sent over in order to achieve some goal. This is why it highly important that sensitive information is never put over insecure mediums. 

Now imagine you're in a Starbucks on the WiFi. There are tons of people on the Wifi doing different things, which they hope can't be easily seen by anybody. We just ran through an example of how you can use Wireshark to view network traffic. If you're a malicious actor, this becomes a no brainer on what the possibilities are. If you are able to configure Wireshark with a proper wireless card that can view traffic from every device, nobody is safe from a potential MITM attack if your information is unencrypted. In fact, hackers might even attempt to spoof the public wifi network and get your machine to join the fake one instead. From there they can possibly enable services that will strip SSL from HTTPS and force all traffic to be unencrypted. This is called an Evil Twin Attack, and is a highly effective way for hackers to steal information. 

Don't freak out! We can take precautions against hackers viewing our internet traffic, as well as our ISP/anyone else we don't want. And that's if we use a VPN! VPN's will encrypt your traffic between your device and the VPN server. This means if someone was trying to view the connections via a packet analyzer, they would only be able to see encrypted connections. 

![watchguard]({{ site.url }}{{ site.baseurl }}/assets/images/vpnguard.jpg)

Now if we rerun Wireshark while we have a VPN turned on, we can now see these results. Because there are many different VPN services out there, yours may very slightly in how it's presented on Wireshark. The main point is that we no longer see unencrypted connections. The protocol "Watchguard" is a popular open source VPN protocol, which allows for encrypted tunneling to be set up between your device and the VPN server. Things like DNS records or anything else that might be able to identify network activity should in theory be protected. If we take a look at some sample traffic by following the stream of connections, we get something like this:

![vpnencrypt]({{ site.url }}{{ site.baseurl }}/assets/images/watchguard.jpg)

As we see, there can be nothing deduced from the stream that would put sensitive information at risk. This information is encrypted and can only be decrypted by the appropriate party. 


### Concluding Thoughts

Hopefully now you've been able to see how easy it is to monitor network traffic. Wireshark is an insane tool with many more features that can't be summed up in just one article. This tool isn't even illegal, and it's free to download. From a cyber security perspective, it can be used to either investigate suspicious network activity, or be a key factor in gathering information while performing an attack. You can bet the bad guys out there are using every tool in their disposal to create and execute serious attacks.

For most people out there, you can definitely reduce the chances of compromise in this way by adhering to some basic security rules; mainly use of your device on open public wifi networks. I'm not saying every single open wifi network is dangerous, but they are very easy targets. You can't possibly know every single person using the wifi in a big space. And it's not like hackers have a big sign saying "Here I am!" 

I'm also not trying to force you to buy a VPN either. As mentioned in the article I have on VPN's, they are not perfect. They offer some added security benefits at the cost of a monthly/yearly subscription. If you're someone who likes to log into public wifi spots and/or want to add to your security posture, then they might be worth the purchase. If not, the very least you can do is be aware of your surroundings and make sure your online activity is secured. This means to always make sure you are connecting to sites you authenticate over with "HTTPS." You can check the top of the address bar in your browser to confirm. 

Thank you for reading! 





