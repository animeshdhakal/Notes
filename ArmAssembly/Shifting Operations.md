When the bits are shifted to the right, the decimal is divided by 2 and when the the bits are shifted to the left, the decimal is multiplied by 2.
## Logical Shift
The logical shift doesn't care about the sign bit. So the sign bit will also be shifted towards the direction.

```assembly
lsl <Rd>, <Rs>, #<shift_amount>
lsr <Rd>, <Rs>, #<shift_amount>
```

## Arithmetic Shift
The arithmetic shift cares about the sign bit. All other bits except the sign bit will be shifted.

```assembly
asl <Rd>, <Rs>, #<shift_amount>
asr <Rd>, <Rs>, #<shift_amount>
```

## Rotate Shift
This shifts the bits in a circular manner.

```assembly
ror <Rd>, <Rs>, #<shift_amount>
rol <Rd>, <Rs>, #<shift_amount>
```