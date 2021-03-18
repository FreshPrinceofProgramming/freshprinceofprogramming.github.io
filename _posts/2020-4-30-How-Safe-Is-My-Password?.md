---
title: "How Safe is my Password?"
categories:
  - Privacy, Security & Safety
header:
  image: assets/images/4eseqn.jpg
---

This question is probably one that is most asked when it comes to ensuring your various accounts are secure. Hopefully after reading this you'll have a good understanding on what good passwords look like, how hackers actually crack your passwords and how you can stay secure. 

### Password: password 

I think we can all agree that using "password" for your password is not a good idea. Most websites won't even let you use that password without throwing in some numbers and symbols. But how are hackers able to figure out your password? It seems every other month there is a major security breach at a company, and millions of peoples' information is compromised, including site passwords. How is the website actually storing these passwords for protection?

When we talk about cyber security, one aspect of it that we are concerned about is the integrity of data. This means that we expect the orginal data that was sent, to be the exact same data that is received on the other end. If you've played the game "Telephone" as a kid in school, this is exactly the purpose of the game. The orginal phrase is passed down from kid to kid, and the last person has to relay the same information to see if the orginal phrase held true. Sounds easy, right?(Hint: It's not) Similar to how kids will purposely alter the phrase to be funny, hackers will alter data in mid transit to corrupt the integrity of the data for their personal benefit.

What does this have to do with passwords though? 

If we can manage to come up with a way to maintain the integrity of data in cyber space, we can effectively ensure that the data is kept in its original form without fear of it being altered OR diciphered. Let's talk about hashing...

### Password: 5f4dcc3b5aa765d61d8327deb882cf99

If you can't tell what the password is, then good(Hint: it's 'password'). As a matter of fact, this is what your password is converted to when it is stored on a database. This gibberish is called a **hash**. A hash is an alphanumeric string that is a mathematical representation of a piece of data. Hash algorithms are **one-way functions** that will take in some input and output a string. This is different from encryption algortihms, which are **two-way functions**(encrypt and decrypt). There are many different hashing algorithms in existence. The above example is called an [MD5 hash](https://searchsecurity.techtarget.com/definition/MD5). 

Hashes have certain properities that they must abide by in order to be considered secure:

* Given a hash, it should be computationally difficult to decipher the original data. Remember, hashes are one way functions. There is no "dehash" method.
* Given a hash, it should be hard to find a different input with the same resulting hash. Hashing is unique in the fact that adding or subtracting even one 1 byte of data from the input can dramatically change the entire hash string output.

There are other properties to hashes, but we will focus on these two.

### Password: BruteForce/DictionaryAttack45@@@

The first property seems pretty straightforward. Nobody should be able to dicipher the orginal data given a hash string. However, while hackers can't reverse engineer a hashed password, they can be clever and compare known hash values to their corresponding plaintext strings. 

Let's say a hacker was able to obtain hundreds of hashed passwords from a database. The goal is to try to crack these passwords in order to obtain their plaintext form for a given username. Typical hacker business. The hacker sees the hash for 'password' (5f4dcc3b5aa765d61d8327deb882cf99) in the database. How do they crack it? 

One thing they could do is generate hashes in real time of every possible combination of letters/symbols. They then could compare the hash that they're trying to crack with one of the hashes they just generated. When it matches, they can see which plaintext combination caused the hit. This is called a **brute force** attack. It's exactly how it sounds. You're going to try EVERY single combination in order to eventually get the result you want. 

In our example, a hacker could generate hashes for all 8 character lower case strings without numebrs or symbols. Eventually, they will generate the hash for "password". This assumes a lot of prior knowledge of the password beforehand, most notably length, which is definitely not something hackers always have. Can you imagine if the hacker didn't have this knowledge? They would have to start with 1 character and work their way up to 8 characters of ALL possible permutations of lower case letters.

This might take more time than we anticipated. As we can see, we trade off time for plausibility of cracking the password. Let's be clear, brute force will always work, but there's no gurantee it will be in a reasonable amount of time. Hence, this is why difficulty of deciphering the original data from a hash is an important property. There has to be a potentially faster way of doing this...

Let's go back to our example. So brute forcing is out of the picture because it takes too long. What if the hacker already has a list of thousands of different plaintext passwords? They could just run through the list, compute the hashes for every entry and then compare it to the hash they're trying to crack. Seems easy right? This is called a **dictionary attack**. The hacker is using a list or dictionary of values that they believe may be one of the passwords. This can be much faster than generating our own string combinations in real time. 

The downside to this attack is that it assumes the password is in the list the hacker has. If it's not in the list, then this attack is not going to work. This is why when perfomring a dictionary attack it's important to have a good password list. Believe it or not, there are lists you can find on the internet of common passwords that people use. The attack can only be as good as the dictionary used. Though this can be faster than brute force attacks, the hacker could also find it very difficult and time intensive to use many different dictionaries to find the password.

Wow that was just the first property. All this hacking and failing may leave the hacker a bit salty...

### Password: CanYouPassTheSalt?156*&

The second property is where things get tricky. Imagine you had a password database full of hashes. It wouldn't be unfair to say that at least two people more than likely share the same password. How could you tell? If you trust the second property holds, you know that if you happen to see at least two of the same hash, it probably means it's the same exact input. This means a hacker could see this as well. Obviosuly, this is bad. Let's look at the case where Alice and Bob share the same password:

* Alice's password: (password) 5f4dcc3b5aa765d61d8327deb882cf99
* Bob's password: (password) 5f4dcc3b5aa765d61d8327deb882cf99

In defenses against hackers, our goal is to frustrate them as much as possible and not give obvious hints where and how to attack. How can we address this issue of two people sharing the same password? Trusting the second property again, what we could do to change the hashes is add a bit of **salt**(some pre-computed value) to the original password in order to change the hash entirely. Remember, adding just 1 byte of data to the input will change the hash. We can prepend OR append this value to the original password.

* Salt value: dontcrackme3456
* Alice's password with salt: (dontcrackme3456password) 760271f1349c0484a4ecaf53e161253e
* Bob's password with salt: (passworddontcrackme3456) 94ccd5cc971a0ffd0745cd5672452d84

As we can now see, we've effectively solved the problem of two people sharing the same password. In Alice's case, the salt value was prepended to her password, whereas Bob's was appended. Both hashes are different, and there's no way a hacker would be able to know these two people shared the same password, let alone use a dictionary or brute force attack in any reasonable time to crack the password. Take that statement with a grain of salt...haha ;) 

