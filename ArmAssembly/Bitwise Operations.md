Bitwise operations are fundamental in low-level programming and are frequently used in ARM assembly language for tasks such as setting, clearing, and toggling bits, as well as performing logical operations.

## AND
The AND instruction performs a bitwise AND operation between the bits of two registers. The result is stored in the destination register. Only bits that are set in both operands will be set in the result.

```assembly
AND <Rd>, <R1>, <R2>
```

## ORR
The ORR instruction performs a bitwise OR operation between the bits of two registers. The result is stored in the destination register. Bits that are set in either operand will be set in the result.

```assembly
ORR <Rd>, <R1>, <R2>
```

## EOR
The EOR instruction performs a bitwise exclusive OR (XOR) operation between the bits of two registers. The result is stored in the destination register. Bits that are set in one operand but not both will be set in the result.

```assembly
EOR <Rd>, <R1>, <R2>
```

## BIC
The BIC instruction performs a bitwise AND operation between the bits of the first operand and the complement of the second operand. Essentially, it clears specified bits in the first operand.

```assembly
BIC <Rd>, <R1>, <R2>
```