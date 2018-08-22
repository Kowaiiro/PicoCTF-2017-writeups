# Digital Camouflage

First, you need to open the description, there are 

"We need to gain access to some routers. Let's try and see if we can find the password in the captured network data: data.pcap."

and hints

"It looks like someone logged in with their password earlier. Where would log in data be located in a network capture?"
"If you think you found the flag, but it doesn't work, consider that the data may be encrypted."

Okay, download the data.pcap, just take a click on it. Dont be afraid, I'm here for you.
Beside, there is a unix shell, you may use it, but I don't in this problem. just explore it and you'll find nothing. tsumaranai desu nee.

1. The first step to exploit the data.pcap, is to open the file. I use wireshark
2. To obtain the password, just thinking about a big picture of a website, and you need a login to enter it to gain access for the router.
   Whatever is it, I'm thinking about username and password
3. Then, to simplify, in the filter box above, search for HTTP
4. Take a look in the Hypertext Transfer Protocol section in the middle, I mean, it's what we're searching for the password. 
5. Then there is a bar with no, time, source, destination, protocol, length, and info. Take a look on this, specifically on info.
6. Use your intuition, skip the unnecessary row of those in number 5, if there's no password or username there that's not what we're searching for.
7. I found in:
```
   72	42.071533	10.0.0.5	10.0.0.1	HTTP	108	POST /pages/main.html HTTP/1.1  (application/x-www-form-urlencoded)
```
   and in the middle section, on the Hypertext Transfer Protocol:
```
   POST /pages/main.html HTTP/1.1
  Referer: 10.0.0.1:8080/index.html
  User-Agent: User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:44.0) Gecko/20100101 Firefox/44.0
  Accept: text/html,application/xhtml+xml,application/xml;q=0.9*/*;q=0.8
  Host: 10.0.0.1:8080
  Connection: Keep-Alive
  Content-Type: application/x-www-form-urlencoded
  Content-Length: 42
  Accept-Language: en-US,en;q=0.5
  ```
  U find that this is what we're searching for. It's a kind of activity of accessing some stuff on the internet
  
8. Almost there, below there's 
```
  Line-based text data: application/x-www-form-urlencoded
  ```
  extend it,
  ```
  userid=stevensj&pswrd=UjZBS05oV3dvNw%3D%3D
  ```
  You only need the password. I enter it but not flag. Just realize that "%3D" is "="
  You got the flag, UjZBS05oV3dvNw==
  but again, not a flag 

9. Remember on the hint,
  "If you think you found the flag, but it doesn't work, consider that the data may be encrypted."
  Just decode it, the "==" terms means that it's base64. search for online decoder, enter it, and you got:
  ```
  R6AKNhWwo7
  ```
  enter it at the flag submit section and it's done. Look, no coding at all
   
