---
layout: post
title: 2414. Length of the Longest Alphabetical Continuous Substring
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, string, medium]
author: Yiding He
---

## 2414. Length of the Longest Alphabetical Continuous Substring

[Question Link](https://leetcode.cn/problems/length-of-the-longest-alphabetical-continuous-substring/description/)

An alphabetical continuous string is a string consisting of consecutive letters in the alphabet. In other words, it is any substring of the string "abcdefghijklmnopqrstuvwxyz".

For example, "abc" is an alphabetical continuous string, while "acb" and "za" are not.
Given a string s consisting of lowercase letters only, return the length of the longest alphabetical continuous substring.

 

Example 1:

Input: s = "abacaba"
Output: 2
Explanation: There are 4 distinct continuous substrings: "a", "b", "c" and "ab".
"ab" is the longest continuous substring.
Example 2:

Input: s = "abcde"
Output: 5
Explanation: "abcde" is the longest continuous substring.

### Note

{: .box-note}
**Note:** 计数，一个变量记录当前的max值，一个变量循环中有上升就继续加加，最后比大小。


### Java

```java
class Solution {
    public int longestContinuousSubstring(String s) {
        int res = 1; 
        int cur = 1;
        for (int i = 1; i < s.length(); i++) {
            if (s.charAt(i) == s.charAt(i - 1) + 1) {
                cur++;
            } else {
                cur = 1;
            }
            res = Math.max(res, cur);
        }
        return res;
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun longestContinuousSubstring(s: String): Int {
        var res = 1
        var cur = 1
        for (i in 1 until s.length) {
            if (s[i] == s[i - 1] + 1) {
                cur++
            } else {
                cur = 1
            }
            res = maxOf(res, cur)
        }
        return res
    }
}
```
