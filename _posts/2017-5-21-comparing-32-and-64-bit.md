---
layout: post
title: Comparing 32-bit and 64-bit Executables
---

On 64-bit Linux, GCC compiles a C program by default to a 64-bit ELF executable. To compile as 32-bit, you first need the GCC multilib support package. For example:

`sudo apt install gcc-multilib`.

Then you need to use `-m32` as an argument to GCC. So, if a 64-bit executable is created with:

`gcc -o program program.c`

you can compile it 32-bit using:

`gcc -m32 program program.c`
