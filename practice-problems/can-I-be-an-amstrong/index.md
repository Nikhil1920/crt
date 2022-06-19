---
title: Can I be an amstrong?
published: 2021-08-25T09:45:00
updated: 2021-08-25T09:45:00
tags: ["daily-contest", "java", "25-05-2021"]
---
Given a sqaure matrix of dimensions r x c (of course r and c will be 
same) find whether the overall sum of all elements on left diagonal of 
matrix and right diagonal of matrix is an Armstrong number or not. 
Armstrong numbers is a number N such that N = sum of cubes of its digits. 
e.g. 0, 1, 153, 370 etc are Armstrong numbers.


## Input Format

First line consist of two space separated integers R C. Next R lines 
consist C element each per line, having elements of matrix.

## Constraints

1 <= R, C <= 1000\
0 <= M[i][j] <= 1000

## Output Format

Print 'Yes' if the sum of left diagonal elements and right left diagonal 
elements is an armstrong number else print 'No'.

## Sample Input 0
```
3 3
22 5 10
6 45 7
20 9 11
```

## Sample Output 0
```
Yes
```

## Solution in java
```java

// CanIbeanamstrong
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int r = sc.nextInt();
        int c = sc.nextInt();
        int matrix[][] = new int[r][c];
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }
        int diagonal_sum = 0;
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++) {
                if (i == j) {
                    diagonal_sum += matrix[i][j];
                }
                if ((i + j) == (r - 1))
                    diagonal_sum += matrix[i][j];
            }
        }
        System.out.println(isArmstrong(diagonal_sum) ? "Yes" : "No");
        sc.close();
    }

    public static boolean isArmstrong(int num) {
        boolean isArmstrong = false;
        int sum = 0;
        int temp = num;
        while (temp > 0) {
            sum += Math.pow(temp % 10, 3);
            temp /= 10;
        }
        if (sum == num) {
            isArmstrong = true;
        }
        return isArmstrong;
    }
}
```