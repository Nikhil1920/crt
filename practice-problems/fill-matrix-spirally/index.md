---
title: Fill matrix spirally
published: 2021-08-25T09:45:00
updated: 2021-08-25T09:45:00
tags: ["daily-contest", "java", "25-05-2021"]
---
Given a R x C matrix Fill matrix with values from 1 to RxC spirally.
We've to repeatedly print elements using these orders (Left->Right, 
Top->Down, Right->Left, Down->Up)

## Input Format

Line 1: Integer T - number of test cases.\
Next T lines contain a pair of integers per line R C

## Constraints
```
1 <= T <= 100
1 <= R, C <= 100
```

## Output Format

For each test case, print RxC matrix on output which is filled spirally. 
Also print newline after all the elements have been printed.

## Sample Input 0
```
2
3 3
2 4
```

## Sample Output 0
```
1 2 3
8 9 4
7 6 5

1 2 3 4
8 7 6 5
```
## Solution in java
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            int r = sc.nextInt();
            int c = sc.nextInt();
            int num = 1;
            int up = 0;
            int left = 0;
            int down = r - 1;
            int right = c - 1;
            int matrix[][] = new int[r][c];
            while (num <= r * c) {
                for (int col = left; col <= right; col++) {
                    matrix[up][col] = num;
                    num++;
                }
                for (int row = up + 1; row <= down; row++) {
                    matrix[row][right] = num;
                    num++;
                }

                if (up != down) {

                    for (int col = right - 1; col >= left; col--) {
                        matrix[down][col] = num;
                        num++;
                    }
                }

                if (left != right) {
                    for (int row = down - 1; row > up; row--) {
                        matrix[row][left] = num;
                        num++;
                    }
                }
                left++;
                right--;
                up++;
                down--;
            }
            for (int i = 0; i < r; i++) {
                for (int j = 0; j < c; j++) {
                    System.out.print(matrix[i][j] + " ");
                }
                System.out.println();
            }
            System.out.println();
        }
        sc.close();
    }
}
```