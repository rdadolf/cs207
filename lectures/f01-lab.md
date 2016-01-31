---
title: Introduction to C Lab
layout: lecture
mathjax: true
---


## Q1: What to do while the data is away?

The Chrome web browser has a diagnostic tool which records the network loading times for any page you visit.
Below is a sample timeline for loading the CS207 homepage.

![Timeline]({{site.baseurl}}/lectures/f01/timeline.png)

It takes 108ms to retrieve all the page's data from the internet.

That's a *long* time for a computer to be waiting.
Let's figure out exactly how long by estimating what we could do with that time.

[AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard), the Advanced Encryption Standard, is a common cryptographic algorithm for securing data.
Let's say you've "acquired" a list of AES-encrypted passwords from a nefarious, trench-coat-wearing "friend".
While we're waiting for our page to load, let's set to work breaking these passwords.

The most common methods for password cracking involve guessing random combinations, encrypting them, and checking against the encrypted list.
To simplify things, let's assume that everything except the encryption is free.
So we need to know how many passwords we can encrypt in 108ms.

Since [2010](https://software.intel.com/en-us/articles/intel-advanced-encryption-standard-aes-instructions-set), Intel CPUs have had special hardware built in which can compute AES in just a couple of instructions.
Specifically, recent Haswell chips have an average decryption rate of [0.89 cycles per byte](http://www.intel.com/content/dam/www/public/us/en/documents/white-papers/haswell-cryptographic-performance-paper.pdf) for 256-bit keys.
If we assume that all your passwords are less than 11 bytes long, and that our processor runs at 2GHz, how many passwords can we try in the time it takes the CS207 webpage to load?

## Q2: Compiers
