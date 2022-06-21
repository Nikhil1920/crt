---
title: Minimum Loss
published: 2021-08-26T09:45:00
updated: 2021-08-26T09:45:00
tags: ["Practice Problems", "crt"]
---

## Problem Statement:

Lauren has a chart of distinct projected prices for a house
over the next several years. She must buy the house in one
year and sell it in another, and she must do so at a loss. She
wants to minimize her financial loss.

## Problem Explanation:

Here you are given an array of integers representing prices of
house from which Lauren can buy the house in one year and sell
it in another year (definitely after buying the house) and she
must the sell the house in such a way that sold price < bought
price of the house and the loss should be minimal.

## Program Logic:

Here we are suppose to sell the house only after we buy it in
the previous year. So we assume that we are selling the house
at each year and try to find the cost from previous years
which is nearest and greater than every current year such that
it might appear that Lauren has bought the house in that year
and sold it with min loss.

## Example:

Prices = [ 20, 15, 8, 2, 12]

Min Loss = 12 - 15 = 3

If Lauren buys the house in the 2nd year for 15 and sells the
house at 12 then this solution will be minimum loss in her
finance.

You can try any other combination of buying and selling the
house the loss might increase.

## Solution in java

```java
import java.util.*;

class MinimumLoss {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        long arr[] = new long[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextLong();
        }
        Map<Long, Integer> map = new HashMap<>();
        for (int i = 0; i < arr.length; i++) {
            map.put(arr[i], i);
        }
        Arrays.sort(arr);
        long loss = Long.MAX_VALUE;
        for (int i = arr.length - 1; i > 0; i--) {
            if (map.get(arr[i]) < map.get(arr[i - 1])) {
                loss = Math.min(arr[i] - arr[i - 1], loss);
            }
        }
        System.out.println(loss);
        sc.close();
    }
}
```
