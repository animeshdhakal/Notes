# LDR
In arm assembly, many operands can't access the memory directly like the mov instruction cannot get the value from the memory.

## LDR Instruction
```asm
ldr <reg>, [<address>]
```

## LDR Pseudo Instruction
The LDR pseudo instruction allows directly to load a constant value directly to the register or to load an address to the register.

### Loading a constant
```asm
ldr r0, =0xffff
```
This will store 0xffff into r0

### Loading an address
```asm
ldr r0, =var1 ; Loads the address of label var1 into r0
ldr r1, [r0] ; Loads the value from address stored in r0
ldr r2, [r0, #4] ; This is relative offset will access memory address (r0 + 4)

var1: .word 0x1234
```

## PC Relative Loads
Arm instruction is 32 bit long. If it is longer than that, the assembler will try to use pc relative offsetting. It will store the load value at the end of the function or label and access it through pc offsetting.

```asm
ldr r0, =0xffeeffff
```
The assembler can optimize it in two ways
```asm
ldr r0, [pc, #8] ; Accesses the memory (pc + 8)
```
The value 0xffeeffff will be stored at the bottom of the function or label in the memory.

or
```asm
movw r0, 0xffff
movt r0, 0xffee
```

We can see that the upper one only takes one instruction to process the same task.