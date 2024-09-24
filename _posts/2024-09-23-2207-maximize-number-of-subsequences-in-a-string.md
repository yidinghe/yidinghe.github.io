---
layout: post
title: 2207. Maximize Number of Subsequences in a String
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, greedy, string, medium]
author: Yiding He
---
## 2207. Maximize Number of Subsequences in a String
You are given a 0-indexed string text and another 0-indexed string pattern of length 2, both of which consist of only lowercase English letters.
You can add either pattern[0] or pattern[1] anywhere in text exactly once. Note that the character can be added even at the beginning or at the end of text.
Return the maximum number of times pattern can occur as a subsequence of the modified text.
A subsequence is a string that can be derived from another string by deleting some or no characters without changing the order of the remaining characters.
 
Example 1:
Input: text = "abdcdbc", pattern = "ac"
Output: 4
Explanation:
If we add pattern[0] = 'a' in between text[1] and text[2], we get "abadcdbc". Now, the number of times "ac" occurs as a subsequence is 4.
Some other strings which have 4 subsequences "ac" after adding a character to text are "aabdcdbc" and "abdacdbc".
However, strings such as "abdcadbc", "abdccdbc", and "abdcdbcc", although obtainable, have only 3 subsequences "ac" and are thus suboptimal.
It can be shown that it is not possible to get more than 4 subsequences "ac" by adding only one character.
Example 2:
Input: text = "aabb", pattern = "ab"
Output: 6
Explanation:
Some of the strings which can be obtained from text and have 6 subsequences "ab" are "aaabb", "aaabb", and "aabbb".
### Java
```java
class Solution {
    public long maximumSubsequenceCount(String s, String pattern) {
        long res = 0;
        int cnt1 = 0, cnt2 = 0;
        for (int i = 0; i < s.length(); ++i) {
            if (s.charAt(i) == pattern.charAt(1)) {
                res += cnt1;
                cnt2++;
            }
            if (s.charAt(i) == pattern.charAt(0)) {
                cnt1++;
            }
        }
        return res + Math.max(cnt1, cnt2);
    }
}
```
### Kotlin
```kotlin
class Solution {
    fun maximumSubsequenceCount(text: String, pattern: String): Long {
        var res = 0.toLong()
        var count1 = 0
        var count2 = 0
        for (i in text.indices) {
            if (text[i] == pattern[1]) {
                res += count1
                count2++
            }
            if (text[i] == pattern[0]) {
                count1++
            }
        }
        return res + maxOf(count1, count2)
    }
}
```
