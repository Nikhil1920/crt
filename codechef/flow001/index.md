---
title: Codechef Add Two Numbers problem solution
published: 2021-08-25T12:28:00
updated: 2021-08-25T12:28:00
tags: ["codechef", "java", "codechef practice"]
---
Shivam is the youngest programmer in the world, he is just 12 
years old. Shivam is learning programming and today he is writing 
his first program.

The task is very simple: given two integers A and B, write a 
program to add these two numbers and output it.

## Input
The first line contains an integer T, the total number of test 
cases. Then follow T lines, each line contains two Integers A and 
B.

## Output
For each test case, add A and B and display the sum in a new line.

## Constraints
1 ≤ T ≤ 1000\
0 ≤ A,B ≤ 10000

## Example
```
Input
3
1 2
100 200
10 40

Output
3
300
50
```

## Codechef Add Two Numbers problem solution in java
```java
// FLOW001
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            int num1 = sc.nextInt();
            int num2 = sc.nextInt();
            int sum = num1 + num2;
            System.out.println(sum);
        }
        sc.close();
    }
}
```