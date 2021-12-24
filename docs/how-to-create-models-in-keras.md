# 如何在 Keras 中创建模型？

> 原文:[https://www . geesforgeks . org/如何创建模型 in-keras/](https://www.geeksforgeeks.org/how-to-create-models-in-keras/)

Keras 是一个开源 API，用于解决各种现代机器学习和深度学习问题。它使用户能够更多地关注深度学习的逻辑方面，而不是暴力编码方面。Keras 是一个极其强大的应用编程接口，通过减少用户的工作量，提供卓越的可扩展性、灵活性和认知便利性。它是用 Python 编写的，使用 TensorFlow 或 antao 作为后端。

## 喀拉斯的模特

Keras 中的典型模型是多个训练和推理层的集合。使用 Keras 创建模型有两种广泛的方法。

### 功能性应用编程接口

功能应用编程接口处理具有不同功能的非线性模型。这些模型极具可扩展性和灵活性。您可以指定神经网络的正向传递，从输入开始，一直到输出，以创建个性化模型。它提供了一种弹性架构，其中成对的层可以以任何方式连接到多个层。功能性应用编程接口可以说是构建层次图和自组织非循环网络图的一种方式。这有助于用户极其轻松地定制像暹罗网络这样的复杂网络。使用功能性应用编程接口创建模型是一个多步骤的过程，在此定义。

#### 1.)定义输入

使用功能 API 创建 Keras 模型的第一步是定义输入层。输入层接受实际上是元组的*形状*参数。这用于定义输入的维度。

## 蟒 3

```py
# defining Input
from keras.layers import Input
visible = Input(shape=(10,))
```

前述一维输入的最后一个维度总是被挂起，以便补偿在分割数据用于训练、测试和验证时使用的小批量的形状。因此，空缺出现在“*逗号*之后。

#### 2.)连接层

在我们创建了输入层之后，我们现在将创建一个密集的隐藏层。这个隐藏层应该连接到我们的输入层，并从它接收输入。

T2T4

```py
# connecting layers
from keras.layers import Input
from keras.layers import Dense
visible = Input(shape=(10,))
# now connecting hidden layer to visible input layer
hidden = Dense(2)(visible)
```

T5

这是隐藏层与可见输入层的连接方式。*密集*层用于将输出从一层神经元传递到另一层神经元作为输入。

请注意，在这种情况下，由于个人需求，只有一个层的输入被传递到输出层。然而，函数模型允许将多个输入输入到神经网络中，以获得多个输出。功能模型非常受欢迎，因为它很容易建立连接。现在，您可以添加任意数量的层。

#### 3.)创建您的模型

现在可以使用模型类以最简单的方式创建所需的模型。只需要定义输入和输出层。

T2T4

```py
#import all required modules
from keras.models import Model
from keras.layers import Input
from keras.layers import Dense
visible = Input(shape=(10,))
hidden = Dense(2)(visible)
model = Model(inputs=visible, outputs=hidden)
```

T5

现在创建的模型输入是可见层，输出是隐藏层。这就是功能性应用编程接口如何帮助用户创建神经网络模型而没有任何麻烦。

### 顺序应用编程接口

顺序应用编程接口是一个稍不完善的应用编程接口，用于模拟更简单的神经网络。网络中的每一层只接受一个输入，传递一个输出。需要注意的是，当模型需要多个输入或输出或者需要共享层时，顺序模型不起作用。顺序模型只能在具有线性拓扑的网络中使用。

#### 创建顺序模型

让我们创建一个三层的顺序模型。完成所有导入后，我们开始创建图层。

T2T4

```py
model = keras.Sequential(
    [
        layers.Dense(2, activation="relu"),
        layers.Dense(3, activation="relu"),
        layers.Dense(4),
    ]
)
```

T5

这就是我们创建三层模型的方法。这种情况下使用的激活函数是‘ReLu’，或者*整流线性激活单元。*传入密集的积分参数表示每层神经元的数量。

请注意， *add()* 方法也可以用于将图层添加到模型中。

## 蟒 3

```py
model = keras.Sequential()
model.add(layers.Dense(2, activation="relu"))
model.add(layers.Dense(3, activation="relu"))
model.add(layers.Dense(4))
```

### 参考

1.  [https://keras.io/guides/sequential_model/](https://keras.io/guides/sequential_model/)
2.  [https://machinelearning master . com/keras-functional-API-deep-learning/](https://machinelearningmastery.com/keras-functional-api-deep-learning/)