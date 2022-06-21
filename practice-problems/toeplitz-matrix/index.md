---
title: Toeplitz Matrix
published: 2021-08-28T09:36:00
updated: 2021-08-28T09:36:00
tags: ["Practice Problems", "crt"]
---

Given an m x n matrix, return true if the matrix is Toeplitz.
Otherwise, return false.

A matrix is Toeplitz if every diagonal from top-left to
bottom-right has the same elements.

```
1 2 3 4
5 1 2 3
9 5 1 2
```

In the above grid, the diagonals are: "[9]", "[5, 5]", "[1, 1,
1]", "[2, 2, 2]", "[3, 3]", "[4]". In each diagonal all
elements are the same, so the answer is True.

## Input Format

First line of input contains N, M - size of the matrix. Its
followed by N lines each containing M intergers - elements of
the matrix.

## Constraints

1 <= m, n <= 20\
0 <= matrix[i][j] <= 99

## Output Format

Print "true" if matrix is Toeplitz else print "false".

## Sample Input

```
3 4
1 2 3 4
5 1 2 3
9 5 1 2
```

## Sample Output

true

## Solution in java

```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = sc.nextInt();
        boolean isToeplitz = true;
        int[][] matrix = new int[n][m];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < m - 1; j++) {
                if (matrix[i][j] != matrix[i + 1][j + 1])
                    isToeplitz = false;
            }
        }
        System.out.println(isToeplitz);
        sc.close();
    }
}
```
