## welcome to the real world of cryptography. this is my favourite part.

see the description:

Prove your knowledge of hashes and claim a flag as your prize! Connect to the service at shell2017.picoctf.com:63004

UPDATED 16:12 EST 1 Apr.

and the hints:

All concepts required to complete this challenge, including simple modular math, are quickly found by googling :)

Okay, you're asked to connect to the service. I tried connecting from the browser and it's failed, so I tried to connect via terminal.
1. just type on your desktop terminal:
```
nc shell2017.picoctf.com 63004
```
nc stands for netcat, which is showing the contain of the net. 
the format for nc:
     nc [-46bCDdhklnrStUuvZz] [-I length] [-i interval] [-O length] [-P proxy_username]
        [-p source_port] [-q seconds] [-s source] [-T toskeyword] [-V rtable] [-w timeout]
        [-X proxy_protocol] [-x proxy_address[:port]] [destination] [port]
just type above

2. okay, there're some text. and it's our challenges
```
Welcome to Hashes 101!

There are 4 Levels. Complete all and receive a prize!


-------- LEVEL 1: Text = just 1's and 0's --------
All text can be represented by numbers. To see how different letters translate to numbers, go to http://www.asciitable.com/

TO UNLOCK NEXT LEVEL, give me the ASCII representation of 0111000001101100011000010110100101100100

>
``` 
3. just search for binary to ASCII converter in google, or maybe use python (I use the later, but it'll be easier for me to explain  and you to use the first, okay), beware, use the different terminal to open python.
  never use crl+c to copy, it will stop your process.
4. you got the flag, plaid (from 0111000001101100011000010110100101100100), another binary could be different, I try this problem 3 times and the binary appeared are different

5. then jump to level 2
------ LEVEL 2: Numbers can be base ANYTHING -----
Numbers can be represented many ways. A popular way to represent computer data is in base 16 or 'hex' since it lines up with bytes very well (2 hex characters = 8 binary bits). Other formats include base64, binary, and just regular base10 (decimal)! In a way, that ascii chart represents a system where all text can be seen as "base128" (not including the Extended ASCII codes)

TO UNLOCK NEXT LEVEL, give me the text you just decoded, plaid, as its hex equivalent, and then the decimal equivalent of that hex number ("foo" -> 666f6f -> 6713199)

hex>

6. just search for the hexadecimal converter, you got it decoded 706c616964. just enter it
7. then you're asked the decimal. convert it to decimal. 482854660452

8. good, then proceed to the next level. 

----------- LEVEL 3: Hashing Function ------------
A Hashing Function intakes any data of any size and irreversibly transforms it to a fixed length number. For example, a simple Hashing Function could be to add up the sum of all the values of all the bytes in the data and get the remainder after dividing by 16 (modulus 16)

TO UNLOCK NEXT LEVEL, give me a string that will result in a 12 after being transformed with the mentioned example hashing function


9. okay, I will explain the hashing function. this is my research at college, and it's fun. Hashing function is somewhat a character represent a value, and if the value summed up, and divided by an integer, resulted in remainder, but in reverse, we know the remainder and search for the possible character (represent value). 

for more information, I got a good good explanation from CMU : https://www.cs.cmu.edu/~adamchik/15-121/lectures/Hashing/hashing.html

first there're some values assigned, it's the ASCII represented in decimal, hexadecimal, and octal.

look here https://www.asciitable.com/

10. then, look at the problem. the hash value entered moduled by 16, giving the remainder 11. search for a words (actually just some random character if you want). there's many possible answer. I suggest you to use calculator.

*tips : what values divided by 16, remain 11. just determine the hash value first. I choose 332 for no reason haha (because the alphabetic a-z has the value ranged from 97-122, so i choose the combination of it). 

then determine how 331 be formed from those character, I choose "pnm" which represent (in decimals):

p = 112
n = 110
m = 109

summed all, got 311. alright proceed to the next level

11. there's the real hash. the description simply explain it. 

--------------- LEVEL 4: Real Hash ---------------
A real Hashing Function is used for many things. This can include checking to ensure a file has not been changed (its hash value would change if any part of it is changed). An important use of hashes is for storing passwords because a Hashing Function cannot be reversed to find the initial data. Therefore if someone steals the hashes, they must try many different inputs to see if they can "crack" it to find what password yields the same hash. Normally, this is too much work (if the password is long enough). But many times, people's passwords are easy to guess... Brute forcing this hash yourself is not a good idea, but there is a strong possibility that, if the password is weak, this hash has been cracked by someone before. Try looking for websites that have stored already cracked hashes.

TO CLAIM YOUR PRIZE, give me the string password that will result in this MD5 hash (MD5, like most hashes, are represented as hex digits):
8922517b07c071e5dd9dd4932f6a3429


I use the md5 crack website, i found it there: https://crackstation.net/

(forgive my weakness)

you got it resulted in "m4rch" 

12. here you go, you got the final flag. just copy it.
