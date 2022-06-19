---
title: Codechef Number Mirror problem solution
published: 2021-08-26T01:00:00
updated: 2021-08-26T01:00:00
tags: ["codechef", "java", "codechef practice"]
---
## Problem Statement
Write a program that accepts a number, n, and outputs the same.

## Input
The only line contains a single integer.

## Output
Output the answer in a single line.

## Constraints
0 ≤ n ≤ 105

## Sample Input
123

## Sample Output
123

## Codechef Number Mirror problem solution in java
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();
        System.out.println(num);
        sc.close();
    }
}
```