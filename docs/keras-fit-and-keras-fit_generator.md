# keras.fit()和 keras.fit_generator()

> 原文:[https://www . geeksforgeeks . org/keras-fit-and-keras-fit _ generator/](https://www.geeksforgeeks.org/keras-fit-and-keras-fit_generator/)

**Python 中的 keras.fit()和 keras.fit_generator()** 是两个独立的深度学习库，可以用来训练我们的机器学习和深度学习模型。这两个函数可以做同样的任务，但是什么时候使用哪个函数是主要问题。

**硬合（）**

**语法:**

```py
fit(object, x = NULL, y = NULL, batch_size = NULL, epochs = 10,
  verbose = getOption("keras.fit_verbose", default = 1),
  callbacks = NULL, view_metrics = getOption("keras.view_metrics",
  default = "auto"), validation_split = 0, validation_data = NULL,
  shuffle = TRUE, class_weight = NULL, sample_weight = NULL,
  initial_epoch = 0, steps_per_epoch = NULL, validation_steps = NULL,
  ...)
```

**理解几个重要论点:**

```py

-> object : the model to train.      
-> X : our training data. Can be Vector, array or matrix      
-> Y : our training labels. Can be Vector, array or matrix       
-> Batch_size : it can take any integer value or NULL and by default, it will
be set to 32\. It specifies no. of samples per gradient.      
-> Epochs : an integer and number of epochs we want to train our model for.      
-> Verbose : specifies verbosity mode(0 = silent, 1= progress bar, 2 = one
line per epoch).      
-> Shuffle : whether we want to shuffle our training data before each epoch.      
-> steps_per_epoch : it specifies the total number of steps taken before
one epoch has finished and started the next epoch. By default it values is set to NULL.

```

**如何使用 Keras fit:**

```py
model.fit(Xtrain, Ytrain, batch_size = 32, epochs = 100)
```

这里我们首先输入训练数据(Xtrain)和训练标签(Ytrain)。然后，我们使用 Keras 允许我们的模型在 32 的批量上训练 100 个时期。

当我们呼唤**的时候。fit()** 函数它做出假设:

*   整个训练集可以装入计算机的随机存取存储器。
*   呼叫模型。第二次 fit 方法不会重新初始化我们已经训练好的权重，这意味着如果我们愿意，我们实际上可以连续调用 fit，然后正确管理它。
*   没有必要使用 Keras 生成器(即没有数据论证)
*   原始数据本身用于训练我们的网络，我们的原始数据只能存储在内存中。

 **The keras . fit _ generator():**

**语法:**

```py
fit_generator(object, generator, steps_per_epoch, epochs = 1,
  verbose = getOption("keras.fit_verbose", default = 1),
  callbacks = NULL, view_metrics = getOption("keras.view_metrics",
  default = "auto"), validation_data = NULL, validation_steps = NULL,
  class_weight = NULL, max_queue_size = 10, workers = 1,
  initial_epoch = 0)
```

**理解几个重要论点:**

```py

-> object : the Keras Object model.
-> generator : a generator whose output must be a list of the form:
                      - (inputs, targets)    
                      - (input, targets, sample_weights)
a single output of the generator makes a single batch and hence all arrays in the list 
must be having the length equal to the size of the batch. The generator is expected 
to loop over its data infinite no. of times, it should never return or exit.
-> steps_per_epoch : it specifies the total number of steps taken from the generator
 as soon as one epoch is finished and next epoch has started. We can calculate the value
of steps_per_epoch as the total number of samples in your dataset divided by the batch size.
-> Epochs : an integer and number of epochs we want to train our model for.
-> Verbose : specifies verbosity mode(0 = silent, 1= progress bar, 2 = one line per epoch).
-> callbacks : a list of callback functions applied during the training of our model.
-> validation_data can be either:
                      - an inputs and targets list
                      - a generator
                      - an inputs, targets, and sample_weights list which can be used to evaluate
                        the loss and metrics for any model after any epoch has ended.
-> validation_steps :only if the validation_data is a generator then only this argument
can be used. It specifies the total number of steps taken from the generator before it is 
stopped at every epoch and its value is calculated as the total number of validation data points
in your dataset divided by the validation batch size.

```

**如何使用 Keras fit_generator:**

```py
# performing data argumentation by training image generator
dataAugmentaion = ImageDataGenerator(rotation_range = 30, zoom_range = 0.20, 
fill_mode = "nearest", shear_range = 0.20, horizontal_flip = True, 
width_shift_range = 0.1, height_shift_range = 0.1)

# training the model
model.fit_generator(dataAugmentaion.flow(trainX, trainY, batch_size = 32),
 validation_data = (testX, testY), steps_per_epoch = len(trainX) // 32,
 epochs = 10)

```

在这里，我们为 10 个时代训练我们的网络，默认批量为 32。

对于较小且不太复杂的数据集，建议使用 keras.fit 函数，而在处理真实数据集时，这并不那么简单，因为真实数据集的大小很大，而且更难放入计算机内存。
处理这些数据集更具挑战性，处理这些数据集的一个重要步骤是进行数据扩充，以避免模型的过度拟合，并提高我们的模型的泛化能力。

**数据增广**是从现有的训练数据集人工创建一个新的数据集进行训练的方法，以可用的数据量提高深度学习神经网络的性能。这是一种正则化形式，使我们的模型比以前更好地推广。
这里我们使用了一个 Keras **ImageDataGenerator** 对象来应用数据增强，以随机平移、调整大小、旋转等图像。我们的每一批新数据都是根据提供给 **ImageDataGenerator** 的参数随机调整的。

**当我们叫**的时候。fit_generator()** 函数它做出假设:**

*   Keras 首先调用生成器函数
*   生成器函数(dataAugmentaion)为我们的。fit_generator()函数。
*   我们的**。fit_generator()** 函数首先接受一批数据集，然后对其进行反向传播，然后更新我们模型中的权重。
*   对于指定的纪元数量(在我们的例子中为 10 个)，重复该过程。

**总结:**
那么，我们已经学习了 Keras.fit 和用于训练深度学习神经网络的 Keras.fit_generator 函数的区别
**。当整个训练数据集可以放入内存并且没有应用数据扩充时，使用 fit** 。
**。fit_generator** 在我们有一个巨大的数据集要放入内存或者需要应用数据扩充时使用。