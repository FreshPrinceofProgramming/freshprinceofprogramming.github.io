---
title: "Are Antivirus Programs Obsolete?"
categories:
  - Privacy, Security & Safety
---

As you're probably aware, cyber security has largely been commodified, which means there's a whole bunch of products that companies are selling to try to get you to enhance your cyber security posture. This includes things like antivirus software. But is antivirus software still relevant in 2021? And if so, which one should you buy? In this article, we'll go through what exactly these programs do to protect you, if you should buy one and the larger implications they have on cyber security. 

### Can I have your signature?

In order for an antivirus program to be successful it needs to catch viruses. Well duh...but how exactly are viruses caught? You can't throw a pokeball at it and it's contained. With the vast amount of virus types out there, it would be great if we could identify them based on previously seen viruses that we know exist. If an antivirus program sees, what it suspects to be, a virus come in and it matches a virus in the database, it can quickly identify it as malicious. This is called a **signature based approach**. 

Malware/virus researchers will try to reverse engineer a new virus they see, figure out its behavior and then create a signature for it. You can think of a signature like a footprint or some other labeling that can help to identify it in the future. A signature is usually made up of particular data points in the virus code that could contain the malicious behavior. The signature is then put into a database of other known viruses of the antivirus program. If this virus is seen in the future by the program, it will know to block it and/or remove it from your computer. 

This is a great way to approach the problem of needing to block known threats. However, this is not useful if a new virus is introduced that has no signature in the database. You can probably imagine the amount of viruses that have no signature are pretty high. This is where signature based detection falls short. The databases for signatures are also constantly growing, so it is crucial to consistently have your antivirus progrm updated. As we can see, it's not feasible to keep this method as a main line of defense. How can we enhance our detection capabilities?  

What if we could modify our antivirus to look at the suspected virus from the inside out? Remember, a virus is just computer code that has the rules and properties for how that particular virus is going to function. We could have the antivirus program analyze the coding structure and decide whether or not it is malicious based on what it finds. This is called a **heuristic based approach**. 

This kind of approach is similar to a signature based one, with a few exceptions. Heuristics will attempt to analyze a virus, much like a researcher would, but instead of looking for a signature, it will look for coding structures that are known to be malicious. For example, let's say a new virus comes out that has not been signatured. Normally in this scenario, a standard antivirus program wouldn't pick it up. However, with heuristics it can see that the coding structure follows a pattern that it has already identified previously as malicious. 

This is very powerful, because now we can expand our antivirus program to detect a lot more "unknown" viruses that have not been fully studied and signatured. You might be thinking, "Ok, well it sounds like we're done here," but of course we aren't. Heuristic based approaches are not perfect either. Let's say this is a heuristic for a coding structure that is malicious: A-B-C-D. If the virus creator is smart and knows that's what the antivirus looking for, they can change the coding structure: A-C-D-B. Now our antivirus program will not pick up that virus with heuristics because that pattern doesn't exist in the database.

Heuristics can also generate more **false positvives** than intended. A false positive, in the context of an antivirus, is what happens when something is identified as malicious, but it actually is harmless. There are viruses out there that mimic legitimate programs, and may cause the antivirus to think that the legitimate program is harmful. The silver lining is that antiviruses that use a combnination of both signature and heuristic based techniques can stop a quite a lot of bad stuff out there. We can stil do better though. But how...?

### Your behavior is appalling

So by now you know that antivirus programs use signature and heuristic based approaches to protect you from threats out there. What other ways are left to find threats? Let's talk about **behavioral based approaches**.

First, let's back up and think about this more practically. If you were a detective trying to pinpoint a suspect, what might you do? You could look in your database and determine whether they 




