產生組合語言
```
gcc -S power.c -o power.s
```
將組合語言轉換成目的碼
```
gcc -c power.c 
```
反組譯目的碼
```
power.o:     file format elf64-x86-64

Disassembly of section .text:

0000000000000000 <power>:
   0:   55                      push   %rbp
   1:   48 89 e5                mov    %rsp,%rbp
   4:   c7 45 fc 01 00 00 00    movl   $0x1,-0x4(%rbp)
   b:   c7 45 f8 00 00 00 00    movl   $0x0,-0x8(%rbp)
  12:   eb 1a                   jmp    2e <power+0x2e>
  14:   8b 45 fc                mov    -0x4(%rbp),%eax
  17:   0f af 45 f0             imul   -0x10(%rbp),%eax
  1b:   89 45 fc                mov    %eax,-0x4(%rbp)
  1e:   8b 45 f8                mov    -0x8(%rbp),%eax
  21:   83 c0 01                add    $0x1,%eax
  24:   89 45 f8                mov    %eax,-0x8(%rbp)
  27:   8b 45 f8                mov    -0x8(%rbp),%eax
  2a:   3b 45 f4                cmp    -0xc(%rbp),%eax
  2d:   7c e5                   jl     14 <power+0x14>
  2f:   8b 45 fc                mov    -0x4(%rbp),%eax
  32:   5d                      pop    %rbp
  33:   c3                      ret

```
印出該目的檔的表頭
```
power.o:     file format elf64-x86-64

Sections:
Idx Name          Size      VMA       LMA       File off  Algn
  0 .text         00000034  00000000  00000000  00000040  2**4
                  CONTENTS, ALLOC, LOAD, READONLY, CODE
  1 .comment      0000002c  00000000  00000000  00000074  2**0
                  CONTENTS, READONLY
  2 .note.GNU-stack 00000000 00000000 00000000  000000a0  2**0
                  CONTENTS, READONLY

```