# Special Agent User

This problem is similar to the prior problem, the digital camouflage. You just took the information given in the description and hints.

"We can get into the Administrator's computer with a browser exploit. 
But first, we need to figure out what browser they're using. 
Perhaps this information is located in a network packet capture we took: data.pcap. 
Enter the browser and version as "BrowserName BrowserVersion". 
NOTE: We're just looking for up to 3 levels of subversions for the browser version (ie. Version 1.2.3 for Version 1.2.3.4) and ignore any 0th subversions (ie. 1.2 for 1.2.0)"

Then here come the hints:

"Where can we find information on the browser in networking data? Maybe try reading up on user-agent strings."

It's similar right? but try to find the browser information. 

1. Open the data.pcap on wireshark, then filter for HTTP
2. here comes a series of it, check one by one and select Hypertext transfer protocol in middle section. Extend it.
3. here we comes the request method to get it. on example, wget, and get. wget is familiar if we use linux, as it obtained through terminal. 
4. search for the GET method, one by one on the list info
5. You got something different.
```
"Mozilla/5.0 (X11; OpenBSD i386) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/36.0.1985.125 Safari/537.36"
```
6. There's the browser info. try it one by one, remember the format on the description, BrowserName BrowserVersion.
NOTE: We're just looking for up to 3 levels of subversions for the browser version (ie. Version 1.2.3 for Version 1.2.3.4) and ignore any 0th subversions (ie. 1.2 for 1.2.0)"
7. Yap, that's the flag
