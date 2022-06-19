---
title: Intersection Of Arrays
published: 2021-09-31T09:36:00
updated: 2021-09-31T09:36:00
tags: ["daily-contest", "java", "31-09-2021"]
---
Given two arrays A and B of size N and M respectively, print the count of 
elements in the intersection (or common elements) of the two arrays.
For this question, the intersection of two arrays can be defined as the set 
containing distinct common elements between the two arrays.

Note: You are not allowed to use built-in data structures (Set/Map/
Dictionary) and built-in functions like Sort.

## Input Format

First line contains integer T - number of test cases.

Each test case consists of 2 lines of input each giving size followed by 
array elements on a line:\
N A1 A2 A3 .... AN\
M B1 B2 .... BM

## Constraints

1 <= T <= 100\
1 <= N <= 10000\
-10000 <= Ai, Bi <= 10000

## Output Format

For each test case, print a separate line of outout containing count of 
elements in intersection Set of A and B.

## Sample Input 0
```
3
5 1 2 2 3 3
6 1 2 3 4 5 6
4 1 2 2 1
3 7 0 9
5 1 9 2 3 4
8 1 1 2 2 9 9 4 4
```

## Sample Output 0
```
3
0
4
```

## Intersection Of Arrays Solution in java
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            int n = sc.nextInt();

            int[] count_a = new int[20001];
            int[] count_b = new int[20001];

            for (int i = 0; i < n; i++)
                count_a[sc.nextInt() + 10000]++;

            int m = sc.nextInt();
            for (int i = 0; i < m; i++)
                count_b[sc.nextInt() + 10000]++;

            int count = 0;
            for (int i = 0; i < 20001; i++) {
                if (count_a[i] != 0 && count_b[i] != 0) {
                    count++;
                }
            }
            System.out.println(count);

        }
        sc.close();
    }
}
```