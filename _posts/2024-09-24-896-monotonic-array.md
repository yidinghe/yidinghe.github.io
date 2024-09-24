---
layout: post
title: 896. Monotonic Array
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, easy]
author: Yiding He
---

## 896. Monotonic Array

An array is monotonic if it is either monotone increasing or monotone decreasing.

An array nums is monotone increasing if for all i <= j, nums[i] <= nums[j]. An array nums is monotone decreasing if for all i <= j, nums[i] >= nums[j].

Given an integer array nums, return true if the given array is monotonic, or false otherwise.

 

Example 1:

Input: nums = [1,2,2,3]
Output: true
Example 2:

Input: nums = [6,5,4,4]
Output: true
Example 3:

Input: nums = [1,3,2]
Output: false



### Java

```java
class Solution {
    public boolean isMonotonic(int[] nums) {
        return isSorted(nums, true) || isSorted(nums, false);
    }

    private boolean isSorted(int[] nums, boolean isIncrease) {
        int n = nums.length;
        if (isIncrease) {
            for (int i = 0; i < n - 1; i++) {
                if (nums[i] > nums[i + 1]) {
                    return false;
                }
            }
        } else {
            for (int i = 0; i < n - 1; i++) {
                if (nums[i] < nums[i + 1]) {
                    return false;
                }
            }
        }
        return true;
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun isMonotonic(nums: IntArray): Boolean {
        return isSorted(nums, true) || isSorted(nums, false)
    }
    fun isSorted(nums: IntArray, isIncrease: Boolean): Boolean {
        val n = nums.size
        if (isIncrease) {
            for (i in 0 until n - 1) {
                if (nums[i] > nums[i + 1] ) {
                    return false
                }
            }
        } else {
            for (i in 0 until n - 1) {
                if (nums[i] < nums[i + 1]) {
                    return false
                }
            }
        }
        return true
    }
}
```
