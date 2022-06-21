---
title: Eligibility for Scholarship
published: 2021-08-24T09:45:00
updated: 2021-08-24T09:45:00
tags: ["Practice Problems", "crt"]
---

Shreya is an average student in her school. She wants to get scholarship but her teacher gave her a puzzle to solve, in puzzle she will be given a non-negative integer N, and she needs to calculate sum of digits of N. If sum of digits of N is greater than 20 she will get the scholarship otherwise she will not get it.

You need to help her know what is sum of digits of N and whether she will get scholarship or not.

## Input Format

First and only line of input contains a non-negative integer N.

## Constraints

0 <= length(N) <= 103

## Output Format

Print two lines of output, first line containing sum of digits of N and second line should print YES or NO based on eligibility criteria.

## Sample Input 0

135

## Sample Output 0

9\
NO

## Solution in java

```java
// EligibilityforScholarship
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        long result = 0;
        for (int i = 0; i < input.length(); i++) {
            result += input.charAt(i) - '0';
        }
        System.out.println(result);
        System.out.println(result > 20 ? "YES" : "NO");
        sc.close();
    }
}
```
