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

For security reasons I have blurred out my neighbors' wifi networks and have only left my own. There's quite a bit to unpack here. Wifite has given me the name of the network (ESSID), the wifi channel, encryption type (WPA), signal strength, WPS enabled, and how many clients are on the network. All of this information is important in choosing to select a potential target, especially the encryption type, signal strength and if WPS is enabled.

Our main goal is to try to hack a target wifi network in order to gain credentials into the network. The encryption type will let us know how to attack the network. The signal strength will tell us how close or far we are away from the target. We can't hack a wifi network if we're not in range. WPS is a potential seperate way to attack the wifi network and gain access, but we will touchbase on that at the end of the article. 




