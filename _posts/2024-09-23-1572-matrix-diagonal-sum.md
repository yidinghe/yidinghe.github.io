---
layout: post
title: 1572. Matrix Diagonal Sum
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, matrix, easy]
author: Yiding He
---

## 1572. Matrix Diagonal Sum

[Question Link](https://leetcode.cn/problems/matrix-diagonal-sum/description/)

Given a square matrix mat, return the sum of the matrix diagonals.

Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.

 

Example 1:


Input: mat = [[1,2,3],
              [4,5,6],
              [7,8,9]]
Output: 25
Explanation: Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25
Notice that element mat[1][1] = 5 is counted only once.
Example 2:

Input: mat = [[1,1,1,1],
              [1,1,1,1],
              [1,1,1,1],
              [1,1,1,1]]
Output: 8
Example 3:

Input: mat = [[5]]
Output: 5

### Note

{: .box-note}
**Note:** 矩阵走一遍，把i==j和i+j==n-1的元素全部相加即可。

### Java

```java
class Solution {
    public int diagonalSum(int[][] mat) {
        int n = mat.length;
        int sum = 0;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i == j || i + j == n - 1) {
                    sum += mat[i][j];
                }
            }
        }
        return sum;
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun diagonalSum(mat: Array<IntArray>): Int {
        val n = mat.size
        var sum = 0
        for (i in 0 until n) {
            for (j in 0 until n) {
                if (i == j || i + j == n - 1) {
                    sum += mat[i][j]
                }
            }
        }
        return sum
    }
}
```
