---
title: "What is Encryption?"
categories:
  - What The Hack
header:
  image: assets/images/nickyoung.jpg  
---

Encryption is one of the most fundamental parts of modern computing. It's the reason why your credit card information isn't stolen every time you buy something online (well at least as infrequently as possible). So what is it? How does it work? Hopefully after reading this, you'll understand what it is, and why it matters when it comes to cyber security.  

### Fdq brx uhdg wklv?

In order to understand encryption, we first need to understand the greater field of **cryptography.** Cryptography, simply put, is the study/art of writing or solving codes. That's it. This fundamental idea of being able to either write and/or solve codes is the reason why modern computing exists in its current state. However, cryptography has existed for thousands of years before any electronic computer was made. In the example above, I used a **ceasar ciper**, which you might guess is named after Julius Ceasar, in order to encrypt the subject title. While it may look cryptic (yes, pun intended), this cipher or encoding method, is very simple to solve.

**Note:** From here on out we will refer to the message we want to encrypt (in its non-encrypted form) as **plaintext**, and the encrypted form of the message as **ciphertext.**
{: .notice--info}

The way that a ceasar cipher works is through a series of shifts or substitutions of the alphabet to a fixed position. In other words, all you're doing is shifting the alphabet by a certain number of characters to come up with your encoded message. For example, if we wanted to encode the plaintext, "Attack," here's what we would do:

1. First, we need a shift value to use. Let's use 3 as an example. This means that we're going to shift the alphabet 3 places forward to get the corresponding letter that will replace the original letter. A encodes to D, B encodes to E, etc.

2. Now let's take our phrase "Attack" and encode it using the shift. The result is "Dwwdfn." We now have our corresponding ciphertext

3. Done

That was very simple! The shift of 3 gave us a completely different string that can't immediately be deciphered as "Attack." The shift of 3 is also what I used in the subject title. If we work backwards, the corresponding plaintext value, "Can you read this?" is the result. As trivial as this encoding method is, history shows this is what Julius Ceasar was using to send messages to his military. Only the correct people knew the shift value and could decode the message appropriately. Here's a visual representation of what the substitutions may look like:

![ceasar]({{ site.url }}{{ site.baseurl }}/assets/images/ceasar.jpg)

Cool! So while being able to encode and decode a ceasear ciper is great, it's nowhere near the level of appropriate encryption needed today to secure data. 

We've already established a purpose or need for encryption from the example above; to keep data confidential. Whether you're sending out battle plans across the globe to your military generals or just trying to buy some clothes online, your data needs to be secured for privacy purposes. As simple as it sounds, there have been countless hours put in by many smart people (mathematicians, computer scientists...the government) over the decades in order to create encryption standards that keep our data safe. So how does it work?

### I'm the same as you! 

We can break down modern encryption into two categories; **symmetric** and **asymmetric** encryption. While both have their pros and cons, these two types of encryption are responsible for securing data in the real world today. 

One of the most important concepts of modern encryption is a **key**. This "key" can be any word, phrase or code that is responsible for encrypting plaintext and/or decrypting ciphertext. As you may have guessed by the naming conventions, symmetric encryption is going to use the **same** key for encryption/decryption, while asymmetric encryption is going to use **different** keys for the same purpose. In the case of symmetric encryption, we want to be able to send a message to someone securely using only one key. How would we do so?

Let's imagine that Alice wanted to send Bob a secure message, meaning that only Bob should be able to see what Alice sent. What might she do? Well, she could write her message, put it in a box, lock it with her key and then send it off to Bob. Once Bob has the box, he could unlock it by using the same key Alice used to lock it. This will have effectively have demonstrated symmetric encryption because the same key was used to lock (encrypt) and unlock (decrypt) the box. We can view an illustration of Alice and Bob below:

Alice sends a secret message to Bob using her key to lock the box
![symmetrickey1]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobsym1.jpg)

Bob receives the message and unlocks the box using the same key
![symmetrickey2]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobsym2.jpg)

Now while this is great, there's a huge problem in the example above that you may have caught onto; it's Bob. How does Bob have Alice's key to unlock the box? More on that in a bit....

