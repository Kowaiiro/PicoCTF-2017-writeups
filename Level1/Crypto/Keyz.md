This is interesting

Tutorial on using shell:

Take a look on the shell on the right, connect to it.
You'll see 
```
your_username@shell-web:~$
```
The "~" sign means that you're in your home directory

try to make a directory, enter
```
  mkdir anyting
```
then, type
```
  ls
```
then there's a directory named "a"

to enter a, type
```
  cd a
```
you've entered the "a" directory.

Back to the problem, we see the description.

While webshells are nice, it'd be nice to be able to login directly. 
To do so, please add your own public key to ~/.ssh/authorized_keys, using the webshell. 
Make sure to copy it correctly! The key is in the ssh banner, displayed when you login remotely with ssh, to shell2017.picoctf.com

and the hints,

There are plenty of tutorials out there. 
This one covers key generation: https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html

Then, use the web shell to copy/paste it, and use the appropriate tool to ssh to the server using your key

Alright, the first hint will be useful in case you forgot or didn't know how to use the public key or register a new one.

1. Open your own terminal, in this case for ease, I use linux terminal. Type cd .ssh, if there's one. okay wait
2. if there isn't one there (and I think so), then make a new one. type:
```
    mkdir .ssh
    cd .ssh
```    
3. then, as instructed in the link embedded on hints, to register a new one, type:
```
    ssh-keygen -t rsa -C "your_email@example.com"
```    
    enter the directory, if left blank, it will use the default one.
    enter the password, if left blank, it will use the default one without password.
    take a look on where your identification and public key saved, defaultly in "/home/username/.ssh/" if you type the command when entering those directory
    then there is a random character, just take a look.
    then type:
```    
    ls
```    
    to check that there are:
 ```   
    id_rsa      id_rsa.pub
 ```   
4. There is id_rsa.pub, which is your public key. To view the content of the id_rsa.pub, just open in gedit, or nano, or cat it directly. I prefer cat.
  
