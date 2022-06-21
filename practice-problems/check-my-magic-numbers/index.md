---
title: Check My Magic numbers
published: 2021-08-27T09:44:00
updated: 2021-08-27T09:44:00
tags: ["Practice Problems", "crt"]
---

## Problem Explanation :

In this problem you will be provided with array A of N
elements in it and K.We need to find the distinct valid
positions in such a way that if you add the one array element
with the value of K then it should be greater than the sum of
the rest of array elements.

## For example :

if the input is ===>

```
2
4 4
2 1 6 7
```

And for this output is ====>\
1

A1 + K = 6 isn't greater than A2 + A3 + A4 = 14, so position 1
isn't valid. A2 + K = 5 isn't greater than A1 + A3 + A4 = 15,
so position 2 isn't valid. A3 + K = 10 isn't greater than A1 +
A2 + A4 = 10, so position 3 also isn't valid. A4 + K = 11 is
greater than A1 + A2 + A3 = 9. Therefore, there is only one
valid position hence the answer is 1 — position 4.

## Problem Logic :

Run a loop to add all the elements of the array.
Then in the second loop add the array element values and then
exclude the current array element value which is added to k
from the sum.

Check a[i]+k > sum (sum of the rest elements) or not .

## Solution in java

```java
// CheckMyMagicnumbers
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            int n = sc.nextInt();
            int k = sc.nextInt();
            int count = 0;
            int[] array = new int[n];
            int array_sum = 0;
            for (int i = 0; i < n; i++) {
                array[i] = sc.nextInt();
                array_sum += array[i];
            }
            for (int i = 0; i < n; i++) {
                int temp = array_sum - array[i];
                if (array[i] + k > temp) {
                    count++;
                }
            }
            System.out.println(count);
        }
        sc.close();
    }
}
```
