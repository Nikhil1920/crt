---
title: Flipping bits
published: 2021-08-26T09:45:00
updated: 2021-08-26T09:45:00
tags: ["Practice Problems", "crt"]
---

## Problem Statement:

You will be given a list of 32 bit unsigned integers. Flip all
the bits ( and ) and return the result as an unsigned integer.

## Problem Explanation:

Here you are given a 32 bit unsigned number to which you need
invert each bit in its 32 bit binary representation, In other
words like 1’s complement.

## Program Logic:

Here you are told that the answer is 32 bit unsigned number so
the maximum possible answer is 232-1 = 4294967295.
Here you are told to invert each bit in the number’s 32 bit
binary representation.

I.e 0 → 1 1 → 0

If n = 0 then inverted answer will be 232-1 = 4294967295.\
If n = 1 then inverted answer will be 232-2 = 4294967294.\
If n = 2 then inverted answer will be 232-3 = 4294967293.

By the above pattern of inversion we can come to a conclusion
that the given answer for the given value “n” will be  
((pow(2,32) - 1 ) - n ).

## Solution in java

```java
import java.util.Scanner;

class Flippingbits {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            long n = sc.nextLong();
            long sum = 4294967295L;
            System.out.println(sum - n);
        }
        sc.close();
    }
}
```
