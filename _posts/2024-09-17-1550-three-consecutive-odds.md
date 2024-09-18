---
layout: post
title: 1550. Three Consecutive Odds
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, easy]
author: Yiding He
---

## 1550. Three Consecutive Odds

Given an integer array arr, return true if there are three consecutive odd numbers in the array. Otherwise, return false.
 

Example 1:

Input: arr = [2,6,4,1]
Output: false
Explanation: There are no three consecutive odds.
Example 2:

Input: arr = [1,2,34,3,4,5,7,23,12]
Output: true
Explanation: [5,7,23] are three consecutive odds.

### Java

```java
class Solution {
    public boolean threeConsecutiveOdds(int[] arr) {

        for (int i = 1; i < arr.length - 1; i++) {
            int first = arr[i - 1];
            int second = arr[i];
            int third = arr[i + 1];
            if (first % 2 == 1 && second % 2 == 1 && third % 2 == 1) {
                return true;
            }
        }

        return false;
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun threeConsecutiveOdds(arr: IntArray): Boolean {
        for (i in 1 until arr.size - 1) {
            val first = arr[i - 1]
            val second = arr[i]
            val third = arr[i + 1]
            if (first % 2 == 1 && second % 2 == 1 && third % 2 == 1) {
                return true
            }
        }

        return false
    }
}
```
