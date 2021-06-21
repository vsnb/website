---
layout: post
title:  "self-modify into a loop"
date:   2021-06-20 16:59:58 +1000
categories: code
---
This is a quick puzzler demonstration of code and data being the same in
von Neumann architecture.

```shell
$ cat self_loop.bin
; Self-modifying code that acts as a loop.

1101 000 0 0000 0000  ; mvi r0 0
1111 0000 0000 0100   ; hout
1111 0000 0000 0001   ; nl
0010 000 111111100    ; ld r0 #-4
0001 000 000 1 00001  ; add r0 r0 #1
0011 000 111111010    ; st r0 #-6
0000 111 111111001    ; br #-7
1111 0000 0000 0000   ; halt
```

/EOM
