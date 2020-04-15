---
title: "Kali Tools"
categories:
  - Capture The Flag/Pentesting
---

I mentioned in the last post that Kali (amongst other security distros) comes pre-packaged with a myriad of tools that are at your disposal. When performing pentests or CTF challenges, you'll be using these tools to complete your engagements. In fact, it's not uncommon to see profressional pentesters create their own tools from scratch in order to complete some task. Fortunately for us, most if not all of the tools we'll need are either already in kali, or very simple to download and incorporate into our tool set. It's very important to understand what these tools do and how they may help you solve a task. If you were building a house, I'd expect you to know when to use a hammer vs a chainsaw for example. The same goes for hacking.

**Warning:** These are real hacking tools that if used improperly and/or maliciously, could cause potential damage to a system. Please only use these in testing environments, or environments were you have permission to engage in such behavior. 
{: .notice--warning} 

## Nmap

This tool is going to be our swiss army knife for performing reconnaisance on a target(s). "Network mapper" or Nmap, is a very powerful tool that allows us to probe into a network for host discovery, port/service information, and vulnerability detection. As this relates to hacking, we can essentially find out which devices on a network are best for targeting. 

A lot of movies and tv shows (Mr. Robot excluded) make hacking into networks and devices seem very simple. You click on a button, and BAM, you've "made it passed the firewall." However, in real life hacking these things take time, and it's important that we have a good understanding of where and how we're going to approach a target machine. The more information we have, the better off we'll be in the long run.

Port and service detection is where we're going to focus our attention. I have a post on ports and protocols that supplements this, so please go look at that for a more detailed explanation. I'm going to assume you've either read that or already have prior knowledge. 

There are so many other applications of nmap that it's pretty hard to explain everything that it can do. I recommend visiting the [website](https://www.nmap.org).

Do NOT use nmap to scan random networks and systems. While not neccesarily "illegal," your nmap scans can leave a digital footprint of who you are (there are ways to evade this). Better to be safe than sorry and explain to your boss, police, or some legal authority figure why you were snooping around. Think of an nmap scan like walking around a house and making notes of all the potential entry points (windows, doors, etc.). Walking is not illegal, but you might draw attention to yourself and be asked what you are doing. 






