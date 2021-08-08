# Bit Shifting

 A bit shift moves each digit in a number's in binary representation left or right
 
 Shift:
 - Left Shifts
 - Arithmetic Right Shifts
 - Logical Right Shifts


## Left Shifts
When shifting left, the most-significant bit is lost, and a 00 bit is inserted on the other end.

```
0010 << 1  →  0100
0010 << 2  →  1000
```

==A single left shift multiplies a binary number by 2==


$xxxx << n → yyyy$

`let xxxx is the binary representation of number x`
`let yyyy is the binary representation of number y`

$( y = x \bullet 2^n )$

There is no need for arithmetic shift left instruction because a logical left shift moves zeroes into the least-significant(low-order) bit, which is correct for both signed and unsigned integers.

----

## Arithmetic Right Shift

When shifting right with an `arithmetic right shift`, the least-significant is lost and the most-significant bit is copied.

==Languages handle arithmetic and logical right shifting in different ways==



If a number is encoded using two's complement, then an arithmetic right shift preserves the number's sign, while a logical right shift makes the number positive.

## Logical Right Shift
When shifting right with an `logical right shift`, the least-significant bit is lost and a 0 is inserted on the other end.

```
1011 >>> 1 → 0101
1011 >>> 3 → 0001
```


For positive numbers, a single logical right shift divides a number by 2, throwing out any remainders.

```

0101 >>> 1 → 0010

0101 is 5
0010 is 2

```
