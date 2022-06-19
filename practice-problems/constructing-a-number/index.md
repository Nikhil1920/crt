---
title: Constructing a number
published: 2021-08-26T09:45:00
updated: 2021-08-26T09:45:00
tags: ["daily-contest", "java", "26-05-2021"]
---
## Problem Statement:
Manipulating numbers is at the core of a programmer's job. To test how well 
you know their properties, you are asked to solve the following problem.

You are given  non-negative integers. You want to know whether 
it's possible to construct a new integer using all the digits of these 
numbers such that it would be divisible by . You can reorder the digits as 
you want. The resulting number can contain leading zeros.

For example, consider the numbers  from which you have to construct a new 
integer as described above. Numerous arrangements of digits are possible; 
but we have illustrated one below.

## Problem Explanation:

Here we are given an array of +ve integers and we are asked to find out 
whether it is possible to construct a new number with the digits of each 
number given in the array in such a way that the resulting new number is 
divisible number is divisible by 3. We can arrange the digits of the 
integers in any order we want.


## Program Logic:

Here we are suppose to build a new number let’s say “x” with the digits of 
the given +ve integers of the array such that x%3 == 0.  

We know that a number is divisible by 3 if and only if sum of digits of the 
number is divisible by 3
(Divisibility Test for 3).

So here are going to form x from the digits of integers of array so if the 
sum of digits of each number in the array given should be divisible by 3 
then we can construct a new number x which is divisible by 3.


## Solution in java
```java
import java.util.Scanner;

class ConstructingANumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            int n = sc.nextInt();
            int arr[] = new int[n];
            for (int i = 0; i < n; i++)
                arr[i] = sc.nextInt();

            int sum = 0;
            for (int i = 0; i < n; i++) {
                while (arr[i] > 0) {
                    sum += arr[i] % 10;
                    arr[i] = arr[i] / 10;
                }
            }
            System.out.println(sum % 3 == 0 ? "Yes" : "No");
        }
        sc.close();
    }
}
```