The power of symmetric key encryption lies in its simplicity and quickness to encrpt and decrypt things that you want to keep secure. After all, there's only one key that needs to be used in the entire process. This is great for things like securing data at rest. Imagine if you had a file that you needed to secure locally on your computer. You could use a program that uses symmetric encryption to effectively encrypt that file. The most well known and secure (currently) symmetric encryption algorithm is called **AES**(Advanced Encryption Standard). 

To spare the history behind it, all you need to know is that it is an official government standard of securing data...like NSA government standard. A lot of companies use it to securely manage private data, and it is also used in securing data transmissions over the internet (in certain ways). I highly suggest looking into the details of AES (and other symmetric key algorithms) to see how they work. We're just scratching the surface in this article. In fact, the ceasar ciper in the previous section is a perfect example of symmetric key encryption; the "key" being the known number of shifts to use to encrypt and decrypt the message. 

### Actually, we aren't the same

Circling back to my previous statement in the last section, there's an obvious problem with symmetric key encryption. Both parties must have a copy of the same key in order to encrypt and decrypt whatever message is being sent over. Not only that, but the key **has to be kept secret** to the appropriate parties. In our above example of Alice and Bob, we assumed that Bob had the same key Alice did to unlock the box containing the message. But how? If you imagine the medium of travel for the box as the internet, this presents a security risk. We have to assume all communication paths are insecure. Alice cant just send Bob her key over without it potentially being compromised. This is where asymmetric key encryption comes into play.

Let's imagine now that Bob buys a padlock and key. Bob then sends that padlock (unlocked) to Alice, while keeping the key secret to himself. Alice receives the padlock and places a copy of her symmetric key in a box. She then locks the padlock on the box and sends it back to Bob. Because only Bob has the key to unlock his padlock, he can open it and receive the symmetric key. The two can now exchange messages securely by just using the same key to lock and unlock a box the box as in the previous example. Here is an illustration:

Bob sends Alice his padlock(unlocked) and keeps the key to it 
![asymmetrickey1]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobasym1.jpg)

Alice places a copy of her symmetric key in a box
![asymmetrickey2]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobasym2.jpg)

Alice sends box locked with the padlock to Bob

![asymmetrickey3]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobasym3.jpg)

Bob opens the padlock with his key and retrieves the copy of the symmetric key
![asymmetrickey4]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobasym4.jpg)

Alice and Bob can now send secret messages to each other using the symmetric key to encrypt and decrypt  
![asymmetrickey5]({{ site.url }}{{ site.baseurl }}/assets/images/alicebobasym5.jpg)

If you noticed, we didn't really "encrypt" any actual message data. All we did was ensure that the symmetric key was able to be exchanged by using asymmetric methods. In this example, the padlock Bob had represented a **public key**, meaning that it is known to both parties (and anyone else who needs it), while the actual key to the padlock represented a **private key**, something only Bob knew and had. Asymmetric key encryption, also known as **public key cryptography**, uses the idea of a public and private key in order to encrypt and decrypt messages. 

The reason why this method is successful in the real world is because both keys are mathematically linked to each other in a way that ensures that only the correct private/public key combination can be used to encrypt or decrypt messages. A user could use a recipients public key to encrypt a message, and only the recipients private key can be used to decrypt it, and vice versa. The most famous algorithm that uses asymmetric encryption is called **RSA**(Rivest–Shamir–Adleman). It has been around since the 1970's and still widely used today as a means to exchange symmetric keys between distant parties. It's the reason why your credit card data can be securely transmitted between the browser and server when you're shopping online. So it's very important to say the least. Like always, I suggest reading into how this is implemented in the real world and what's behind the algorithm. 

Asymmetric key encryption is also very slow. As you can imagine, there are 4 keys(2 public and 2 private per 2 parties) we now have to deal with and the overhead for generating them can be quite computationally intensive. This is why asymmetric algortihms are hardly used for actually encrypting message data. They can however ensure a symmetric key is generated and encrypted to be securely sent over an insecure medium such as the internet. But the actual encryption of data uses symmetric algorithms for that purpose. 

### Encryption visualized

I think it would be beneficial to see encryption in a real life example before we wrap up in the next section. 

I mentioned previously with asymmetric encryption (public key cryptography), that it can be used to ensure safe transaction of private data in the case of shopping online for example. You may heard the term **SSL**(Secure Socket Layer) or **TLS**(Transport Layer Security, aka the successor to SSL) mentioned when it comes to ensuring a website is secure. This is the "s" in HTTPS (hypertext transfer protocol secure). It is always encouraged that you only visit sites with https enabled, and encryption is the reason. 

