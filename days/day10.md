
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
