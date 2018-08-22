# Internet Kitties

It said
"I was told there was something at IP shell2017.picoctf.com with port 43099. How do I get there? Do I need a ship for the port?"

and hints:

Look at using the netcat (nc) command!
To figure out how to use it, you can run "man nc" or "nc -h" on the shell, or search for it on the interwebz

This is the tutorial how to accessing something on server using terminal, so just type:
```
  nc -h```
It means look for help in using this command. For me (maybe different for others but the command still the same)
```
OpenBSD netcat (Debian patchlevel 1.105-7ubuntu1)
This is nc from the netcat-openbsd package. An alternative nc is available
in the netcat-traditional package.
usage: nc [-46bCDdhjklnrStUuvZz] [-I length] [-i interval] [-O length]
	  [-P proxy_username] [-p source_port] [-q seconds] [-s source]
	  [-T toskeyword] [-V rtable] [-w timeout] [-X proxy_protocol]
	  [-x proxy_address[:port]] [destination] [port]
	Command Summary:
		-4		Use IPv4
		-6		Use IPv6
		-b		Allow broadcast
		-C		Send CRLF as line-ending
		-D		Enable the debug socket option
		-d		Detach from stdin
		-h		This help text
		-I length	TCP receive buffer length
		-i secs		Delay interval for lines sent, ports scanned
		-j		Use jumbo frame
		-k		Keep inbound sockets open for multiple connects
		-l		Listen mode, for inbound connects
		-n		Suppress name/port resolutions
		-O length	TCP send buffer length
		-P proxyuser	Username for proxy authentication
		-p port		Specify local port for remote connects
        	-q secs		quit after EOF on stdin and delay of secs
		-r		Randomize remote ports
		-S		Enable the TCP MD5 signature option
		-s addr		Local source address
		-T toskeyword	Set IP Type of Service
		-t		Answer TELNET negotiation
		-U		Use UNIX domain socket
		-u		UDP mode
		-V rtable	Specify alternate routing table
		-v		Verbose
		-w secs		Timeout for connects and final net reads
		-X proto	Proxy protocol: "4", "5" (SOCKS) or "connect"
		-x addr[:port]	Specify proxy address and port
		-Z		DCCP mode
		-z		Zero-I/O mode [used for scanning]
	Port numbers can be individual or ranges: lo-hi [inclusive]
```
In this case, just type:
  ```
   nc shell2017.picoctf.com 43099
```
Then appeared:
```
  Yay! You made it!
  Take a flag!
  3f6cd68a982d8f0b72b04faf389e6a51
```