This example was pretty simple and defintely not indicative of any real industry security standard for actual salt + hashing techniques for safely storing passwords. However, this is what SHOULD happen to your password on the backend when you create one for a website. Different salts are used for every user and are generated randomly and securely. This is why password cracking is incredibly difficult, but not impossible. 

### Ok...but is my password safe?

Whew...ok now we get to the actual point of the article. The answer is, it depends....

In the attacks for cracking passwords, I mentioned that length of your password was something that hackers don't always have prior knowledge of. This is very important. As computing power becomes more powerful and accessible to the public, password cracking is becoming faster. It's not a coincidence that websites have requirements for passwords such as 8 characters upper and lower case + numbers + symbols for example. What they're really trying to do is increase the computational complexity that a computer has to go through if it's attempting to generate a hash to crack the passwords. 

The shorter and less complex your password is, the easier it is to crack. In our example with 'password' as an 8 character all lower case string, it actually won't take that long to bruteforce its hash. It would take about 4 hours or less with a good GPU. However, if you use a 20 character alphanumeric + symbols password, you've exponentially increased the time it would take to crack that hash. There's a certain amount of trust with the website you authenticate with, and hopefully they are doing everything on their end to store your passwords safely, regardless of any length you put on a password.

It can be really hard to come up with a long and complex password that you'll A) remember and B) know is secure. This is why it is highly recommened that you get a **password manager** in order to increase your own security posture. Not only will a password manager make your life easier in storing all of your passwords, they also can be used to generate secure passwords based on any criteria needed by the user. This also makes it easier to change passwords if there is any kind of compromise on a website, which you should already be doing every couple of months to keep your accounts safe. Easier said than done :p Consider getting one! 

Some popular password managers:

* KeepassX
* LastPass
* 1Password

I recommened looking these up and see which one works for you. Most have free versions and are compatible with most OS's. There may even be a mobile app version as well. 

Thanks for reading! 