But did you know that each website (most of them) that offers SSL/TLS has a way to verify the legitimacy of itself? Sounds weird, I know. Amazon.com is just amazon.com. It's got to be legitimate already, right? That's where you would be wrong. This is where **digitial certificates** come in handy. You can think of a digital certificate as proof or legitimacy by the website, which will offer key identifiers for every device that connects to it to confirm that it is actually amazon.com that you are connecting to. One of these proofs is the public key of the website. And we all know what that is by now...

I'm sure we've all seen the "lock" symbol at the top of the URL next to the site we're connecting to. It looks like this:

![amazoncert1]({{ site.url }}{{ site.baseurl }}/assets/images/amazoncert1.jpg)

Here it is telling us that this website is secured, and we can even see the spot for the certificate. If we click on the certificate, we get this page:

![amazoncert2]({{ site.url }}{{ site.baseurl }}/assets/images/amazoncert2.jpg)

This certificate is informing us that it proves its own identity as well as your identity when connecting to the website, which is owned by Amazon.com. It is very important that websites keep their certificates valid. They aren't cheap, but the benefits speak for itself. Hackers or bad actiors can use free certificates to make their websites look more legitimate and often can trick unsuspecting users to thinking the site is secure. 

We can take the certificate a step further and looks at details:

![amazoncert3]({{ site.url }}{{ site.baseurl }}/assets/images/amazoncert3.jpg)

See anything that looks familiar? The RSA public key! This isn't a hack or some lack of security. The public key is exactly what the name suggests, public. Anybody can see this. The private key is what is kept hidden and hopefully never exposed. I would look up more about digital certs and how websites use them. There have been [hacks against digital certifcates](https://resources.infosecinstitute.com/topic/cybercrime-exploits-digital-certificates/) in the past, and continues to be a potential avenue for hackers to exploit. Interesting stuff.

Now with all of that said, let's look at some Amazon encrypted traffic:

![amazoncert4]({{ site.url }}{{ site.baseurl }}/assets/images/amazoncert4.jpg)

Can you figure out what I was doing on Amazon? No, and that's the point. I used a packet analyzer to look at the traffic between my machine and the amazon website. This is what your traffic gets turned into when encryption is enabled properly. Unless a hacker has Amazon's or my private key, they can't decrypt the traffic.

### Putting it all together 

In the grand scheme of keeping things private, cryptography has a long history of people coming up with ways to securely be able to implement ways of doing so. In modern computing, it has allowed the secure transfer of data between unknown parties and has kept us relatively safe. However, encryption itself isn't completely secure. Think of it as a tool to achieve some goal. With any tool, if it's used properly you will see great results. But if used improperly, it can present high risk of being potentially exposed. 

Encryption is like a two-way sword; when it works, it really works. But that may mean it works too well in cases where you need to possibly get beyond the encryption to access certain information. Let me give an example: 

Let's say that you are an investigator trying to figure out information on a suspect's phone. The phone is locked with a passcode and there is a certain amount of attempts until the phone automatically wipes/locks itself permanently (a very common security measure for phones). To make matters worse, the suspect is deceased and nobody knows the passcode but them. Sounds like you have your work cut out for you. You cant just brute force your way into the phone, and the company that provided the phone has no way of accessing the data internally on it either. Sounds like a non-likely scenario, right?

But [that is exactly what happened](https://www.wired.com/story/the-time-tim-cook-stood-his-ground-against-fbi/) a couple of years ago during the investigation into the shootings in San Bernadino, CA. Essentially, the FBI needed to get into the iphone of one of the suspects and pressured Apple to do so. Apple refused and the FBI became frustrated. Eventually they were able to get into the phone, but due to the strong encryption on the iphone itself, we can see how this created a problem in the first place. Nonetheless it proved that encryption works. 

Trying to break various encryption protocols takes a lot of knowledge, time and persistance, but there are people who have proven it possible. The good news for us is that most high level encryption standards are still relatively safe. But remember, it's all about how you use encryption. If keys are improperly placed, key length is too short, or various other parts of the implementation are flawed, encryption will not help in trying to keep data private.

















