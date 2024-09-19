---
layout: post
title: 867. Transpose Matrix
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, easy]
author: Yiding He
---

## 867. Transpose Matrix

Given a 2D integer array matrix, return the transpose of matrix.

The transpose of a matrix is the matrix flipped over its main diagonal, switching the matrix's row and column indices.



 

Example 1:

Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[1,4,7],[2,5,8],[3,6,9]]
Example 2:

Input: matrix = [[1,2,3],[4,5,6]]
Output: [[1,4],[2,5],[3,6]]


### Java

```java
class Solution {
    public int[][] transpose(int[][] matrix) {
        int m = matrix.length;
        int n = matrix[0].length;
        int[][] res = new int[n][m];

        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                res[j][i] = matrix[i][j];
            }
        }
        return res;
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun transpose(matrix: Array<IntArray>): Array<IntArray> {
        val m = matrix.size;
        val n = matrix[0].size;
        val res = Array(n) {IntArray(m)}
        for (i in 0 until m) {
            for (j in 0 until n) {
                res[j][i] = matrix[i][j]
            }
        }
        return res
    }
}
```
