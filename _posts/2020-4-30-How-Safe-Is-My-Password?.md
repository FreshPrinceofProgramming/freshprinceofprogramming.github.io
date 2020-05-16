---
title: "How Safe is my Password?"
categories:
  - General
---

This question is probably one that is most asked when it comes to ensuring your various accounts are secure. Hopefully after reading this you'll have a good understanding on what good passwords look like, how hackers actually crack your passwords and how you can stay secure. 

### Password: password 

I think we can all agree that using "password" for your password is not a good idea. Most websites won't even let you use that password without throwing in some numbers and symbols. But how are hackers able to figure out your password? It seems every other month there is a major security breach at a company, and millions of peoples' information is compromised, including site passwords. How is the website actually storing these passwords for protection?

When we talk about cyber security, one aspect of it that we are concerned about is the integrity of data. This means that we expect the orginal data that was sent, to be the exact same data that is received on the other end. If you've played the game "Telephone" as a kid in school, this is exactly the purpose of the game. The orginal phrase is passed down from kid to kid, and the last person has to relay the same information to see if the orginal phrase held true. Sounds easy, right?(Hint: It's not) Similar to how kids will purposely alter the phrase to be funny, hackers will alter data in mid transit to corrupt the integrity of the data for their personal benefit.

What does this have to do with passwords though? 

If we can manage to come up with a way to maintain the integrity of data in cyber space, we can effectively ensure that the data is kept in its original form without fear of it being altered OR diciphered. Let's talk about hashing...

### Password: 5f4dcc3b5aa765d61d8327deb882cf99

If you can't tell what the password is, then good(Hint: it's 'password'). As a matter of fact, this is what your password is converted to when it is stored on the database. This gibberish is called a "hash." A hash is an alphanumeric string that is a mathematical representation of a piece of data. There are many different hashing algorithms that exist to serve this purpose. Hash algorithms are one way functions that will take in some input and output the string. The above example is an MD5 hash, which is no longer considered secure.

Hashes have important properities that they must abide by in order to be considered secure:

1) Given a hash, it should be difficult to decipher the original message (remember, hashes are one way functions)
2) Hashing should always produce unique strings. This means that give 2 unique messages, the hashes produced should not be the same.

There are other properties, but we will focus on these 2.

In the first scenario



