---
layout: post
title: Distance Between Bus Stops
subtitle: Java/Kotlin
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
author: Yiding He
---

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