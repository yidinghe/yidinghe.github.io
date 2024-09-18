---
layout: post
title: 1184. Distance Between Bus Stops
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [algorithm, array, easy]
author: Yiding He
---

## 1184. Distance Between Bus Stops

A bus has n stops numbered from 0 to n - 1 that form a circle. We know the distance between all pairs of neighboring stops where distance[i] is the distance between the stops number i and (i + 1) % n.

The bus goes along both directions i.e. clockwise and counterclockwise.

Return the shortest distance between the given start and destination stops.

 

Example 1:



Input: distance = [1,2,3,4], start = 0, destination = 1
Output: 1
Explanation: Distance between 0 and 1 is 1 or 9, minimum is 1.
 

Example 2:



Input: distance = [1,2,3,4], start = 0, destination = 2
Output: 3
Explanation: Distance between 0 and 2 is 3 or 7, minimum is 3.
 

Example 3:



Input: distance = [1,2,3,4], start = 0, destination = 3
Output: 4
Explanation: Distance between 0 and 3 is 6 or 4, minimum is 4.

### Java

```java
class Solution {
    public int distanceBetweenBusStops(int[] distance, int start, int destination) {
        if (start > destination) {
            int temp = destination;
            destination = start;
            start = temp;
        }
        int sum1 = 0;
        int sum2 = 0;
        for (int i = 0; i < distance.length; i++) {
            if (i >= start && i < destination) {
                sum1 += distance[i];
            } else {
                sum2 += distance[i];
            }
        }

        return Math.min(sum1, sum2);
    }
}
```

### Kotlin

```kotlin
class Solution {
    fun distanceBetweenBusStops(distance: IntArray, start: Int, destination: Int): Int {
        var start = start
        var destination = destination
        if (start > destination) {
            val temp = start
            start = destination
            destination = temp
        }
        var sum1 = 0
        var sum2 = 0
        for (i in distance.indices) {
            if (i in start until destination) {
                sum1 += distance[i]
            } else {
                sum2 += distance[i]
            }
        }
        return minOf(sum1, sum2)
    }
}
```
