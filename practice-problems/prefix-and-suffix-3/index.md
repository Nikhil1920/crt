---
title: Pefix and Suffix 3
published: 2021-08-27T09:38:00
updated: 2021-08-27T09:38:00
tags: ["daily-contest", "java", "27-05-2021"]
---
## Problem statement-  

For a given string s, the task is to compute the length of the 
longest proper prefix which is same as the suffix of the given 
string.

Ex- smartintsmart

smart is the longest proper prefix as well as suffix.
The length of the longest proper prefix which is also a suffix 
i.e “smart” is 5.

A proper prefix and proper suffix of a string is not equal to 
the string itself and non- empty.
These are the special cases of substrings.

Lets say ⇒ String- "India"

All possible substrings - "India", "Indi" , "ndia" , " Ind", " 
ndi" , "dia",  "In", "nd", "di", "ia" , "I", "n", "d", "i", 
"a"  

A prefix of a string is a substring that occurs at the 
beginning of the string.

A suffix of a string is a substring that occurs at the end of 
the string.

Proper Prefix - "I", "In", "Ind", "Indi"

Proper Suffix - "a", "ia", "dia", "ndia"

## Approach⇒ 

If the string length is less than 2 then return 0 as there is 
no  proper prefix which is same as  suffix 

Else , take two pointers (say i,j) pointing the first index of 
string and the second pointer pointing the second index of the 
string.

Until the second pointer is less than the length of string ( j 
< s.length() ) check if s [ i ] == s [ j ] then increment the 
pointers

If s [ i ] ans s [ j ]  are not equal then increment j pointer 
and  make i=0 (as to start comparing from the initial letter 
of string )  

Once the loop terminates return ‘i’ as it contains the length 
of longest proper prefix which is same as the suffix


## Solution in java
```java
import java.util.Scanner;

class PrefixAndSuffix {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        int s_len = s.length();
        int count = 0;
        if (s_len > 1) {
            int suf_start = (s_len + 1) / 2;
            while (suf_start < s_len) {
                if (s.charAt(suf_start) == s.charAt(count)) {
                    count++;
                    suf_start++;
                } else {
                    suf_start = suf_start - count + 1;
                    count = 0;
                }
            }
        }
        System.out.println(count);
        sc.close();
    }
}
```