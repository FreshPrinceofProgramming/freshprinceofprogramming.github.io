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

That was very simple! The shift of 3 gave us a completely different string that can't immediately be deciphered as "Attack." The shift of 3 is also what I used in the subject title. If we work backwards, the corresponding plaintext value, "Can you read this?" is the result. As trivial as this encoding method is, history shows this is what Julius Ceasar was using to send messages to his military. Only the correct people knew the shift value and could decode the message appropriately. 

Cool! So while being able to encode and decode a ceasear ciper is great, it's nowhere near the level of appropriate encryption needed today to secure data. 

We've already established a purpose or need for encryption from the example above; to keep data confidential. Whether you're sending out battle plans across the globe to your military generals or just trying to buy some clothes online, your data needs to be secured for privacy purposes. As simple as it sounds, there have been countless hours put in by many smart people (mathematicians, computer scientists...the government) over the decades in order to create encryption standards that keep our data safe. So how does it work?

### I'm the same as you! 

We can break down modern encryption into two categories; **symmetric** and **asymmetric** encryption. While both have their pros and cons, these two types of encryption are responsible for securing data in the real world today. 

One of the most important concepts of modern encryption is a **key**. This "key" can be any word, phrase or code that is responsible for encrypting plaintext and/or decrypting ciphertext. As you may have guessed by the naming conventions, symmetric encryption is going to use the **same** key for encryption/decryption, while asymmetric encryption is going to use **different** keys for the same purpose. In the case of symmetric encryption, we want to be able to send a message to someone securely using only one key. How would we do so?

Let's imagine that Alice wanted to send Bob a secure message, meaning that only Bob should be able to see what Alice sent. What might she do? Well, she could write her message, put it in a box, lock it with her key and then send it off to Bob. Once Bob has the box, he could unlock it by using the same key Alice used to lock it. This will have effectively have demonstrated symmetric encryption because the same key was used to lock (encrypt) and unlock (decrypt) the box. In fact, the ceasar ciper above is a perfect example of symmetric encryption; the "key" being the known number of shifts to use to encrypt and decrypt the message.

Now while this is great, there's a huge problem in the example above that you may have caught onto; it's Bob. How does Bob have Alice's key to unlock the box? More on that in a bit....

### Actually, we aren't the same

The power of symmetric key encryption lies in its simplicity and quickness to encrpt and decrypt things that you want to keep secure. After all, there's only one key that needs to be used in the entire process. This is great for things like securing data at rest. Imagine if you had a file that you needed to secure locally on your computer. You could use a program that uses symmetric encryption to effectively encrypt that file. The most well known and secure (currently) symmetric encryption algorithm is called **AES**(Advanced Encryption Standard). To spare the history behind it, all you need to know is that it is an official government standard of securing data. A lot of companies use it to securely manage private data. I highly suggest looking into the details of AES (and other symmetric key algorithms) to see how they work. We're just scratching the surface in this article. 

Circling back to my previous statement at the end of the last section, there's an obvious problem with symmetric key encryption. Both parties must have a copy of the same key in order to encrypt and decrypt whatever message is being sent over. Not only that, but the key MUST be kept secret to the appropriate parties. In our above example of Alice and Bob, we assumed that Bob had the same key Alice did to unlock the box containing the message. But how? If you imagine the medium of travel for the box as the internet, this presents a security risk. Alice cant just send Bob her key over without it potentially being compromised by someone watching their communications. This is where asymmetric key encryption comes into play.

So we've already established that in order for Alice and Bob to communicate securely, both of them need to have the same key in order to lock and unlock the box. The problem is that the key needs to also be securely transmitted between both parties. How do we solve this?

Let's imagine now that Bob buys a padlock and key. Bob then sends that padlock (unlocked) to Alice, while keeping the key secret to himself. Alice receives the padlock and places a copy of her symmetric key in a box. She then locks the padlock and sends it back to Bob. Because only Bob has the key to unlock his padlock, he can open it and receive the symmetric key. The two can now exchange messages securely by just using the same key to lock and unlock a box the box in the previous example.















