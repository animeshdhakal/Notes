This instruction loads the value in a register into specified memory address

```assembly
str <src>, [<address>]
```

## Example
```assembly
.text
_start:
ldr r0, =var1
ldr r1, 15
str r1, [r0]

.data
var1: .word 12
```


## PC Relative Store
This code uses a PC relative load to load the address of a variable into a register before a store.

```assembly
.text 
.global _start 

_start: 
ldr r0, =mydata 
ldr r1, =#32 
str r1, [r0] 

.data 
mydata: 11 .byte 0x0
```

