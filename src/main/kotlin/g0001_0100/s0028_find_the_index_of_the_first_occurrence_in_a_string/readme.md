[![](https://img.shields.io/github/stars/javadev/LeetCode-in-Kotlin?label=Stars&style=flat-square)](https://github.com/javadev/LeetCode-in-Kotlin)
[![](https://img.shields.io/github/forks/javadev/LeetCode-in-Kotlin?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/javadev/LeetCode-in-Kotlin/fork)

## 28\. Find the Index of the First Occurrence in a String

Medium

Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.

**Example 1:**

**Input:** haystack = "sadbutsad", needle = "sad"

**Output:** 0

**Explanation:** "sad" occurs at indices 0 and 6. The first occurrence is at index 0, so we return 0.

**Example 2:**

**Input:** haystack = "leetcode", needle = "leeto"

**Output:** -1

**Explanation:** "leeto" did not occur in "leetcode", so we return -1.

**Constraints:**

*   <code>1 <= haystack.length, needle.length <= 10<sup>4</sup></code>
*   `haystack` and `needle` consist of only lowercase English characters.

## Solution

```kotlin
class Solution {
    fun strStr(h: String, p: String): Int {
        val m = h.length; val n = p.length
        if (n == 0) return 0
        if (n > m) return -1
        for (i in 0..m - n) {
            var j = 0
            while (j < n && h[i + j] == p[j]) j++
            if (j == n) return i
        }
        return -1
    }
}
```
