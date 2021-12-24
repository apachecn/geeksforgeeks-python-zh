# 使用 Adaline 网络实现或门

> 原文:[https://www . geeksforgeeks . org/impering-or-gate-use-Adaline-network/](https://www.geeksforgeeks.org/implementing-or-gate-using-adaline-network/)

**Adline** 代表自适应线性神经元。它利用线性激活函数，并使用增量规则进行训练，以最小化实际输出和期望目标输出之间的均方误差。重量和偏差可调。这里，我们执行 10 个时期的训练，并计算每种情况下的总平均误差，总平均误差在某些时期后下降，随后变得几乎恒定。

**或门真值表**

<figure class="table">

| **x** | **y** | **x 或 y** |
| --- | --- | --- |
| -1 | -1 | -1 |
| -1 | one | one |
| one | -1 | one |
| one | one | one |

</figure>

下面是实现。

## 蟒蛇 3

```
# import the module numpy
import numpy as np

# the features for the or model , here we have
# taken the possible values for combination of
# two inputs
features = np.array(
    [
        [-1, -1],
        [-1, 1],
        [1, -1],
        [1, 1]
    ])

# labels for the or model, here the output for 
# the features is taken as an array
labels = np.array([-1, 1, 1, 1])

# to print the features and the labels for 
# which the model has to be trained
print(features, labels)

# initialise weights, bias , learning rate, epoch
weight = [0.5, 0.5]
bias = 0.1
learning_rate = 0.2
epoch = 10

for i in range(epoch):

    # epoch is the number of the the model is trained
    # with the same data
    print("epoch :", i+1)

    # variable to check if there is no change in previous
    # weight and present calculated weight
    # initial error is kept as 0
    sum_squared_error = 0.0

    # for each of the possible input given in the features
    for j in range(features.shape[0]):

        # actual output to be obtained
        actual = labels[j]

        # the value of two features as given in the features
        # array
        x1 = features[j][0]
        x2 = features[j][1]

        # net unit value computation performed to obtain the 
        # sum of features multiplied with their weights
        unit = (x1 * weight[0]) + (x2 * weight[1]) + bias

        # error is computed so as to update the weights
        error = actual - unit

        # print statement to print the actual value , predicted 
        # value and the error
        print("error =", error)

        # summation of squared error is calculated
        sum_squared_error += error * error

        # updation of weights, summing up of product of learning rate , 
        # sum of squared error and feature value
        weight[0] += learning_rate * error * x1
        weight[1] += learning_rate * error * x2

        # updation of bias, summing up of product of learning rate and 
        # sum of squared error
        bias += learning_rate * error

    print("sum of squared error = ", sum_squared_error/4, "\n\n")
```

**输出:**

```
[[-1 -1]
 [-1  1]
 [ 1 -1]
 [ 1  1]] [-1  1  1  1]
epoch : 1
error = -0.09999999999999998
error = 0.9199999999999999
error = 1.1039999999999999
error = -0.5247999999999999
sum of squared error =  0.5876577599999998 

epoch : 2
error = -0.54976
error = 0.803712
error = 0.8172543999999999
error = -0.64406528
sum of squared error =  0.5077284689412096 

epoch : 3
error = -0.6729103360000002
error = 0.7483308032
error = 0.7399630438400001
error = -0.6898669486079996
sum of squared error =  0.5090672560860652 

epoch : 4
error = -0.7047962935296
error = 0.72625757847552
error = 0.7201693816586239
error = -0.7061914301759491
sum of squared error =  0.5103845399996764 

epoch : 5
error = -0.7124421954738586
error = 0.7182636328518943
error = 0.7154472043637898
error = -0.7117071786082882
sum of squared error =  0.5104670846209363 

epoch : 6
error = -0.714060481354338
error = 0.715548426006041
error = 0.7144420989392495
error = -0.7134930727032405
sum of squared error =  0.5103479496309858 

epoch : 7
error = -0.7143209120714415
error = 0.7146705871452027
error = 0.7142737539596766
error = -0.7140502797165604
sum of squared error =  0.5102658027779979 

epoch : 8
error = -0.7143272889928647
error = 0.7143984993919014
error = 0.7142647152041359
error = -0.7142182126044045
sum of squared error =  0.510227607583693 

epoch : 9
error = -0.7143072010372341
error = 0.7143174255259156
error = 0.7142744539151652
error = -0.7142671011374249
sum of squared error =  0.5102124122866718 

epoch : 10
error = -0.7142946765305948
error = 0.7142942165270032
error = 0.7142809804050706
error = -0.7142808151475037
sum of squared error =  0.5102068786350209
```