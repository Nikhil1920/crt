---
title: Help Rishab
published: 2021-08-24T09:45:00
updated: 2021-08-24T09:45:00
tags: ["daily-contest", "java", "24-05-2021"]
---
Each student in KLU is given a matrix and are assigned with few tasks, Rishab being a student of kLU is also given a matrix and is assigned few tasks to perform on matrix but he is not aware of matrices so you being his mate need to get his tasks done.

Task 1- Given a matrix, transpose the matrix and print it.\
Task 2- find maximum row sum and maximum column sum of transposed matrix.\
Task 3- print absolute difference of maximum row sum and maximum column sum of transposed matrix.\

## Input Format

First line consists of dimensions of matrix r,c.
Next r line consists of matrix elements.

## Constraints
```
1 < r,c < 10
```

## Output Format

first c lines of output consists of transposed matrix.
Next line consists of absolute difference of maximum row sum and maximum coloumn sum of transposed matrix.

## Sample Input 0
```
3 3
1 2 3
2 1 3
3 1 2
```

## Sample Output 0
```
1 2 3 
2 1 1 
3 3 2
2
```

## Solution in java
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int r = sc.nextInt();
        int c = sc.nextInt();
        int matrix[][] = new int[r][c];
        int transpose[][] = new int[c][r];
        int max_row_sum = 0;
        int max_col_sum = 0;
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }

        for (int i = 0; i < c; i++) {
            int row_sum = 0;
            for (int j = 0; j < r; j++) {
                transpose[i][j] = matrix[j][i];
                row_sum += transpose[i][j];
                System.out.print(transpose[i][j] + " ");
            }
            if (max_row_sum < row_sum)
                max_row_sum = row_sum;
            System.out.println();
        }

        for (int i = 0; i < r; i++) {
            int col_sum = 0;
            for (int j = 0; j < c; j++) {
                col_sum += transpose[j][i];
            }
            if (max_col_sum < col_sum)
                max_col_sum = col_sum;
        }
        System.out.println(Math.abs(max_row_sum - max_col_sum));
        sc.close();
    }
}
```