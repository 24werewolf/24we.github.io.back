---
layout: post
title: leetcode easy count_prime
category: algorithm
tagline: "Supporting tagline"
tags: [leetcode, algorithm]
---
{% include JB/setup %}
# leetcode easy count_prime
---

####题目：

```
Count the number of prime numbers less than a non-negative number, n
```

####翻译：

```
计算比一个给定非负数n小的质数的个数。
```

####引用：

[How many primes are there?](https://primes.utm.edu/howmany.html "一共有多少个素数")


[Sieve of Eratosthenes](http://en.wikipedia.org/wiki/Sieve_of_Eratosthenes "Era筛选法")

####Tags：`Hash Table` `Math`
<!--break-->


####代码：


```
C：

int countPrimes(int n) {
	if(n < 3)
		return 0;
	else if(n == 3)
		return 1;
	else{
		int count = 1;
		int i = 0, j;
		int data;
		int len = n / 2;
		int array[len];

		//初始化奇数数组
		for(;i < len; i ++){
			data = 3 + 2 * i;
			if(data < n)
				array[i] = 3 + 2 * i;
			else
				array[i] = 0;
		}

		for(i = 0; i < len; i++){
			if(array[i] != 0)
				count++;
			else
				continue;
			for(j = i + array[i]; j < len; j+=array[i]){
				if(array[j] == 0)
					continue;
				array[j] = 0;
			}
		}

		return count;
	}
}

```

####讲解：

```
本体使用了引用中的欧拉筛选法，首先初始化一个小于n的奇数数组，然后将所有素数的倍数全部置为0，每次检索的步长等于素数的大小。
```
