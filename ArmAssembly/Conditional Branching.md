Branching and conditional execution are fundamental aspects of programming that allow the control flow of a program to change based on certain conditions.

## B 
This causes unconditional branch to the specified label.

```assembly
B <label>
```

## BL
This instruction causes a unconditional branch with the return address saved in the link register.

```assembly
BL <label>
```

## Condition Codes
The condition codes are two-letter suffixes that specify the condition under which the instruction should be

- **eq:** Equal (z set)

- **ne:** Not equal (z clear)

- **cs/hs**: Carry set/Unsigned higher or same (c set)

- **cc/lo**: Carry clear/Unsigned lower (c clear)

- **mi**: Minus/Negative (n set)

- **pl**: Plus/Positive or zero (n clear)

- **vs**: Overflow (v set)

- **vc**: No overflow (v clear)

- **hi**: Unsigned higher (c set and z clear)

- **Is**: Unsigned lower or same (c clear or z set)

- **ge**: Signed greater than or equal (n equals v)

- **It**: Signed less than (n not equal to v)

- **gt**: Signed greater than (z clear and n equals v)

- **le**: Signed less than or equal (z set or n not equal to v)