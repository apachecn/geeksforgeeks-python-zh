# Python Hard |keras.utils.to_categorical（）

> 原文:[https://www . geesforgeks . org/python-keras-keras-utils-to _ classic/](https://www.geeksforgeeks.org/python-keras-keras-utils-to_categorical/)

Keras 提供了 numpy 实用程序库，它提供了在 numpy 数组上执行操作的函数。使用 to _ classic()方法，numpy 数组(或)具有代表不同类别的整数的向量可以转换为 numpy 数组(或)具有二进制值且列数等于数据中类别数的矩阵。

**语法:**TF . keras . utils . to _ classic(y，num _ classes = None，dtype="float32 ")

**参数:**

```
y (input vector): A vector which has integers representing various classes in the data.

num_classes: Total number of classes. If nothing is mentioned, it considers the largest number of the input vector and adds 1, to get the number of classes.
Its default value is "None".

dtype: It is the desired data type of the output values. 
By default, it's value is 'float32'.
```

**输出:**
该函数返回一个二进制值矩阵(1 或 0)。它的行数等于输入向量的长度，列数等于类的数量。

**代码:将 Cifar10 数据集标签向量转换为分类数据矩阵:**

## 蟒蛇 3

```
# Loading the dataset

from keras.datasets import cifar10
(train_images, train_labels), (test_images, test_labels)= cifar10.load_data()

# Labels before applying the function
# Training set labels
print(train_labels)
print(train_labels.shape)

# Testing set labels
print(test_labels)
print(test_labels.shape)

# Applying the function to training set labels and testing set labels
from keras.utils import to_categorical
train_labels = to_categorical(train_labels, dtype ="uint8")
test_labels = to_categorical(test_labels, dtype ="uint8")

# Labels after applying the function
# Training set labels
print(train_labels)
print(train_labels.shape)

# Testing set labels
print(test_labels)
print(test_labels.shape)
```

**输出:**

```
***#Labels before applying the function***
#Training set labels
array([[6],
       [9],
       [9],
       ...,
       [9],
       [1],
       [1]], dtype=uint8)

#Training set labels shape
(50000, 1)

#Testing set labels
array([[3],
       [8],
       [8],
       ...,
       [5],
       [1],
       [7]], dtype=uint8)

#Testing set labels shape
(10000, 1)

***#Labels after applying the function***
#Training set labels
[[0 0 0 ... 0 0 0]
 [0 0 0 ... 0 0 1]
 [0 0 0 ... 0 0 1]
 ...
 [0 0 0 ... 0 0 1]
 [0 1 0 ... 0 0 0]
 [0 1 0 ... 0 0 0]]

#Training set labels shape
(50000, 10)

#Testing set labels
[[0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 0\. 1\. 0.]
 [0\. 0\. 0\. ... 0\. 1\. 0.]
 ...
 [0\. 0\. 0\. ... 0\. 0\. 0.]
 [0\. 1\. 0\. ... 0\. 0\. 0.]
 [0\. 0\. 0\. ... 1\. 0\. 0.]]

#Testing set labels shape
(10000, 10)
```

**代码:考虑一个 7 类的输入向量。(它的值范围可以从 0 到 6(n-1))。**

## 蟒蛇 3

```
# Initializing Input vector
class_vector =[2, 5, 6, 1, 4, 2, 3, 2]
print(class_vector)

# Applying the function on input class vector
from keras.utils import to_categorical
output_matrix = to_categorical(class_vector, num_classes = 7, dtype ="int32")

print(output_matrix)
```

**输出:**

```
[[0 0 1 0 0 0 0]
 [0 0 0 0 0 1 0]
 [0 0 0 0 0 0 1]
 [0 1 0 0 0 0 0]
 [0 0 0 0 1 0 0]
 [0 0 1 0 0 0 0]
 [0 0 0 1 0 0 0]
 [0 0 1 0 0 0 0]]
```