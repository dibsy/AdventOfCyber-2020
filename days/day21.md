One of the 'little helpers' logged into his workstation only to realize that the database connector file has been replaced, and he can't find the naughty list anymore. Furthermore, upon executing the database connector file, a taunting message was displayed, hinting that the file was moved to another location.

McEager has been notified, and he will put the pieces together to find the database connector file.

- Read the contents of the text file within the Documents folder. What is the file hash for db.exe?
```
596690FFC54AB6101932856E6A78E3A1
```
- What is the file hash of the mysterious executable within the Documents folder?
```
5F037501FB542AD2D9B06EB12AED09F0
```
- Using Strings find the hidden flag within the executable?
```
THM{f6187e6cbeb1214139ef313e108cb6f9}
```
- What is the flag that is displayed when you run the database connector file?
```
THM{088731ddc7b9fdeccaed982b07c297c}
```
