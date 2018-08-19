# ComputeAES

see the description, there're 

You found this clue laying around. Can you decrypt it?

and hints : 
Try online tools or python


wow, you found these:
Encrypted with AES in ECB mode. All values base64 encoded
ciphertext = V3Vqirostg6qW26sle5mnyrwEYSrteN6oHkilO50e9dFkN+0JhC3yu0LcQNw/hXU
key = r7y1dhmTvjQrcra7A1UQFw==

take a look that the value is on base64 encode. 

1. before that, convert those base64 to hex.

2. you got the hex, use the online aes converter, insert the text and keys.
   I found the tutorial from John Hammond to generate it using python. just try it, note that you can't rely on internet forever.
    
    https://www.youtube.com/watch?v=sR29bTAD_2o

3. I use the base64 to hex converter here: http://tomeko.net/online_tools/base64.php?lang=en
   and aes decryptor here: http://www.cryptogrium.com/aes-encryption-online-ecb.html
   
4. you found on hexadecimals: 666c61677b646f5f6e6f745f6c65745f6d616368696e65735f77696e5f36613638613239327d5f5f5f5f5f5f5f5f5f5f
5. just convert it to ascii, you found: flag{do_not_let_machines_win_6a68a292}__________
