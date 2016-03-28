---
layout: post
title: leetcode medium single number
category: algorithm
tagline: "Supporting tagline"
tags: [leetcode, algorithm]
---
{% include JB/setup %}
# leetcode medium single number
---

####题目：

```
Given an array of integers, every element appears twice except for one. Find that single one.

有一个整数数组，其中的元素只有一个出现了一次，其他的均出现了两次，请找出只出现了一次的元素。
```


####注意：

```
Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

你的算法的时间复杂度应该是线性的。你能够不使用额外内存实现这个算法吗？
```
<!--break-->

####Tags：`Hash Table` `Bit Manipulation`


####代码：


```
Java：

public class Solution {
    public int singleNumber(int[] A) {
        int result = 0;

        for(int i=0;i<A.length;i++)
        	result ^= A[i];
        return result;
    }
}
```

####讲解：

```
本题利用了bit操作XOR，写法为'^'，特性为a^a=0，即所有出现两次的元素进行异或操作后均变为0，则剩下的元素即为所求。
这个算法可以扩展到除了一个元素，其他元素均出现偶数次的情况使用。
```
