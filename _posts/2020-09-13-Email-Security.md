---
title: "Email Security"
categories:
  - Privacy, Security & Safety
header:
  image: assets/images/email.jpg
---

Contrary to what you may think, email is actually the most common attack vector for hackers. Depending on the goals of the hacker, they will probably try to use email in some way to either compromise your machine and/or gain credentials to important accounts. After reading this article, you should have a good understanding of what these methods are, and how you can stay safe on your email platform.

### Really, email? 

I know, I know. It's not the most exciting platform, and probably the least "cool" when it comes to cyber security. Most people when they think of hackers, they imagine someone breaking through firewalls/the mainframe and doing a bunch of complicated things in order to achieve their goal. The reality though is that hackers are trying to work smarter, not harder. Why go through the long process of hacking a bank website for account information when you can target a specific user and have them give you the information? Sometimes, email may be the only way for a hacker to even gain a foothold into the network in order for them to continue their hacking campaign. 

### Let's go phishing

I'm sure you've all seen emails in your inbox that look a bit sketch. They might ask you to click on a link, download an attachment and/or provide some level of information in order to "verify" yourself. Some emails look very convincing, while others are obviously scams. In any case, this is called **phishing**. Phishing is an attempt through email to solicit information or get a user to do X action in order for personal gain. Phishing attemps are getting harder to spot and defend against. It doesn't matter how good your internal security is. If a user in your company clicks on a link that takes them to a portal where they input sensitive information, the hacker has essentially bypassed all security controls and can now start to do bad things. I'm going to show some examples of what these emails may look like, and how you can spot it.


#### Amazon "lock out"
![Amazon1]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_amazon1.jpg)

Here's an email I received from "Amazon" claiming that I'm locked out of my account because my billing information didn't match what was on my card. That's strange. To check, the first thing I did was log onto my Amazon account from the website itself, and **not the link they provided**. Not only am I able to log on, but my account information matches everything that is expected when placing an order. Right away this should give some context clues that this email is a scam. However, look at how the email is structured. It's got Amazon's logo at the top and all the right words that you might actually think would come from an Amazon representative. You might be tempted to click on the link provided under, "unlock my account." If you're still not sure whether this is a scam or not, there's another metric you can usually check...the actual sender's email address.

![Amazon2]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_amazon2.jpg)

Look at who this email is from. Very quickly this should raise some alarms. The "no-reply" address is coming from an unknown email address that does not immediately identify them as amazon in any way. I'd imagine that any kind of attempt to reach out to customers from an actual Amazon domain would be easily indentifiable. In this email, these people were trying to solicit my Amazon account information and potentially any billing info (credit card, billing address, etc.). If I had followed the link, I most likely would have been brought to a page that imitated an Amazon login page. Once I enter my credentials, it's game over. EMAIL DELETED 

#### Apple Thinks I'm Poor

![Apple1]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_apple1.jpg)

Well...I am poor, but chances are if you're a milennial reading this, you are too. But we're not so poor enough that we can't afford an apple account, which should sound very phishy to begin with. Apple does not charge you for having an apple account(they're free), unless you're paying for apps, buying extra storage for icloud, or purchasing some kind of apple product. If none of these apply to you, and you were to receive this email, you should automatically be warry. Let's give this email from "Apple" the benefit of the doubt though. It looks very legitimate, just like the Amazon email. Let's just get straight to the point and look at who's actually sending this email.

![Apple2]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_apple2.jpg)

Annnnndddddd there we go. Here's another "no-reply" email, and the address looks even stranger than the sender from the Amazon email. Look at the ".tk" suffix at the end of the email address. This is indicating the origin location of the email address, often refered to as a TLD or **Top Level Domain**. In this case, it's coming from the country "Tokelau." High key, I had to look where this country was. It's apparently a territory of New Zealand. Clearly, this is not associated with the Apple we all know and love. EMAILE DELETED

#### Paypal Shoe Plug

