---
title: Codeforces 282 a Bit++ problem solution
published: 2021-08-26T04:44:00
updated: 2021-08-26T04:44:00
tags: ["codeforces", "java", "codeforces problemset"]
---
The classic programming language of Bitland is Bit++. This 
language is so peculiar and complicated.

The language is that peculiar as it has exactly one variable, 
called x. Also, there are two operations:

1. Operation ++ increases the value of variable x by 1.
2. Operation -- decreases the value of variable x by 1.

A statement in language Bit++ is a sequence, consisting of 
exactly one operation and one variable x. The statement is 
written without spaces, that is, it can only contain characters "
+", "-", "X". Executing a statement means applying the operation 
it contains.

A programme in Bit++ is a sequence of statements, each of them 
needs to be executed. Executing a programme means executing all 
the statements it contains.

You're given a programme in language Bit++. The initial value of 
x is 0. Execute the programme and find its final value (the value 
of the variable when this programme is executed).

## Input

The first line contains a single integer n (1 ≤ n ≤ 150) — the 
number of statements in the programme.

Next n lines contain a statement each. Each statement contains 
exactly one operation (++ or --) and exactly one variable x 
(denoted as letter «X»). Thus, there are no empty statements. The 
operation and the variable can be written in any order.

## Output
Print a single integer — the final value of x.

## Examples
```
input

1
++X

output

1

input
2
X++
--X

output

0
```

## Codeforces 282a Bit++ problem solution in java
```java

// 282a bit++
import java.util.Scanner;

public class Bit {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int x = 0;
        int num_of_cases = sc.nextInt();
        while (num_of_cases-- > 0) {
            String s = sc.next();
            if (s.equals("++X") || s.equals("X++"))
                x++;
            else
                x--;
        }
        System.out.println(x);
        sc.close();
    }
}
```