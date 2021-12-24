# Python–直方图 _ 固定 _ 宽度 _ 箱()

> 原文:[https://www . geesforgeks . org/python-直方图 _fixed_width_bins/](https://www.geeksforgeeks.org/python-histogram_fixed_width_bins/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

**直方图 _ 固定 _ 宽度 _ 面元()**用于查找元素将被面元的索引。

> **语法** : tensorflow .直方图 _ fixed _ width _ bins(值、值 _ 范围、nbins、数据类型、名称)
> 
> **参数:**
> 
> *   **值**:数值张量。
> *   **value_range:** 是形状[2]的张量，其数据类型与 values 相同。
> *   **nbins(可选):**定义直方图中的箱数。默认值为 100。
> *   **数据类型(可选):**定义返回索引的数据类型。默认值为 int32。
> *   **名称(可选):**定义操作的名称。
> 
> **返回:**返回直方图值的张量。

**例 1:**

## 蟒蛇 3

```py
]# Importing the library
import tensorflow as tf

# Initializing the input
nbins = 6
value_range = [0.0, 6.0]
values = [3.0, 0.0, 1.5, 2.0, 5.0, 15.0]

# Finding histogram values
indices = tf.histogram_fixed_width_bins(values, value_range, nbins)

# Printing the result
print("res: ", indices.numpy())
```

**输出:**

```py
res:  [3 0 1 2 5 5]
```

**例 2:**

## 蟒蛇 3

```py
# Importing the library
import tensorflow as tf

# Initializing the input
nbins = 6
value_range = [0.0, 4.0]
values = [3.0, 0.0, 1.5, 2.0, 5.0, 1.0]

# Finding histogram values
indices = tf.histogram_fixed_width_bins(values, value_range, nbins)

# Printing the result
print("res: ", indices.numpy())
```

**输出:**

```py
res:  [4 0 2 3 5 1]
```