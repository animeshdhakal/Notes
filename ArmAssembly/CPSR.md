# CPSR
The Current Processor Status Register hold different flags which are set/unset using different instructions.

The CPSR contains these flags
- N (Negative Flag)
- Z (Zero Flag)
- V (Overflow Flag)
- Z(Zero Flag)

## N (Negative Flag)
The Negative flag is set when the result of an operation is negative. This flag is primarily used in signed arithmetic

- **Set**: If the result is negative
- **Clear**: If the result is non negative

## Z (Zero Flag)
The Zero flag is set when the result of an operation is zero. 

- **Set**: If the result is zero 
- **Clear**: If the result is non zero 

## C (Carry Flag)
The Carry flag indicates a carry out of the most significant bit in an addition operation or a borrow in a subtraction operation. It is used in both unsigned arithmetic and bitwise operations.

- **Set**: If there is a carry out of the most significant bit.
- **Clear**: If there is no carry

## V (Overflow Flag)
The Overflow flag is set when the result of an operation causes a signed overflow, meaning the result is too large to fit in the register.

- **Set**: If there is a signed overflow
- **Unset**: If there is no overflow

