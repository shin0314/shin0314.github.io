---
title: Floating Point Error
date: 2023-02-03 
categories: [cs61a]
tags: [cs61a]
---

如果做大规模计算 中间可能损失很多精度

### 保留小数点前n位

eg. 5/3的小数点前三位

方法1：
```python
round(5/3 * 1000) / 1000
```

方法2：
```python
round(5/3, 3)
```
