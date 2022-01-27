# The Frustrated CEO!

Author: Pratik Jallan

Flag: `cTf{fe21304838}`

## Problem Statement:

One fine day, Mr. Zuckerberg was busy dealing with the continous leak of user information from their databases, passwords were being compromised yet again. Stressed, he went to eat at Sha-e-darbaar, 3 turns from his house. He entered the restaurant and found his food to be lacking salt. He picked up the sprinkler and all of a sudden an idea struck him. Shouting 'EUREKA!', He finished his food asap, paid the bill of 512 usd and ran as fast as possible. After reaching home, he implemented his idea immediately.

As a hacker, surely you can't let this one slide. Crack Zuckerberg's new password to destory his peace! His old one being 'dadada!'. The flag format is cTf{first_10_characters_of_new_password}.

## Relevant files / links:

## Hints:

1. Does the restuarant name seem weird to you too, or is it just me?
2. Tired, Mr. Zuckerberg might have implemented his idea multiple times to enforce things... 

## Solution:

Suggested Difficulty: `Easy/Medium`

The question involves elementary application of `SHA-512` hashing, and concepts of salting, storing passwords etc. Companies never store our passwords directly but rather store their corresponding hashes, to protect user data even in case of security breaches. `Salting` is done in order to make the hashes even more difficult to understand. In salting, we append some random text to the the plaintext password and store their combined hash in the database. Doing this multiple times, by using the hash of the password as input for another hash, enforces security even more. This is known as `adaptive hashing`.

The question begins with some hinting towards storage of passwords in companies, Facebook being one of the best unsuccessful examples. The first hint and restaurant name gives us the hint of using SHA algorithm. `EUREKA!` is the salt here clearly, with 512 indicating the usage of SHA-512.

The second hint and 3 turns indicate that we must hash it two more times, to get the new password. The first 10 characters of the hash finally formed give us the flag.

The online tools that have been used in the question are as follows:

- [SHA-512](https://emn178.github.io/online-tools/sha512.html)
