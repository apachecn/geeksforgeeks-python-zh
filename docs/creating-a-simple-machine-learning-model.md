# 创建简单的机器学习模型

> 原文:[https://www . geesforgeks . org/creating-a-simple-machine-learning-model/](https://www.geeksforgeeks.org/creating-a-simple-machine-learning-model/)

使用随机创建的数据集在 Python 中创建线性回归模型。

**线性回归模型**
[线性回归极客为极客](https://www.geeksforgeeks.org/linear-regression-python-implementation/)

**生成训练集**

```py
# python library to generate random numbers
from random import randint

# the limit within which random numbers are generated
TRAIN_SET_LIMIT = 1000

# to create exactly 100 data items
TRAIN_SET_COUNT = 100

# list that contains input and corresponding output
TRAIN_INPUT = list()
TRAIN_OUTPUT = list()

# loop to create 100 data  items with three columns each
for i in range(TRAIN_SET_COUNT):
    a = randint(0, TRAIN_SET_LIMIT)
    b = randint(0, TRAIN_SET_LIMIT)
    c = randint(0, TRAIN_SET_LIMIT)

# creating the output for each data item
    op = a + (2 * b) + (3 * c)
    TRAIN_INPUT.append([a, b, c])

# adding each output to output list
    TRAIN_OUTPUT.append(op)
```

**机器学习模型–线性回归**

模型可以分两步创建:-
1。**用训练数据
2 训练**模型。**用测试数据测试**模型

**训练模型**
使用上述代码创建的数据用于训练模型

```py
# Sk-Learn contains the linear regression model
from sklearn.linear_model import LinearRegression

# Initialize the linear regression model
predictor = LinearRegression(n_jobs =-1)

# Fill the Model with the Data
predictor.fit(X = TRAIN_INPUT, y = TRAIN_OUTPUT)
```

**测试数据**
测试是手动完成的。可以使用一些随机数据进行测试，并测试模型是否给出了输入数据的正确结果。

```py
# Random Test data
X_TEST = [[ 10, 20, 30 ]]

# Predict the result of X_TEST which holds testing data
outcome = predictor.predict(X = X_TEST)

# Predict the coefficients
coefficients = predictor.coef_

# Print the result obtained for the test data
print('Outcome : {}\nCoefficients : {}'.format(outcome, coefficients))
```

上面提供的测试数据的结果应该是， **10 + 20*2 + 30*3 = 140。**
**输出**

```py
Outcome : [ 140.]
Coefficients : [ 1\. 2\. 3.]

```