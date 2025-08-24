# LDM
This instruction enables to load into multiple registers at once using a single instruction. In simple terms, it is a way of handling array in Arm assembly.

```assembly
ldm <base_register> {<register_list>}
```

The base_register should point to the memory address of the first element. The way it works is by increasing the memory address by one to access other elements.

```
.text
ldr r0, =var1
ldm r0, {r1, r2, r3, r4, r5}

.data
var1: .word 1,2,3,4,5
```

This will load value 1,2,3,4,5 in registers r1, r2, r3, r4, r5