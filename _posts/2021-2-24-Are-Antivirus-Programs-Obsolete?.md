---
title: "Are Antivirus Programs Obsolete?"
categories:
  - Privacy, Security & Safety
header:
  image: assets/images/beback2.jpg
---

It's no surprise that cyber security has largely been commodified. This means there's a whole bunch of products that companies are selling to try to get you to enhance your cyber security posture. This includes things like antivirus software. But is antivirus software still relevant in 2021? And if so, which one should you buy? In this article, we'll go through what exactly these programs do to protect you, if you should buy one and the larger implications they have on cyber security. 

### Can I have your signature?

In order for an antivirus program to be successful it needs to catch viruses. Well duh...but how exactly are viruses caught? You can't throw a pokeball at it and it's contained. With the vast amount of virus types out there, it would be great if we could identify them based on previously seen viruses that we know exist. If an antivirus program sees, what it suspects to be, a virus come in and it matches a virus in the database, it can quickly identify it as malicious. This is called a **signature based approach**. 

Malware/virus researchers will try to reverse engineer a new virus they see, figure out its behavior and then create a signature for it. You can think of a signature like a footprint or some other labeling that can help to identify it in the future. A signature is usually made up of particular data points in the virus code that could contain the malicious behavior. The signature is then put into a database of other known viruses of the antivirus program. If this virus is seen in the future by the program, it will know to block it and/or remove it from your computer. 

This is a great way to approach the problem of needing to block known threats. However, this is not useful if a new virus is introduced that has no signature in the database. You can probably imagine the amount of viruses that have no signature are pretty high. This is where signature based detection falls short. The databases for signatures are also constantly growing. This makes it crucial to consistently have your antivirus progrm updated, which is by virtue of how often the antivirus program chooses to update itself. As we can see, it's not feasible to keep this method as a main line of defense. How can we enhance our detection capabilities?  

What if we could modify our antivirus to look at the suspected virus from the inside out? Remember, a virus is just computer code that has the rules and properties for how that particular virus is going to function. We could have the antivirus program analyze the coding structure and decide whether or not it is malicious based on what it finds. This is called a **heuristic based approach**. 

This kind of approach is similar to a signature based one, with a few exceptions. Heuristics will attempt to analyze a virus, much like a researcher would, but instead of looking for a signature, it will look for coding structures that are known to be malicious. For example, let's say a new virus comes out that has not been signatured. Normally in this scenario, a standard antivirus program wouldn't pick it up. However, with heuristics it can see that the coding structure follows a pattern that it has already identified previously as malicious. 

This is very powerful, because now we can expand our antivirus program to detect a lot more "unknown" viruses that have not been fully studied and signatured. Heuristic based approaches are not perfect either. Let's say this is a heuristic for a coding structure that is malicious: A-B-C-D. If the virus creator is smart and knows that's what the antivirus looking for, they can change the coding structure: A-C-D-B. Now our antivirus program will not pick up that virus with heuristics because that pattern doesn't exist in the database.

Heuristics can also generate more **false positvives** than intended. A false positive, in the context of an antivirus, is what happens when something is identified as malicious, but it actually is harmless. There are many legitimate programs that could mimic malware/virus behaviors, and may cause the antivirus to think that the legitimate program is harmful. The silver lining is that antiviruses that use a combnination of both signature and heuristic based techniques can stop a quite a lot of bad stuff out there. We can still do better though.

### Your behavior is appalling

So by now you know that antivirus programs use signature and heuristic based approaches to protect you from threats out there. What other ways are left to find threats? Let's talk about **behavioral based approaches**. First, a real world sceneario:

If you were investigating a crime and had a suspect, what might you do? You could potentially look them up in the police database and see if they have committed previous similar crimes. You might also interview the suspect to try to get an idea of what they were doing around the time of the crime. But let's say there was no direct evidence linked to the suspect at the time. However, you still have your suspicions. What might you do next?

You could then start to analyze the suspect's behavior to see if anything throws a red flag. This could include looking at phone records, surveillence cameras, wiretaps, etc. What you're trying to do is establish a baseline pattern for normal behavior and see if there are any **deviations from that pattern**. If we see the suspect behave abnormally(i.e. packing their belongings and fleeing, revisiting the crime scence, etc.) we might have a good indicator that this is the person we're looking for that committed the crime.

Although that was a simple example, this is the approach that some antivirus programs and various cyber security tools are taking in the defense against malicious activity. We're far beyond just using signatures and heuristics to detect threats. For quite some time the threat landscape has shifted to more advanced viruses and malware that traditional detection tools can't pick up. With a behavioral based approach, we can detect more malicious activity by using advanced algorithms (i.e. machine learning and artificial intelligence) to get the job done.

### So...my antivirus program is useless?

No, your antivirus solution is not useless. In fact, it's probably one of your main lines of defenses when it comes to personal computer security. I've mentioned in a previous article about **defense-in-depth**, which is essentially a strategy for securing your network at various levels. For individuals, having endpoint security (i.e. antivirus) has been the most basic form of cyber security that has been available to us for quite awhile. Companies like Norton and McAfee have been leaders in the antivirus software space for over 30 years. 

If you want to protect your devices from common types of malware and virues, an antivirus program is definitely needed. The market has grown significantly to the point where there are antivirus programs for all operating systems(windows, mac, linux) and device types (laptop, phone, etc.). Doing a bit of research, you can find the right antivirus program for you. Many companies will also include extra things like VPN, password managers and firewalls in addition to the antivirus program. We've gone over some of those topics in other articles ;)

The hard truth is that antivirus programs will not be able to stop everything. However, when it comes to evaluating risk and forming depth in your defenses, they are pretty damn good at what they do. [Here is a website](https://www.av-comparatives.org/) that evaluates different vendors and scores them based on their performance. You can get a sense of which antivirus programs are worth buying and how they stacked up against each other. As always, using proper cyber hygiene will reduce the risk of running into viruses out there on the internet. 

Hopefully after reading this article you have a better sense of how antivirus software works. As new threats emerge, the market for these kinds of programs will have to shift to match the needs for cyber security. The technology itself wlll also have change to address these threats and properly be able to stop them from happening. Proactive threat responses are becoming normalized in the industry, whereas reactive responses are struggling to have a seat at the table. This isn't to say that reactive technology is useless, but more needs to be implemented to properly secure systems going forward in the future. 

Thank you for reading! 

