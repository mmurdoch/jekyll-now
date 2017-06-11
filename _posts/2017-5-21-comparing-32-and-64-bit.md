---
layout: post
title: Comparing 32-bit and 64-bit Linux Executables
---

## Compiling C Programs with GCC
On 64-bit Linux, GCC compiles a C program by default to a 64-bit ELF executable. To compile as 32-bit, you first need the GCC multilib support package. For example:

`sudo apt install gcc-multilib`.

Then you need to use `-m32` as an argument to GCC. So, if a 64-bit executable is created with:

`gcc -o program-64 program.c`

you can compile it 32-bit using:

`gcc -m32 program-32 program.c`

# Compiling Assembly Programs with NASM
Unlike C, assembly is not portable between 32-bit and 64-bit systems, so the source files to NASM will be different. NASM also must be told explicitly which object format to write. So for 32-bit output, use:

`nasm -f elf32 program-32.asm`

and for 64-bit output, use:

`nasm -f elf64 program-64.asm`

The resultant object files need to be linked into an appropriate executable format. To create a 32-bit ELF, use:

`ld -m elf_i386 -s -o program-32 program-32.o`

and a 64-bit ELF can be created using the following:

`ld -m elf_x86_64 -s -o program-64 program-64.o`
