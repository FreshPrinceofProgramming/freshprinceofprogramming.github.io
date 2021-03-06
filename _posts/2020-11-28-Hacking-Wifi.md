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

Devices have to do this same kind of intro, but in a technical sense for many computer processes non-related to just accessing Wifi. However, the one thing that is passed over in this particular case during the handshake is the **preshared key**, aka the Wifi password. It turns out that if we can position ourselves inbetween the access point and a client device trying to authenticate, we can capture the handshake and try to crack the password hash that's in it. This can be done by using a wireless network card and a program capable of doing the dirty work. Well let's get started...
