[![](https://img.shields.io/github/stars/javadev/LeetCode-in-Kotlin?label=Stars&style=flat-square)](https://github.com/javadev/LeetCode-in-Kotlin)
[![](https://img.shields.io/github/forks/javadev/LeetCode-in-Kotlin?label=Fork%20me%20on%20GitHub%20&style=flat-square)](https://github.com/javadev/LeetCode-in-Kotlin/fork)

## 110\. Balanced Binary Tree

Easy

Given a binary tree, determine if it is height-balanced.

For this problem, a height-balanced binary tree is defined as:

> a binary tree in which the left and right subtrees of _every_ node differ in height by no more than 1.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/06/balance_1.jpg)

**Input:** root = [3,9,20,null,null,15,7]

**Output:** true

**Example 2:**

![](https://assets.leetcode.com/uploads/2020/10/06/balance_2.jpg)

**Input:** root = [1,2,2,3,3,null,null,4,4]

**Output:** false

**Example 3:**

**Input:** root = []

**Output:** true

**Constraints:**

*   The number of nodes in the tree is in the range `[0, 5000]`.
*   <code>-10<sup>4</sup> <= Node.val <= 10<sup>4</sup></code>

## Solution

```kotlin
import com_github_leetcode.TreeNode

class Solution {
    fun isBalanced(root: TreeNode?): Boolean {
        fun heightOrFail(node: TreeNode?): Int {
            if (node == null) return 0
            val lh = heightOrFail(node.left)
            if (lh == -1) return -1
            val rh = heightOrFail(node.right)
            if (rh == -1) return -1
            if (kotlin.math.abs(lh - rh) > 1) return -1
            return 1 + maxOf(lh, rh)
        }
        return heightOrFail(root) != -1
    }
}
```
