---
title: Codeforces 1a Theatre Square solution
published: 2021-08-26T03:00:00
updated: 2021-08-26T03:00:00
tags: ["codeforces", "java", "codeforces problemset"]
---
Theatre Square in the capital city of Berland has a rectangular 
shape with the size n × m meters. On the occasion of the city's 
anniversary, a decision was taken to pave the Square with square 
granite flagstones. Each flagstone is of the size a × a.

What is the least number of flagstones needed to pave the Square? 
It's allowed to cover the surface larger than the Theatre Square, 
but the Square has to be covered. It's not allowed to break the 
flagstones. The sides of flagstones should be parallel to the 
sides of the Square.

## Input
The input contains three positive integer numbers in the first 
line: n,  m and a (1 ≤  n, m, a ≤ pow(10,9)).

## Output
Write the needed number of flagstones.

## Examples
### input
6 6 4

### output
4

## Codeforces 1a Theatre Square problem solution in java
```java
// TheatreSquare
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        long n = sc.nextInt();
        long m = sc.nextInt();
        long a = sc.nextInt();
        long l = (n + a - 1) / a;
        long r = (m + a - 1) / a;
        System.out.println(l * r);
        sc.close();
    }
}
```