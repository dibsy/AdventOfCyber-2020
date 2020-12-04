Our malicious, despicable, vile, cruel, contemptuous, evil hacker has defaced Elf's forums and completely removed the login page! However, we may still have access to the API. The sysadmin also told us that the API creates logs using dates with a format of YYYYMMDD.

- Given the URL "http://shibes.xyz/api.php", what would the entire wfuzz command look like to query the "breed" parameter using the wordlist "big.txt" (assume that "big.txt" is in your current directory)
```
wfuzz -c -z file,big.txt http://shibes.xyz/api.php?breed=FUZZ
```
- Use GoBuster to find the API directory. What file is there?

```
site-log.php
```
```
gobuster dir -u http://10.10.58.3 -w /usr/share/wordlists/dirb/big.txt 
/.htaccess (Status: 403)
/.htpasswd (Status: 403)
/LICENSE (Status: 200)
/api (Status: 301)
/server-status (Status: 403)


http://10.10.58.3/api/
```
- Fuzz the date parameter on the file you found in the API directory. What is the flag displayed in the correct post?
```
THM{D4t3_AP1}
```
```
wfuzz -c -z file,somefuzzparam -z file,wordlist --hh 0 http://10.10.58.3/api/site-log.php?FUZZ=FUZ2Z
Warning: Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.

********************************************************
* Wfuzz 2.2.9 - The Web Fuzzer                         *
********************************************************

Target: http://10.10.58.3/api/site-log.php?FUZZ=FUZ2Z
Total requests: 441

==================================================================
ID      Response   Lines      Word         Chars          Payload    
==================================================================

000278:  C=200      0 L        1 W           13 Ch        "date - 20201125"

Total time: 0.620686
Processed Requests: 441
Filtered Requests: 440
Requests/sec.: 710.5041


root# curl http://10.10.58.3/api/site-log.php?date=20201125
THM{D4t3_AP1}
```
