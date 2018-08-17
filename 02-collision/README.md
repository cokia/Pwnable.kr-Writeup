# Pwnable.kr 01-FD writeup
```
[+] Connecting to pwnable.kr on port 2222: Done
[!] Couldn't check security settings on 'pwnable.kr'
[+] Opening new channel: './col \xc8\xce\xc5\x06\xc8\xce\xc5\x06\xc8\xce\xc5\x06\xc8\xce\xc5\x06\xcc\xce\xc5\x06': Done
[+] Receiving all data: Done (52B)
[*] Closed SSH channel with pwnable.kr
daddy! I just managed to create a hash collision :)
```
# What I used?
 program divides argument string to 5 parts and sum, then compare with hashcode if is same, u will get a flag.
so I made 2 variable. hashpart1 and hashpart2

hashpart1 = p32(int(hashcode/5)))

hashpart2 = p32(4 + int(hashcode/5))

because hashcode - hashcode / 5 * 5 = 4 
so I need to plus 4 in shellcode.

# same exploit with explanation 
blog.hanukoon.com

