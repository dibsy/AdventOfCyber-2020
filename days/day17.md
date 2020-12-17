McSkidy has never really touched low-level languages - this is something they must learn in their quest to defeat the Christmas monster.
- What is the value of local_ch when its corresponding movl instruction is called (first if multiple)?
```
1
```
- What is the value of eax when the imull instruction is called?
```
6
```
- What is the value of local_4h before eax is set to 0?
```
6
```

```
[0x00400b62]> ds
[0x00400b62]> pdf
            ;-- main:
/ (fcn) sym.main 35
|   sym.main ();
|           ; var int local_ch @ rbp-0xc
|           ; var int local_8h @ rbp-0x8
|           ; var int local_4h @ rbp-0x4
|              ; DATA XREF from 0x00400a4d (entry0)
|           0x00400b4d      55             push rbp
|           0x00400b4e      4889e5         mov rbp, rsp
|           0x00400b51      c745f4010000.  mov dword [local_ch], 1
|           0x00400b58      c745f8060000.  mov dword [local_8h], 6
|           0x00400b5f      8b45f4         mov eax, dword [local_ch]
|           0x00400b62 b    0faf45f8       imul eax, dword [local_8h]
|           0x00400b66      8945fc         mov dword [local_4h], eax
|           ;-- rip:
|           0x00400b69      b800000000     mov eax, 0
|           0x00400b6e      5d             pop rbp
\           0x00400b6f      c3             ret
[0x00400b62]> px @ rbp-0x4
- offset -       0 1  2 3  4 5  6 7  8 9  A B  C D  E F  0123456789ABCDEF
0x7ffe77d4fc5c  0600 0000 4018 4000 0000 0000 e910 4000  ....@.@.......@.
0x7ffe77d4fc6c  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fc7c  0100 0000 88fd d477 fe7f 0000 4d0b 4000  .......w....M.@.
0x7ffe77d4fc8c  0000 0000 0000 0000 0000 0000 0600 0000  ................
0x7ffe77d4fc9c  5500 0000 5000 0000 0400 0000 0000 0000  U...P...........
0x7ffe77d4fcac  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fcbc  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fccc  0000 0000 0004 4000 0000 0000 66b7 3a9e  ......@.....f.:.
0x7ffe77d4fcdc  da11 c4a6 e018 4000 0000 0000 0000 0000  ......@.........
0x7ffe77d4fcec  0000 0000 1890 6b00 0000 0000 0000 0000  ......k.........
0x7ffe77d4fcfc  0000 0000 66b7 5a56 f3fe 3859 66b7 8e8f  ....f.ZV..8Yf...
0x7ffe77d4fd0c  da11 c4a6 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fd1c  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fd2c  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fd3c  0000 0000 0000 0000 0000 0000 0000 0000  ................
0x7ffe77d4fd4c  0000 0000 0000 0000 0000 0000 0000 0000  ................

```
