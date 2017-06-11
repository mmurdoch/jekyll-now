---
layout: post
title: Useful x86 Opcodes
---

## EB (JMP)
Unconditional jump. Can be used to overwrite a conditional jump to ensure that the jump always happens.

## 90 (NOP)
No operation. Does absolutely nothing. Can be used to overwrite a jump instruction and its operands to prevent the jump.

## E8 (CALL)
Calls a function. Works by pushing the address of the next instruction onto the stack and setting the instruction pointer to the address of the start of the function.

## C3 (RET)
Returns from a function called by a CALL instruction. Works by popping the return address from the stack and setting the instruction pointer to that address.

## CD 80 (INT 0x80)
32-bit Linux system call. The system call number must be in register EAX. Arguments to the system call must be in registers EBX, ECX, EDX, ESI, EDI and EBP (in that order). Any return value from the system call will be put in EAX. All registers are saved across the system call.

## 0F 05 (SYSCALL)
64-bit Linux system call. The system call number must be in register RAX. Arguments to the system call must be in registers RDI, RSI, RDX, R10, R8, and R9 (in that order). Any return value from the system call will be put in RAX. All registers **except RCX and R11** are saved across the system call.
