Someone is mischievous at The Best Festival Company. The contents within the stockings have been removed. A clue was left in one of the stockings that hints that the contents have been hidden within Elfstation1. McEager moves quickly and attempts to RDP into the machine. Yikes! He is unable to log in.

- Search for the first hidden elf file within the Documents folder. Read the contents of this file. What does Elf 1 want?
```
2 front teeth
```
- Search on the desktop for a hidden folder that contains the file for Elf 2. Read the contents of this file. What is the name of that movie that Elf 2 wants?
```
Scrooged
```
- Search the Windows directory for a hidden folder that contains files for Elf 3. What is the name of the hidden folder? (This command will take a while)
```
3lfthr3e
```
```
Get-ChildItem -Hidden -Directory -Recurse -ErrorAction SilentlyContinue
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d--h--       11/23/2020   3:26 PM                3lfthr3e
d--h--       11/23/2020   2:26 PM                GroupPolicy

```
- How many words does the first file contain?
```
9999
```
- What 2 words are at index 551 and 6991 in the first file?
```
Red Ryder
```
```
Select-String -Path '2.txt' -Pattern '*Red*'
```
- This is only half the answer. Search in the 2nd file for the phrase from the previous question to get the full answer. What does Elf 3 want? (use spaces when submitting the answer)
```
red ryder bb gun
```
```
Get-Content 2.txt | Select-String -Pattern "redryder"
```
