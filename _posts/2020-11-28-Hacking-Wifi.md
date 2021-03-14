---
title: "Let's Hack Wifi"
categories:
  - Hacking
---

Well just like the title says, we're going to hack wifi in this article. It's a lot easier than you'd think. Remember, this is just a proof of concept. I'll be hacking my own wifi connection.

### Scenario

We want to hack wifi. Pretty simple. Our target machine sits behind this wifi access point, and we'll need to establish some presence on the network in order to gain access. Once on the network, we can continue our hacking exploits.

### Concept

Wifi networks are vulnerable to a variety of attacks. Most notably, the way in which we're going to be hacking wifi is through a semi-involved **dictionary attack**. Yes, bad passwords are going to be key for this attack to work. If you're unsure about password security in general, please read my ["How Safe is my Password"](https://freshprinceofhacking.github.io/privacy,%20security%20&%20safety/How-Safe-Is-My-Password/) article.

Specifically, we are going to be targeting a **WPA2 access point**(Wi-Fi Protected Access). To keep it short, this particular security setting is used in many home network routers. It is an updated version of WPA, which allows for a stronger encryption standard to be used to secure your wifi connection. 

Whenever you connect to a Wifi network, a lot has to happen in the background in order to properly authenticate you. Most notably, your device and the access point need to go through a **4-way handshake** in order to establish a connection. You can think of this handshake like an introduction of sorts. If you were to meet someone in real life, how might that conversation go? 

"Hi, my name is Taylor."

"Nice to meet you Taylor. My name is Bob"

"Great meeting you Bob."

Devices have to do this same kind of intro, but in a technical sense for many computer processes non-related to just accessing Wifi. However, the one thing that is passed over in this particular case during the handshake is the **preshared key**, aka the Wifi password. It turns out that if we can position ourselves in between the access point and a client device trying to authenticate, we can capture the handshake and try to crack the password hash that's in it. This can be done by using a wireless network card and a program capable of doing the dirty work. Let's get started...

### Tools Used

* Operating System: Kali Linux
* Virtualbox for emulation of Kali Linux
* Wireless network adapter: TP-Link TL-WN722N
* Wifite2: automated wifi hacking tool for linux systems
* Aircrack: Wifi network security assesor 

### The Attack

The first thing we'll need to do is fire up our Kali Linux box and run the wifite program. I don't believe wifite is part of Kali by default, but you can download it by [cloning their github page](https://github.com/derv82/wifite2) and following the directions. I'm assuming you'll also have a compatible wireless network adapter installed at this point. If you're unsure which one to buy [check these out](https://www.ign.com/articles/best-usb-wifi-adapter). You don't need to spend a lot of money on one, but if you want to do a variety of hacks it will need to be an adapter that you can put into "monitor mode," and capable of packet injection. 

Once you have wifite installed and running, you should see this page:

![Wifite1]({{ site.url }}{{ site.baseurl }}/assets/images/wifite1.png)

The great thing about wifite is that it will automatically put our wireless adapter into monitor mode. You can think of monitor mode like being able to listen to everything around you. The wireless adapter will be listening around to see which wireless networks are out there. You can put your adapater in and out of monitor mode as you see fit, but for these next few steps you'll need to keep it on.

Wifite should automatically then start sniffing for wifi networks around you. Depending on the adapater you bought and where you are located, it may pull dozens of wifi networks around. Your screen should look like the following:

![wifite2]({{ site.url }}{{ site.baseurl }}/assets/images/wifite2blur.jpg)

For security reasons I have blurred out my neighbors' wifi networks and have only left my own. There's quite a bit to unpack here. Wifite has given me the name of the network (ESSID), the wifi channel, encryption type (WPA), signal strength, if it's WPS enabled, and how many clients are on the network. All of this information is important in choosing to select a potential target, especially the encryption type, signal strength and if WPS is enabled.

Our main goal is to try to hack a target wifi network in order to gain credentials into the network. The encryption type will let us know how to attack the network. The signal strength will tell us how close or far we are away from the target. We can't hack a wifi network if we're not in range. WPS is a potential seperate way to attack the wifi network and gain access, but we will touchbase on that at the end of the article. 

Continuing on, wifite will run through the wifi network lists until we give it a command to stop. If you press Ctrl+c, that should stop the search. You will then be asked to enter the number of the wifi network that you want to attack. Be careful, as you probably don't want to hack every wifi network in range. In this case, our network is located #6 on the list (channel of wifi has nothing to do with this number). Entering in 6 will bring up this screen:

![wifite3]({{ site.url }}{{ site.baseurl }}/assets/images/wifite3blur.jpg)

There's also a lot going on in this picture, but we'll break it down. Once a wifi network(s) is chosen, wifite will run attacks on the network based on the information it knows. The first attack it ran was a PMKID attack. To keep it short, this method of attack will not rely on any handshake to extract the preshared key password hash. Instead, it will try to get the hash from the access point itself. We'll skip this attack for today. Pressing Ctrl+c will move on to the next attack.

In order to get a handshake we need to see client devices (i.e. phone, laptop, etc.) connect to the access point. This can be done by just waiting for a device to come on the network, but if you're impatient there is a faster way. It turns out we can deauthenticate clients on the network and force them to reauthenticate, which should give us the handshake we need.


**Warning:** This is the part of the hack that will get you into trouble. Technically, kicking someone off the network is considered a **denial of service** attack, and may interrupt necessary processes. This is also a very "loud" attack and system admins will be able to see this. Use with caution.
{: .notice--danger}

While waiting for client devices to join, wifite will attempt to deauthenticate devices on the network every 30 seconds. You can see in the picture that it's found 2 devices, and has captured a handshake. Once it has captured the handshake, it will try to start cracking it using a pre-existing dictionary file of plaintext passwords. For some reason when I tried doing it through wifite it wasn't able to crack it. No worries though, we have other programs that can help us out.

We can use aircrack-ng to help us crack the password hash. You can run aircrack-ng with the -w option, which will take the path of the wordlist we want to use AND the path of the .cap file which contains the handshake. I used the same wordlist that wifite comes with just for consistency. We can see the results below:

![aircrackblur]({{ site.url }}{{ site.baseurl }}/assets/images/aircrackblur.jpg)

We can see towards the bottom that the key was found. It took less than 1 second to run through 4240 keys in the wordlist to find the matching password. Now we can log into the wifi network and start doing...things ;) 

### Conclusion

So now we've seen how easy it is to hack wifi. This doesn't take an overly skilled person to pull off, and it doesn't have to take a lot of time to accomplish. In this particular example I had already added my wifi network password to the wordlist. This made sure it was going to be found. However, we could have also used other password cracking programs to do a **brute force** attack against the handshake file. There are many possibilities.


