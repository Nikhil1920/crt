---
title: Big Sorting
published: 2021-09-31T09:38:00
updated: 2021-09-31T09:38:00
tags: ["daily-contest", "java", "31-09-2021"]
---
Consider an array of numeric strings where each string is a positive number 
with anywhere from  to  digits. Sort the array's elements in non-decreasing, 
or ascending order of their integer values and return the sorted array.

## Example
unsorted = ['1', '200', '150', '3']\
Return the array ['1', '3', '150', '200'].

## Function Description

Complete the bigSorting function in the editor below.

bigSorting has the following parameter(s):

- string unsorted[n]: an unsorted array of integers as strings

## Returns

- string[n]: the array sorted in numerical order

## Input Format

The first line contains an integer, n, the number of strings in unsorted.
Each of the n subsequent lines contains an integer string, unsorted[i].

## Constraints

- Each string is guaranteed to represent a positive integer.
- There will be no leading zeros.
- The total number of digits across all strings in unsorted is between 1 and pow(10, 6) (inclusive).

## Sample Input 0
```
6
31415926535897932384626433832795
1
3
10
3
5
```

## Sample Output 0
```
1
3
3
5
10
31415926535897932384626433832795
```

## Big Sorting Solution in python
```py
num = int(input())
unsorted = []
for _ in range(num):
    unsorted_item = input()
    unsorted.append(unsorted_item)

for element in sorted(unsorted, key=int):
    print(element)
```