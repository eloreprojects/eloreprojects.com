---
layout: post
title: "A Guide to Password Systems"
categories: Software Engineering
description: "How to implement your application’s first and final line of defense."
---

*[This piece was originally published in HackerNoon. Code examples and images included.](https://hackernoon.com/a-6-minute-guide-to-password-systems-52f1857dc0ec)*

![A lock and door](https://cdn-images-1.medium.com/max/2000/1*4IwGiQ87DWBXokwsO9MWsw.jpeg)

_“There are two kinds of cryptography in this world: cryptography that will stop your kid sister from reading your files, and cryptography that will stop major governments from reading your files.”_ - Bruce Schneier

Dutch cryptographer [Auguste Kerckhoffs](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle) once said that a system should be secure even if everything is known about the system other than its key. In the case of the internet, with web applications serving as the system, passwords have become the new key. It’s not a stretch to say that your most valuable information is probably hidden across all your social media, cloud storage, digital banking and so forth. So, the first and final line of defence between you and digital burglars potentially highjacking your life is none other than your password.

News publications all go **bananas** over security breaches, yet security is often the most daunting task for beginners in back-end development. This guide aims not to provide backend code, but to provide new developers a skeleton for password systems.

## Hashing
The foundation of any good password system lies in its use of hashing algorithms. So what is a hashing algorithm?

A hashing algorithm is a function that when inputted a string of arbitrary size will produce a fixed length string. More simply, a hashing algorithm is a one-way function that converts any text of _any size_ into text with the exact same length each time.

This is made possible by altering and construing the input text until it does not even remotely resemble the original string. For example, the commonly used SHA-256 algorithm _always_ produces outputs of 256 bits for a total of 2^256 possible outputs. As a result, it’s radically difficult to create collisions - when two different input strings produce the same output. In fact, there is a chance of 1 in over 115 quattuorvigintillion (that’s a real number; it’s 78 digits long) to produce a collision. 

Hashing algorithms are used in practically every secure authentication system on the planet. 

Instead of storing a plaintext password in a database when a new user is created, a hash of the password is stored instead. Whenever that user later logs in, whatever password they log in with is hashed and compared with the original password’s hash to verify the user. This is because even if a hacker was able to break into a database and view its contents (which happens more often than you’d think), a hash effectively hides every password _even if_ the hacker knew which hashing algorithm was used. Kerckhoffs would be proud.

Some things to remember:

1. A hashing algorithm will produce the same output for the same input.
2. A slightly different input will produce a completely different output.
3. A good hashing algorithm minimizes collisions.

Or just use bcrypt (covered in final section).

## Good Passwords
First, what makes a secure password?

The best passwords aren’t necessarily the ones that include both numbers, capital and lowercase letters, and special characters. Neither are passwords over 8-10 characters. Instead, what these web guidelines do is encourage users to expand _variation_ in passwords to (hopefully) create a one-of-a-kind password. The best passwords are the ones that nobody has ever used before. Here’s why.

Let’s do some quick math. 

Using 10 characters, your standard 26 lowercase characters will give you the option of 26^10 possible passwords. That’s a big number - 141,167,095,653,376 to be precise. However, we also have 26 uppercase letters at our disposal too (52 possible characters), which multiplies our total password count by **1000**. When you add special characters and numbers our total password count (barring conditions) is 59,873,693,923,837,890,000. 

That number is too astronomically large to even wrap your head around. A more understandable metric would be _how long it takes to crack a given password_. Using a raw SHA256 hashing algorithm, it would take about **738 thousand years** to brute force the entire key space. 

Seems secure enough? 
Yeah, right.

## Salting
Even though it’s impossible to reverse engineer a given hash, we have standardized hashing algorithms like SHA. 

This means that hackers can compile huge datasets known as **dictionaries** of common passwords and hash each password themselves to see if any of the corresponding hashes equal the original password hash. Another technique is to precompute the hashes of a dictionary and place them into a data-structure known as a lookup table, making it EVEN easier to determine the original password. Since large numbers of hashes can be computed only once and reused, these types of hacks can be efficient. 

The best way to combat this method of hacking is to use **salts**: additional random characters added to the password when hashing. Each password requires a different salt, but the plaintext salt can be stored right alongside the password. How is this secure? 

Salting protects your passwords because salting renders all the hashes stored in a lookup table useless, since using a salt will completely change the hash. Your passwords are (more or less) safe again.

## Hashes in the Real World
So can you just take SHA256 implementation, throw in a secure salt, and call it a day? Just hold your horses for a second.

Turns out you can’t just roll your own authentication. When the only limit to cracking your password is how fast CPU’s run (and CPUs get faster every year), your security system will start to resemble a ticking time bomb. To combat this, most modern authentication systems use a technique called **key stretching**.

(Use this analogy: a stretched out key takes longer to fit into a hole to check if it’s the right key)

How key stretching works is beyond the scope of this guide, but essentially the technique makes it extremely difficult for hackers to test out a bunch of hashes in a short amount of time by slowing down the hashing algorithm and forcing hackers to wait (relatively) long times before a hash is produced.

A popular implementation of key stretching is used in bcrypt, a password hashing function that has been developed specifically for passwords in 1999. In a world where technology quickly outpaces itself, the age of bcrypt is a testament to how powerful it is. Bcrypt is available in every language conceivable, from node.js to C. Bcrypt even generates a cryptographically secure salt to prevent rainbow attacks. Useful, right?

## Final Advice
Use libraries like bcrypt, use 2-factor authentication, follow emerging trends in network security, and penetrate test frequently.

If you learned anything from this guide, I hope its this: 

Never roll your own authentication. Your security isn’t just competing with hackers - it’s competing with other security systems since hackers can effortlessly apply the same hacking techniques from other attempts to your system.
- - - -
