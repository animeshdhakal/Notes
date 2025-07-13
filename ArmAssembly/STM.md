This instruction enables to store multiple into memory from registers.

```assembly
stm <base_register>, {<register_list>}
```

The **base_register** should point to the memory address of the first element

```assembly
.text
ldr r0, =var1
mov r1, 6 
mov r2, 7
mov r3, 8
mov r4, 9
mov r5, 10

stm r0, {r1, r2, r3, r4, r5}

.data
var1: .word 1,2,3,4,5
```

The location of 1, 2, 3, 4, 5 will be overwritten with 6, 7, 8, 9, 10