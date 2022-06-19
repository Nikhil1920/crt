---
title: How many ways?
published: 2021-08-16T08:04:00
updated: 2021-08-16T08:04:00
tags: ["14-08-2021", "dialy practise", "crt"]
---
Write a program which identifies the number of combinations of three 
integers which satisfy the following conditions:

You should select three distinct integers from 1 to n. A total sum of the 
three integers is x. For example, there are two combinations for n = 5 and 
x = 9.

1 + 3 + 5 = 9\
2 + 3 + 4 = 9


### Input Format

The input consists of multiple datasets. For each dataset, two integers n 
and x are given in a line.

The input ends with two zeros for n and x respectively. Your program 
should not process for these terminal symbols.

### Constraints
3 ≤ n ≤ 100\
0 ≤ x ≤ 300

### Output Format

For each dataset, print the number of combinations in a line.

### Sample Input 0

5 9\
0 0

### Sample Output 0

2

### java code
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNext()) {
            int n = sc.nextInt();
            int x = sc.nextInt();
            if (x == 0 && n == 0) {
                break;
            }
            int count = 0;
            for (int i = 1; i <= n; i++) {
                for (int j = i + 1; j <= n; j++) {
                    for (int k = j + 1; k <= n; k++) {
                        if (i + j + k == x) {
                            count++;
                        }
                    }
                }
            }
            System.out.println(count);
        }
        sc.close();
    }
}
```