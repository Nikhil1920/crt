---
title: Even Chef have Friends!
published: 2021-08-28T09:34:00
updated: 2021-08-28T09:34:00
tags: ["daily-contest", "java", "28-08-2021"]
---
Chef decided to find the connections with all of his friends 
in an unnamed social network. He calls a user of the social 
network his friend if there is a common substring of the 
string "chef" and the nickname of that user with length ≥ 2.

Given a list of users of the social network, compute the 
number of Chef's friends.

## Input Format

The first line of the input contains a single integer N 
denoting the number of users in the social network.

N lines follow. Each of these lines contains a single string u 
denoting the nickname of one user.

## Constraints

1 ≤ N ≤ 5,000\
3 ≤ |u| ≤ 20

each character of each user's nickname is either a lowercase 
English letter ('a'-'z') or '.'

the first character of each user's nickname is a lowercase 
English letter.

## Output Format

Print a single line containing one integer — the number of 
Chef's friends.

## Sample Input
```
4
gennady.korotkevich
kefaa
fhlasek
chemthan
```

## Sample Output

3

## Explanation
gennady.korotkevich is a friend to Chef because he has "ch" at 
the end of his nickname, which is also a substring of "chef" 
with length 2

The common substring with kefaa is "ef" and the common 
substring with chemthan is "che"

## Solution in java
```java
import java.util.Scanner;

class chefAndFriends {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num_of_cases = sc.nextInt();
        int count = 0;
        while (num_of_cases-- > 0) {
            String s = sc.next();
            String chef = "chef";
            for (int i = 0; i < s.length() - 1; i++) {
                String sub = s.substring(i, i + 2);
                if (chef.contains(sub)) {
                    count++;
                    break;
                }
            }
        }
        System.out.println(count);
        sc.close();
    }
}
```