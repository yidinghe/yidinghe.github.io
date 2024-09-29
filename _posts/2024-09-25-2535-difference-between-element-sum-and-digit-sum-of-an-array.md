---
layout: post
title: 2535. Difference Between Element Sum and Digit Sum of an Array
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, math, easy]
author: Yiding He
---

## 2535. Difference Between Element Sum and Digit Sum of an Array

[Question Link](https://leetcode.cn/problems/difference-between-element-sum-and-digit-sum-of-an-array/description/)

You are given a positive integer array nums.

The element sum is the sum of all the elements in nums.
The digit sum is the sum of all the digits (not necessarily distinct) that appear in nums.
Return the absolute difference between the element sum and digit sum of nums.

Note that the absolute difference between two integers x and y is defined as |x - y|.

 

Example 1:

Input: nums = [1,15,6,3]
Output: 9
Explanation: 
The element sum of nums is 1 + 15 + 6 + 3 = 25.
The digit sum of nums is 1 + 1 + 5 + 6 + 3 = 16.
The absolute difference between the element sum and digit sum is |25 - 16| = 9.
Example 2:

Input: nums = [1,2,3,4]
Output: 0
Explanation:
The element sum of nums is 1 + 2 + 3 + 4 = 10.
The digit sum of nums is 1 + 2 + 3 + 4 = 10.
The absolute difference between the element sum and digit sum is |10 - 10| = 0.

### Note

{: .box-note}
**Note:** 算digit相加，和总数比较数量大小。


### Java

```java
class Solution {
    public int differenceOfSum(int[] nums) {
        int sum1 = 0;
        int sum2 = 0;
        for (int num: nums) {
            sum1 += num;
            sum2 += getDigitSum(num);
        }
        return Math.abs(sum1 - sum2);
    }
    private int getDigitSum(int num) {
        int sum = 0;
        while (num != 0) {
            sum += num % 10;
            num /= 10;
        }
        return sum;
    }
}
```

### Kotlin

```kotlin
import kotlin.math.abs

class Solution {
    fun differenceOfSum(nums: IntArray): Int {
        var sum1 = 0
        var sum2 = 0
        for (num in nums) {
            sum1 += num
            sum2 += getDigitNum(num)
        }
        return abs(sum1 - sum2)
    }

    private fun getDigitNum(num: Int): Int {
        var num = num
        var sum = 0
        while (num != 0) {
            sum += num % 10
            num /= 10
        }
        return sum
    }
}
```
