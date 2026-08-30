# DearQA

## Gather Infomation (OSINIT)
first we what to gather infomation as much as possible from this binary 

1. First clue the binary is not stripped and it an x86_64 ELF binary 
![alt text](image/file.png)
2. Second clue string give us some clue about this program at some point we might able to entract with shell as we saw /bin/bash and it want us to input a some kind of password
![alt text](image/string.png)
3. Third clue tell us that binary have ALSR disable and Canary also disable which mean the address doesen't changes this mean we can write a value into and do some evil stuff >:) 
![alt text](image/checksec.png)

## Program Controll flow (Reverse Engineering)

