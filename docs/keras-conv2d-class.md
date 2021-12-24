# Hard.Conv2D Class

> 原文:[https://www.geeksforgeeks.org/keras-conv2d-class/](https://www.geeksforgeeks.org/keras-conv2d-class/)

**Keras Conv2D** 是一个 2D 卷积层，该层创建了一个卷积核，该核与层输入相结合，有助于产生输出张量。

**核:**在图像处理中，核是一个卷积矩阵或掩模，通过在核和图像之间进行卷积，可以用于模糊、锐化、压花、边缘检测等。

**Keras Conv2D 类构造函数有以下参数:**

```py
keras.layers.Conv2D(filters, kernel_size, strides=(1, 1),
  padding='valid', data_format=None, dilation_rate=(1, 1),
  activation=None, use_bias=True, kernel_initializer='glorot_uniform',
  bias_initializer='zeros', kernel_regularizer=None,
  bias_regularizer=None, activity_regularizer=None,
  kernel_constraint=None, bias_constraint=None)
```

**现在让我们逐个检查这些参数:**
**过滤器**

*   强制 Conv2D 参数是卷积层将学习的滤波器数量。
*   它是一个整数值，也决定了卷积中输出滤波器的数量。

    ```py
    model.add(Conv2D(32, (3, 3), padding="same", activation="relu"))
    model.add(MaxPooling2D(pool_size=(2, 2)))
    ```

*   在这里，我们总共学习了 32 个过滤器，然后我们使用最大池来减少输出体积的空间维度。
*   至于为过滤器数量选择合适的值，建议始终使用 2 的幂作为值。

**内核 _ 大小**

*   这个参数决定了内核的尺寸。常用维度包括 1×1、3×3、5×5、7×7，可以作为(1，1)、(3，3)、(5，5)或(7，7)元组传递。
*   它是一个整数或 2 个整数的元组/列表，指定 2D 卷积窗口的高度和宽度。
*   此参数必须是奇数。

```py
model.add(Conv2D(32, (7, 7), activation="relu"))
```

**大步**

*   该参数是一个整数或 2 个整数的元组/列表，指定卷积的“步长”以及输入体积的高度和宽度。
*   它的默认值始终设置为(1，1)，这意味着给定的 Conv2D 滤镜应用于输入体积的当前位置，给定的滤镜向右移动 1 个像素，滤镜再次应用于输入体积，并且一直执行到我们移动滤镜的体积的最右边界。

```py
model.add(Conv2D(128, (3, 3), strides=(1, 1), activation="relu"))
model.add(Conv2D(128, (3, 3), strides=(2, 2), activation="relu"))
```

**填充**

*   Keras Conv2D 类的填充参数可以采用两个值之一:“有效”或“相同”。
*   将该值设置为“有效”参数意味着输入体积不是零填充的，并且允许通过卷积的自然应用来减少空间维度。

```py
model.add(Conv2D(32, (3, 3), padding="valid"))
```

相反，您可以通过将值设置为“相同”来保留体积的空间尺寸，以便输出体积大小与输入体积大小相匹配。

```py
model.add(Conv2D(32, (3, 3), padding="same"))
```

**数据 _ 格式**

*   Conv2D 类的该参数可以设置为“通道 _ 最后”或“通道 _ 第一”值。
*   到 Keras 的 TensorFlow 后端使用通道最后排序，而 Anano 后端使用通道第一排序。
*   通常我们不会像 Keras 那样触及这个值，因为大多数时候我们将使用 TensorFlow 后端来处理 Keras。
*   它默认为在您的 Keras 配置文件中位于~/的 image_data_format 值。keras/Keras.json。

**扩张 _ 速率**

*   Conv2D 类的膨胀率参数是一个二元整数，它控制膨胀卷积的膨胀率。
*   扩张卷积是应用于具有定义间隙的输入体积的基本卷积。
*   当使用更高分辨率的图像并且精细的细节对您很重要时，或者当您构建具有更少参数的网络时，您可以使用此参数。

**激活**

*   Conv2D 类的激活参数只是一个方便的参数，允许您提供一个字符串，该字符串指定执行卷积后要应用的激活函数的名称。

```py
model.add(Conv2D(32, (3, 3), activation="relu"))
```

运筹学

```py
model.add(Conv2D(32, (3, 3)))
model.add(Activation("relu"))
```

*   如果您没有指定任何内容，则不会应用激活，也不会对卷积神经网络的性能产生影响。

**使用 _bias**

*   Conv2D 类的该参数用于确定是否将偏置向量添加到卷积层。
*   默认情况下，其值设置为“真”。

**内核初始化器**

*   此参数控制初始化方法，该方法用于在实际训练模型之前初始化 Conv2D 类中的所有值。
*   它是内核权重矩阵的初始化器。

**bias_initializer**

*   而 bias_initializer 控制在训练开始之前如何初始化偏置向量。
*   它是偏差向量的初始值设定项。

**核正则化器、偏差正则化器和活性正则化器**

*   **核正则化**是应用于核权重矩阵的正则化函数。
*   **偏置正则化**是应用于偏置向量的正则化函数。
*   **activity _ regulator**是应用于图层输出(即激活)的 regulator 函数。
*   正则化是通过在给定的训练集上适当地拟合函数来减少误差并避免过度拟合的技术。
*   它控制应用于 Conv2D 图层的正则化方法的类型和数量。
*   在处理大型数据集和深度神经网络时，必须使用正则化。
*   使用正则化有助于我们减少过拟合的影响，并提高模型的泛化能力。
*   有两种类型的正则化:L1 正则化和 L2 正则化，这两种正则化都用于减少模型的过拟合。

```py
from keras.regularizers import l2
...
model.add(Conv2D(128, (3, 3), activation="relu"),
    kernel_regularizer=l2(0.0002))
```

*   您应用的正则化值是您需要为自己的数据集调整的超参数，其值通常在 0.0001 到 0.001 之间。
*   始终建议不要使用 bias _ regularizer，因为它对减少过拟合的影响非常小。
*   还建议将 activity _ regularizer 保留为默认值。

**内核 _ 约束和偏置 _ 约束**

*   核约束是应用于核矩阵的约束函数。
*   偏置约束是应用于偏置向量的约束函数。
*   约束是最优化问题的一个条件，解必须满足。
    约束有几种类型——主要是等式约束、不等式约束和整数约束。
*   这些参数允许您对 Conv2D 图层施加约束。
*   除非您有特定的理由对 Con2D 图层应用约束，否则这些参数通常不会被使用。

**下面是一个简单的代码示例，向您展示了 Conv2D 类的不同参数的工作方式:**

```py
# build the model
model = Sequential()
model.add(Conv2D(32, kernel_size =(5, 5), strides =(1, 1),
                 activation ='relu'))
model.add(MaxPooling2D(pool_size =(2, 2), strides =(2, 2)))
model.add(Conv2D(64, (5, 5), activation ='relu'))
model.add(MaxPooling2D(pool_size =(2, 2)))
model.add(Flatten())
model.add(Dense(1000, activation ='relu'))
model.add(Dense(num_classes, activation ='softmax'))

# training the model
model.compile(loss = keras.losses.categorical_crossentropy,
              optimizer = keras.optimizers.SGD(lr = 0.01),
              metrics =['accuracy'])

# fitting the model
model.fit(x_train, y_train,
          batch_size = batch_size,
          epochs = epochs,
          verbose = 1,
          validation_data =(x_test, y_test),
          callbacks =[history])

# evaluating and printing results
score = model.evaluate(x_test, y_test, verbose = 0)
print('Test loss:', score[0])
print('Test accuracy:', score[1])
```

**理解代码:**

*   当使用 **Sequential.model.add()** 方法添加 Conv2D 图层时，我们可以使用许多参数，这些参数我们之前已经在博客中读到过。
*   第一个参数告诉我们卷积运算中使用的滤波器数量。
*   然后第二个参数以像素为单位指定卷积滤波器的大小。滤镜大小可能由您使用的 CNN 架构决定–例如，VGGNet 仅使用(3，3)个滤镜。如果没有，使用 5×5 或 7×7 的滤波器学习更大的特征，然后快速缩小到 3×3。
*   第三个参数指定卷积滤波器应该如何沿着源图像的 x 轴和 y 轴步进。在大多数情况下，将跨距参数保留为默认值(1，1)是可以的。但是，您可以将其增加到(2，2)以减小输出音量。
*   第四个参数是激活参数，指定执行卷积后要应用的激活函数的名称。

**使用功能性应用编程接口的类似代码**

```py
#build the model
inputs = Input(shape = ())
conv1 = Conv2D(32, kernel_size = (5,5), strides = (1,1), activation = 'relu'))(inputs)
max1 = MaxPooling2D(pool_size=(2,2), strides=(2,2)))(conv1)
conv2 = Conv2D(64, (5,5), activation = 'relu'))(max1)
max2 = MaxPooling2D(pool_size=(2,2)))(conv2)
flat = Flatten()(max2)
den1 = Dense(100, activation = 'relu'))(flat)
out1 = Dense(num_classes, activation ='softmax'))(den1)

model = Model(inputs = inputs, output =out1 )

# training the model 
model.compile(loss = keras.losses.categorical_crossentropy,
              optimizer = keras.optimizers.SGD(lr = 0.01),
              metrics =['accuracy'])

# fitting the model 
model.fit(x_train, y_train,
          batch_size = batch_size,
          epochs = epochs,
          verbose = 1,
          validation_data =(x_test, y_test),
          callbacks =[history])

# evaluating and printing results 
score = model.evaluate(x_test, y_test, verbose = 0)
print('Test loss:', score[0])
print('Test accuracy:', score[1])
```

## 总结:

*   大多数时候，您将使用过滤器、内核大小、步长、填充。
*   如何正确使用 Keras Conv2D 类来创建我们自己的卷积神经网络，并确定我们是否需要利用 Keras Conv2D 类的特定参数。