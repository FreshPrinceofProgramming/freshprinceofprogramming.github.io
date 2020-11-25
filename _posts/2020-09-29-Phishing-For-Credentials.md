---
title: "Stealing Facebook Credentials"
categories:
  - Hacking
---

In this article we're going to see how we can use some hacking tools to create a fake website in order to gain user credentials for Facebook. This is just a proof of concept more so than an actual hack. I'm not trying to go to jail ;)

### Scenario

We want to gain a user's Facebook login credentials. If we get these credentials, we can potentially log in ([if 2FA isn't enabled](https://freshprinceofhacking.github.io/privacy,%20security%20&%20safety/2FA/)), and find out all there is to know about our victim on their facebook page. With this information, we can possibly form more attacks for our benefit at a later stage. 

### Concept

**Social engineering** is the art using deception for the purpose of fraudulently gaining sensitive information. An example of social engineering is pretending to be someone in order to illicit a certain response. This can be in real life OR in cyber space. 

Example: If I'm working in the front building of a company, I may let through a wide variety of people throughout the day. Suppose a hacker came into the building, announced to me that they were trying to get further into the building to find a server room to do their malicious deed. I'm probably not going to let them through, and most likely I'm going to call the police. 

Now let's say this same hacker pretended to be a UPS delivery driver. They could easily walk in and say they have to deliver a package for a certain floor. If I'm not doing my job correctly and verifying their identity properly, they could gain access. They would have effectively bypassed the physical security protocol of not allowing any unauthorized people in the building. 

Of course there are more clever ways of using social engineering. In this case, we want to fool the user in believing that the request for logging into their facebook account looks legitimate. Easier said that done...


### Tools Used

* Operating System: Kali Linux 
* VirtualBox for emulation of Kali Linux
* SET (Social Engineering Toolkit) for creating our phishing scam: comes installed in Kali Linux 

### The Attack

The first thing we have to do is fire up Kali Linux and make our way to the command line. We're then going to launch SET. The command should just be: "setoolkit" (without quotes). Depending on your version of Kali or whatever OS you're using, you may have to run it as sudo first: "sudo setoolkit"

You should see this screen when the program starts:

![SETmain]({{ site.url }}{{ site.baseurl }}/assets/images/setmain.png)

As you can see, SET comes with a bunch of options. We're going to focus on the first option, which is the Social-Engineering attacks. Enter "1" at the prompt and press enter on your keyboard. 

You should now see this screeen:

![second]({{ site.url }}{{ site.baseurl }}/assets/images/secondpage.png)

Again, we see a lot different options for the different kinds of attacks we can perform. This is a VERY powerful tool, and if you know what you're doing (or don't for that matter), you can do some malicious things. Because we want to focus on a website for this specific attack, we're going to choose the second option on the list. Enter "2" and press enter on your keyboard. 

You will be on this screen next:

![third]({{ site.url }}{{ site.baseurl }}/assets/images/thirdpage.png)

Ughh another screen with yet more options. This time just select "3" and press enter.

"Are we done with the screens yet?" NO >:(

![fourth]({{ site.url }}{{ site.baseurl }}/assets/images/fourthpage.png)

We're getting closer! We now have options to specify the different kinds of sites we can choose to try duplicate. Depending on the creativity of the user, they may have a custom site that they want to use for this attack. For us, we're lazy and we just kinda want the tool to do everything for us. So we're going to choose the second option and hit enter on the keyboard.

Here is the final screen we need to worry about:

![fifth]({{ site.url }}{{ site.baseurl }}/assets/images/fifthpage.png)

Now here's where we do the actual cloning of our target site. You'll notice some disclaimers about the IP address you'll need to put in for this part. For our proof of concept, we're not concerned with having a publicly facing cloned site of facebook.com (more on this later). To make a long story short, you'll need to put in the private IP of your kali linux instance. The reason for this is because we need to set up a callback for the cloned site to be routed to, and the private IP of your kali machine will be used for this purpose. The program has been nice enough to get that for us (10.0.0.208). Enter in your machines private IP and then hit enter.

The next piece we'll need to put in is the actual website we want to clone. In this case it's facebook.com. Make sure to enter in the full address for the website (i.e. include the 'https://'). Once you enter in the website, you can hit enter on the keyboard. You'll see notices on the program saying that it's cloning the site. For me this took about a minute to do, but this may take longer for others. You'll know it's complete when you see the "information will be displayed to you as it arrives below" prompt from the program. Now is where the fun starts....

So we just cloned the facebook.com login page. Let's see what it looks like. Take your private IP address and enter it into a browser on any device on your local LAN (will not work if you didn't set up bridged mode for your network settings on your kali machine).

