---
title: Codechef Enormous Input Test problem solution
published: 2021-08-25T12:32:00
updated: 2021-08-25T12:32:00
tags: ["codechef", "java", "codechef practice"]
---
The purpose of this problem is to verify whether the method you 
are using to read input data is sufficiently fast to handle 
problems branded with the enormous Input/Output warning. You are 
expected to be able to process at least 2.5MB of input data per 
second at runtime.

## Input
The input begins with two positive integers n k (n, k<=107). The 
next n lines of input contain one positive integer ti, not 
greater than 109, each.

## Output
Write a single integer to output, denoting how many integers ti 
are divisible by k.

## Example
```
Input:
7 3
1
51
966369
7
9
999996
11

Output:
4
```

## Codechef Enormous Input Test problem solution in java
```java
// INTEST
import java.util.Scanner;

class INTEST {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int k = sc.nextInt();
        int[] arr = new int[n];
        int count = 0;
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
            if (arr[i] % k == 0) {
                count++;
            }
        }
        System.out.println(count);
        sc.close();
    }
}
```