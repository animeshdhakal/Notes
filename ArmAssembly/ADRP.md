The `ADRP` instruction loads the address of the 4KB page anywhere in the +/-4GB (33 bits) range of the current instruction (which takes 21 high bits of the offset). This is denoted by the `@PAGE` operator. then, we can either use `LDR` or `STR` to read or write any address inside that page or `ADD` to to calculate the final address using the remaining 12 bits of the offset (denoted by `@PAGEOFF`).


```assembly
adrp x0, var@PAGE ; Gets the page address
add x0, x0, var@PAGEOFF ; Add the page offset to the page address to get the actual address

; 12 

.data
var: .space 256
```

