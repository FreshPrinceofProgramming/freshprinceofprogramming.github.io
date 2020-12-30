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

One of the most important concepts of modern encryption is a **key**. This "key" can be any word, phrase or code that is responsible for encrypting plaintext and/or decrypting ciphertext. You can think of this key as like a lock box key. If you wanted to store somethign in the box and secure it, you would use the key you have to lock the box AND unlock it when you need to. 












