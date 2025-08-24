# Mathematical Operations
## Signed vs Unsigned Numbers

### Signed Numbers
The MSB is used as the sign bit. The numbers are stored as 2's complement.

- 0 indicates positive number
- 1 indicates negative number

### Unsigned Numbers
The MSB is used as a value.

## ADD
It is same for both signed and unsigned values.

```assembly
ADD[S] <Rd>, <R1>, <R2> or #num
```
- Rd is the destination register
- R1 and R2 are the input registers.

## SUB 
It is same for both signed and unsigned values.

```assembly
SUB[S] <Rd>, <R1>, <R2> or #num
```
- Rd is the destination register
- R1 and R2 are the input registers.

## MUL 
It is same for both signed and unsigned values.

```
MUL[S] <Rd>, <R1>, <R2> or #num
```
- Rd is the destination register
- R1 and R2 are the input registers.

## SMULL/UMULL
- **SMULL**: Signed long multiplication
- **UMULL**: Unsigned long multiplication

```assembly
SMULL <low_part>, <high_part>, <R1>, <R2>
UMULL <low_part>, <high_part>, <R1>, <R2>
```

The result is separated into two registers one having the higher part and one having the lower part.

## SDIV/UDIV
- **SDIV**: Signed division
- **UDIV**: Unsigned division 

```assembly
SDIV <Rd>, <R1>, <R2>
UDIV <Rd>, <R1>, <R2>
```

## CMP 
This instruction is same for both unsigned and signed values.

```assembly
CMP <R1>, <R2>
```

## Conditional Branching
Signed: BGE (Branch if Greater or Equal), BLT (Branch if Less Than).
Unsigned: BHS (Branch if Higher or Same), BLO (Branch if Lower).



