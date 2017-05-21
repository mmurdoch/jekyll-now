---
layout: post
title: Useful x86 Opcodes
---

## EB (JMP)
Unconditional jump. Can be used to overwrite a conditional jump to ensure that the jump always happens.

## 90 (NOP)
No operation. Does absolutely nothing. Can be used to overwrite a jump instruction and its operands to prevent the jump.

## E8 (CALL)
Calls a function.

## C3 (RET)
Returns from a function.
