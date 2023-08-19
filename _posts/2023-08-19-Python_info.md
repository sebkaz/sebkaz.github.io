---
title: "Python vs Julia"
date: 2023-08-19
---

# Python vs Julia

What is the difference between Python and Julia? and which one is better?

If you use both for mathematical calculations, you will find that Julia is much faster than Python. 
However, Python is more popular than Julia, and there are many libraries that can be used in Python.
When i red about Neural Networks, i found informations how to use Python numpy to get fast matrix calculations.

In this short post I whant show You one example where python give you ,,bad'' (no mathematical correct) result.

## Example sum of columns and rows
```python
import numpy as np
# our simple matrix
a = np.array([[1,2],[3,4]])
print(a)
# [[1 2],
# [3 4]]
# sum by rows
```
Let's compute simple sum of rows and columns
```python
np.sum(a, axis=0)
# array([4, 6])
np.sum(a, axis=1)
# array([3, 7])
```
As You can see it does not matter if we sum by rows or columns, we get the same shape of result. 

But from elementary maths we know that sum of rows and columns should be transposed.

Let's see how it looks in Julia
```julia
a = [1 2; 3 4]
# 2×2 Matrix{Int64}:
# 1  2
# 3  4
sum(a, dims=1)
# 1×2 Matrix{Int64}:
# 4  6
sum(a, dims=2)
# 2×1 Matrix{Int64}:
# 3
# 7
```
So You see that in Julia we get correct result.


```
