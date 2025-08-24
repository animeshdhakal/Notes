# Registers
There are several types of registers in ARM assembly on the basis of their use cases

## General Purpose 
The registers **r0-r10** are general purpose registers which means that they can be used in any ways in a program.

## Calling Conventions
When writing a complex program, certain things are made to be standardized so that they are consistent over all computer system. The registers **r0-r3, r7** have specific use cases. 

## Special Purpose
- **Stack Pointer R13**:  This register point to the top of the stack
- **Link Register R14**:  This register holds the return address for function calls
- **Program Counter R15**: This register holds the address of the next instruction to be executed.
- **CPSR**: The Current Program State Register provided essential information about the processors's state.






