---
layout: post
title: 989. Add to Array-Form of Integer
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, design, heap, medium]
author: Yiding He
---

## 989. Add to Array-Form of Integer

[Question Link](https://leetcode.cn/problems/add-to-array-form-of-integer/description/)

The array-form of an integer num is an array representing its digits in left to right order.

For example, for num = 1321, the array form is [1,3,2,1].
Given num, the array-form of an integer, and an integer k, return the array-form of the integer num + k.

 

Example 1:

Input: num = [1,2,0,0], k = 34
Output: [1,2,3,4]
Explanation: 1200 + 34 = 1234
Example 2:

Input: num = [2,7,4], k = 181
Output: [4,5,5]
Explanation: 274 + 181 = 455
Example 3:

Input: num = [2,1,5], k = 806
Output: [1,0,2,1]
Explanation: 215 + 806 = 1021

### Note

{: .box-note}
**Note:** 套用加法模版，注意最后要翻转。


### Java
```java
class Solution {
    public List<Integer> addToArrayForm(int[] num, int k) {
        int n = num.length;
        int carry = 0;
        int i = n - 1;
        List<Integer> res = new ArrayList<>();
        while (i >= 0 || k != 0) {
            int x = i >= 0 ? num[i] : 0;
            int y = k != 0 ? k % 10 : 0;
            int sum = x + y + carry;
            res.add(sum % 10);
            carry = sum / 10;
            k = k / 10;
            i--;
        }

        if (carry != 0) {
            res.add(carry);
        }
        Collections.reverse(res);
        return res;
    }
}
```


### Kotlin
```kotlin
class Solution {
    fun addToArrayForm(num: IntArray, k: Int): List<Int> {
        val res = mutableListOf<Int>()
        val n = num.size
        var carry = 0
        var i = n - 1
        var k = k
        while (i >= 0 || k != 0) {
            val x = if (i >= 0) num[i] else 0
            val y = if (k != 0) k % 10 else 0
            val sum = x + y + carry
            res.add(sum % 10)
            carry = sum / 10
            k = k / 10
            i--
        }
        if (carry > 0) {
            res.add(carry)
        }
        res.reverse()
        return res
    }
}
```
