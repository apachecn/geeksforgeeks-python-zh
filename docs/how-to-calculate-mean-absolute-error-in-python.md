# 如何用 Python 计算平均绝对误差？

> 原文:[https://www . geesforgeks . org/如何计算 python 中的平均绝对误差/](https://www.geeksforgeeks.org/how-to-calculate-mean-absolute-error-in-python/)

平均绝对误差计算计算值和实际值之间的平均差异。它也被称为与尺度相关的精度，因为它计算的是同一尺度上观测值的误差。它被用作机器学习中回归模型的评估指标。它计算实际值和模型预测值之间的误差。它用于预测机器学习模型的准确性。

**公式:**

> 平均绝对误差=(1/n)*∑| y<sub>I</sub>–x<sub>I</sub>|
> 
> 哪里，
> 
> *   σ:求和的希腊符号
> *   y <sub>i</sub> :第一次观测的实际值
> *   x <sub>i</sub> :第一次观测的计算值
> *   n:观察总数

## 方法 1:使用实际公式

平均绝对误差(MAE)的计算方法是取整个阵列上每个观测值的实际值和计算值之间的绝对差值之和，然后除以阵列中观测值的数量。

**例**:

## 蟒蛇 3

```py
# Python program for calculating Mean Absolute Error

# consider a list of integers for actual
actual = [2, 3, 5, 5, 9]

# consider a list of integers for actual
calculated = [3, 3, 8, 7, 6]

n = 5
sum = 0

# for loop for iteration
for i in range(n):
    sum += abs(actual[i] - calculated[i])

error = sum/n

# display
print("Mean absolute error : " + str(error))
```

**Output**

```py
Mean absolute error : 1.8
```

## 方法 2:使用 sklearn

python 的 sklearn.metrics 模块包含用于计算不同用途的错误的函数。它提供了一个名为 mean_absolute_error()的方法来计算给定数组的平均绝对误差。

**语法**:

```py
mean_absolute_error(actual,calculated)
```

在哪里

*   实际值数组作为第一个参数
*   计算–预测/计算值数组作为第二个参数

它将返回给定数组的平均绝对误差。

**例**:

## 蟒蛇 3

```py
# Python program for calculating Mean Absolute
# Error using sklearn

# import the module
from sklearn.metrics import mean_absolute_error as mae

# list of integers of actual and calculated
actual = [2, 3, 5, 5, 9]
calculated = [3, 3, 8, 7, 6]

# calculate MAE
error = mae(actual, calculated)

# display
print("Mean absolute error : " + str(error))
```

**输出**

```py
Mean absolute error : 1.8
```