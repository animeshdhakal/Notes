It is the region of memory in which data can be pushed or from which can be popped. There is a specific register called stack pointer (SP) that points to the top of the stack.

## PUSH
This instruction pushes the data into the stack and subtracts the stack pointer by the number of values.

```assembly
PUSH {<registers>}
```

## POP
This instruction pops the data from the stack and increments the stack pointer by the number of values.

```assembly
POP {<registers>}
```

## Stack Frame
It is the section of the stack that is dedicated to the function. This information generally includes arguments passed to th function, local variables and where to return upon terminating.

## Creating a stack frame

```assembly
sample:
	push {r4-r11, lr}
	sub sp, #32 ; Allocate 32 byte for the stack frame

	str r0, [sp]
	str r1, [sp, #4]
	str r2. [sp, #8]
	str r3, [sp, #12]
	
	add sp, #32 ; Deallocate 32 byte
	pop {r4-r11, pc}

_start:
	bl sample
```