![Paypal]({{ site.url }}{{ site.baseurl }}/assets/images/rsz_paypal.png)

This phishing email actually looks pretty well done. In this email, "Paypal" is claiming that I've purchased women's shoes from Zappos, which is a shoe supplier. Similar to the other emails, it is structured in a way that is very believable. However, this email is doing something a little different that actually makes this a little more clever than the other two.

I have used Zappos in the past to purchase shoes, but none recently. However, I do use paypal on occasion. Looking at the shipping details, this becomes even more apparent that this appears to be fraudulent. My name isn't Christina, nor is that my billing info. Ok, so did they think I wasn't going to notice this? What's so clever about it? 

If you're not a frequent user of Zappos, like myself, and have a paypal account, this might catch your eye as to an obvious sign that something is wrong. Seeing how legitimate this email seems, it might be tempting to immediately click on the link provided to "verify your information and cancel the order." This is where the phishing step is actually orchastrated. This email was presented to us intentionally as a fraudulent purchase in order to trick us into giving our information to the hackers. Pretty damn clever! Of course we can always check the sender email too as in the previous examples.

![Paypal1]({{ site.url }}{{ site.baseurl }}/assets/images/paypal1.jpg)

This doesn't set off any bells or whistles, so it's unclear whether this could be legitimate or not, although an actual zappos "no-reply" would probably have the name inside. Probably the smartest thing to do would be to check your paypal account to see if there has been any activity. If you are a frequent user of Zappos, check that account as well and make sure any concerns are brought up with an actual representative. EMAIL DELETED

### Encrypting Your Emails

Now that we've seen some examples of external phishing attempts, let's talk about encrypting our emails and why you may want to start doing so. Let's suppose that now instead of being phished from the outside, the entire email database gets compromised. This would mean that the attacker could intercept the emails coming and going from the organization. Obviously, this isn't ideal and could pose a serious threat. All kinds of sensitive information is sent every day from organizations both internally and externally. However, more than likely if you work for a company, they are encrypting the emails you send internally to each other. If not, you may want to suggest this to the security team! 

What about personal emails though? Can you encrypt personal emails? Of course you can! Encrypting emails is a major part of certain email platforms. For example, google and outlook all provide some level of encryption that can protect emails from being read should they be compromised. This is great because if there is breach, unless the attacker has the proper keys, they won't be able to decipher the email in any readable way. You may also want to consider moving over to a non-standard email platform like **Protonmail**. 

[Protonmail](https://protonmail.com/) is a company based in Switzerland that provides email services, specifically end-to-end encryption. If you visit the website they'll explain what services they offer and how you can get started! You may want to consider this email service for your personal emails if you want some added layer of security. Some services may need the recipient to have installed something to make the encryption work both ways. Protonmail does not require that at all. You can send encrypted emails to anyone with a non-protonmail account. 

I'll have a seperate article on encryption and what this all actually does for data protection. For now, being safe on any email platform is going to be what we're focusing on, sans any encryption necessary or not necessary for that particular message. 


### How to Stay Safe

The three examples above are just a small amount of the kinds of phishing attempts out there. In more sophisticated attacks, you may see an email come from somone you know and trust. This attempt is called a **spoof**. Phishing is a form of spoofing but, but in spoofing the bad person usually will have compromised a legit email account. This makes it harder to differentiate the bad actor from the actual person. You'll typically see these kinds of attacks on companies, which may target high profile people in order to gain very sensitive information. Here are some things you can do to protect yourself on email to stay safe:

* Do not click on any links or attachments from emails you aren't expecting to receive or that look suspicious
* Always check the senders email address/email header information if you are suspicious about a particular email
* If the email is malicious/sketchy, report it to the main company through their security team OR your own internal security team if this is within your company
* Encrypt your emails if necessary, and make sure the other recipient has email encryption as well (may or may not apply to certain platforms)

Hopefully after reading this, you have a good sense of email security and how you can spot certain attacks. 

Thanks for reading! 






