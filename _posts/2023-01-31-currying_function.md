---
title: currying fuction
date: 2023-01-31 
categories: [cs61a]
tags: [cs61a]
---

<http://composingprograms.com/pages/16-higher-order-functions.html#currying>

*currying*: 将接受多个参数的函数转换为接受单个参数的一系列函数的转换。

f(2)(3)(4)(5) 从左到右计算

pow函数的curry版本:
```python
>>> def curried_pow(x):
        def h(y):
            return pow(x, y)
        return h
>>> curried_pow(2)(3)
8
```

计算2的前10次幂:
```python
>>> def map_to_range(start, end, f):
        while start < end:
            print(f(start))
            start = start + 1

>>> map_to_range(0, 10, curried_pow(2))
1
2
4
8
16
32
64
128
256
512
```
