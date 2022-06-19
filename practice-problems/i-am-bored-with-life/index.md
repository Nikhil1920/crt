---
title: I'm bored with Life
published: 2021-08-16T10:16:00
updated: 2021-08-16T10:16:00
tags: ["14-08-2021", "dialy practise", "crt"]
---
Holidays have finished. Thanks to the help of the hacker Leha, Noora 
managed to enter the university of her dreams which is located in a town 
Pavlopolis. It's well known that universities provide students with 
dormitory for the period of university studies. Consequently Noora had to 
leave Vičkopolis and move to Pavlopolis. Thus Leha was left completely 
alone in a quiet town Vičkopolis. He almost even fell into a depression 
from boredom!

Leha came up with a task for himself to relax a little. He chooses two 
integers A and B and then calculates the greatest common divisor of 
integers "A factorial" and "B factorial". Formally the hacker wants to 
find out GCD(A!, B!). It's well known that the factorial of an integer x 
is a product of all positive integers less than or equal to x. Thus 
x! = 1·2·3·...·(x - 1)·x. For example 4! = 1·2·3·4 = 24. Recall that GCD(x,
 y) is the largest positive integer q that divides (without a remainder) 
both x and y.

Leha has learned how to solve this task very effective. You are able to 
cope with it not worse, aren't you?

### Input Format

The first and single line contains two integers A and B

### Constraints

(1 ≤ A, B ≤ 109,  min(A, B) ≤ 12)

### Output Format

Print a single integer denoting the greatest common divisor of integers A! 
and B!

### Sample Input 0

4 3

### Sample Output 0

6

### java code
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num1 = sc.nextInt();
        int num2 = sc.nextInt();
        int result = 1;
        int min = Math.min(num1, num2);
        for (int i = 1; i <= min; i++) {
            result *= i;
        }
        System.out.println(result);
        sc.close();
    }
}
```