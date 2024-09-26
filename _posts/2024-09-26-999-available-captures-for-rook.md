---
layout: post
title: 999. Available Captures for Rook
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, matrix, easy]
author: Yiding He
---

## 999. Available Captures for Rook

You are given an 8 x 8 matrix representing a chessboard. There is exactly one white rook represented by 'R', some number of white bishops 'B', and some number of black pawns 'p'. Empty squares are represented by '.'.

A rook can move any number of squares horizontally or vertically (up, down, left, right) until it reaches another piece or the edge of the board. A rook is attacking a pawn if it can move to the pawn's square in one move.

Note: A rook cannot move through other pieces, such as bishops or pawns. This means a rook cannot attack a pawn if there is another piece blocking the path.

Return the number of pawns the white rook is attacking.

 

Example 1:


Input: board = [[".",".",".",".",".",".",".","."],[".",".",".","p",".",".",".","."],[".",".",".","R",".",".",".","p"],[".",".",".",".",".",".",".","."],[".",".",".",".",".",".",".","."],[".",".",".","p",".",".",".","."],[".",".",".",".",".",".",".","."],[".",".",".",".",".",".",".","."]]

Output: 3

Explanation:

In this example, the rook is attacking all the pawns.

Example 2:


Input: board = [[".",".",".",".",".",".","."],[".","p","p","p","p","p",".","."],[".","p","p","B","p","p",".","."],[".","p","B","R","B","p",".","."],[".","p","p","B","p","p",".","."],[".","p","p","p","p","p",".","."],[".",".",".",".",".",".",".","."],[".",".",".",".",".",".",".","."]]

Output: 0

Explanation:

The bishops are blocking the rook from attacking any of the pawns.

Example 3:


Input: board = [[".",".",".",".",".",".",".","."],[".",".",".","p",".",".",".","."],[".",".",".","p",".",".",".","."],["p","p",".","R",".","p","B","."],[".",".",".",".",".",".",".","."],[".",".",".","B",".",".",".","."],[".",".",".","p",".",".",".","."],[".",".",".",".",".",".",".","."]]

Output: 3

Explanation:

The rook is attacking the pawns at positions b5, d6, and f5.


### Java

```java
class Solution {
    fun numRookCaptures(board: Array<CharArray>): Int {
        var count = 0
        var sx = 0
        var sy = 0
        val dx = intArrayOf(0, 1, 0, -1)
        val dy = intArrayOf(1, 0, -1, 0)
        for (i in 0 until 8) {
            for (j in 0 until 8) {
                if (board[i][j] == 'R') {
                    sx = i
                    sy = j
                    break
                }
            }
        }
        for (i in 0 until 4) {
            for (step in 1 until 8) {
                val nx = sx + step * dx[i]
                val ny = sy + step * dy[i]
                if (nx < 0 || nx >= 8 || ny < 0 || ny >= 8 || board[nx][ny] == 'B') {
                    break
                }
                if (board[nx][ny] == 'p') {
                    count++
                    break
                }
            }
        }

        return count
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun numRookCaptures(board: Array<CharArray>): Int {
        var count = 0
        var sx = 0
        var sy = 0
        val dx = intArrayOf(0, 1, 0, -1)
        val dy = intArrayOf(1, 0, -1, 0)
        for (i in 0 until 8) {
            for (j in 0 until 8) {
                if (board[i][j] == 'R') {
                    sx = i
                    sy = j
                    break
                }
            }
        }
        for (i in 0 until 4) {
            for (step in 1 until 8) {
                val nx = sx + step * dx[i]
                val ny = sy + step * dy[i]
                if (nx < 0 || nx >= 8 || ny < 0 || ny >= 8 || board[nx][ny] == 'B') {
                    break
                }
                if (board[nx][ny] == 'p') {
                    count++
                    break
                }
            }
        }

        return count
    }
}
```