Here is the resulting page:

![sixth]({{ site.url }}{{ site.baseurl }}/assets/images/sixthpage.png)

Wow this looks really good! The site cloner that the program used really made this website look more legitimate than expected, which is great. I've already entered in some fake credentials to the login page for this example.

Remember, what we're trying to do is get password information from this user. At this point in the attack, you will have successfully gotten the victim to your fake website. All there is to do is wait until we see them attempt to login. Once they enter in their credentials and login we'll have them trapped. If we look back to the program, some interesting results come in.

Here is the program after the credentials have been entered:

![seventh]({{ site.url }}{{ site.baseurl }}/assets/images/seventhpage.png)

We can see the email and password used to authenticate to the website. From the victim's perspective, the login did not work and they will be automatically redirected to the real facebook.com login page. Assuming they don't think anything is wrong, they'll just log in again and go about their business. As the attacker, you can leverage this information to attempt to log in as that user. Chances are the victim is probably using this password for other online accounts too. 

We're done! But let's unpack what we just did...

### Conclusion

Hopefully now you're able to see how easy it is to set up a fake website to solicit credential information. As mentioned before, this is strictly a proof of concept. There's a lot the actual social engineering piece that we didn't go over. The reason for this is because there are quite a few different scenarios that we could have presented to our victim to get them to actually go to our website. 

As it stands now, this attack will only work on the LAN that you are on. This means that people that are not connected to the wifi you're on (the greater internet), will not be able to see the site. This isn't very useful if your target isn't in the same geographical location. Here's what an attacker might do to make this look more legitimate:

1. This is the perfect scenario for a phishing attempt. An attacker may buy and/or create a fake email domain that looks like it's coming from facebook. Remember, in social engineering we're trying to pretend to look like a legitimate source. If we can get a hold of a compromised facebook email or create one that looks good enough, it may be our ticket to getting the victim to trust us. 

2. The attacker will also probably utilize a bunch of different website domains to shuffle through to point their publicly facing attack server, which can then be used as the connecting site for the victim to go to. Often times for attackers, it's in their advantage to have a variety of website domains to cycle through in case they get shut down for whatever reason. They can also utilize compromised machines to do various activities as well, so the possibilities are endless. 

3. The attacker will craft the email to make it look like the victim needs to login to facebook for some purpose. If this is wide ranged attack, SET can also be used to mass send emails to many different people. A common phishing attempt may look like it's coming from the security or IT team from that organization claiming that you need to enter in your credentials for them to help. 

4. Once the victim clicks on the link (attacker could also obscure the link to not have it seem as obvious as a fake website) and enters their information, it's over. 

This is just one scenario of many that could be used to conduct these attacks. In any case, it doesn't take an advanced hacker to be able to get these attacks out there. The best way to defend against any of these attempts is to first always verify the website you are connecting to. If you do not see "https" in the browser, do not authenticate to that site, even if it claims it's legitimate. The second thing to do is never click on any links or attachments in emails that you do not trust. I have an [email security](https://freshprinceofhacking.github.io/privacy,%20security%20&%20safety/Email-Security/) article that goes into how to spot these kinds of emails. The last thing to do is always be aware of what you're doing. Common sense goes a long way protecting yourself agains cyber attacks. Hopefully by reading the other articles in this blog, you'll have a better understanding of what to look out for. 

Thank you for reading!


