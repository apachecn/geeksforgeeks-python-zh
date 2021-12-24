# 喀拉斯的数据集

> 原文:[https://www.geeksforgeeks.org/datasets-in-keras/](https://www.geeksforgeeks.org/datasets-in-keras/)

Keras 是一个 python 库，广泛用于训练深度学习模型。深度学习中的一个常见问题是为开发模型找到合适的数据集。在本文中，我们将看到已经包含在`keras.datasets`模块中的流行数据集列表。

**MNIST(10 位数字的分类):**
该数据集用于手写数字的分类。它包含训练集中的 *60，000 张*图像和测试集中的 10，000 张图像。每张图片大小为 *28×28* 。

```
from keras.datasets import mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
```

**返回:**

*   **x_train，x_test:** 具有形状(num_samples，28，28)的灰度图像数据的无符号整数(0-255)数组。
*   **y_train，y_test:** 带 shape (num_samples，)的无符号整数(0-255)数字标签(0-9 范围内的整数)数组。

* * *

**Fashion-MNIST(classification of 10 fashion categories):**

该数据集可用作 MNIST 的替代产品。它由 10 个时尚类别的 60，000 幅 28×28 灰度图像以及一组 10，000 幅图像组成。类别标签包括:

<figure class="table">

| 标签 | 描述 |
| Zero | t 恤/上衣 |
| one | 裤子 |
| Two | 套衫 |
| three | 连衣裙 |
| four | 外套 |
| five | 凉鞋 |
| six | 衬衫 |
| seven | 运动鞋 |
| eight | 袋 |
| nine | 踝靴 |

</figure>

```
from keras.datasets import fashion_mnist
(x_train, y_train), (x_test, y_test) = fashion_mnist.load_data()
```

**返回**:

*   **x_train，x_test:** 具有形状(num_samples，28，28)的灰度图像数据的无符号整数(0-255)数组。
*   **y_train，y_test:** 带 shape (num_samples，)的无符号整数(0-255)数字标签(0-9 范围内的整数)数组。

* * *

**CIFAR10 (classification of 10 image labels):**

该数据集包含广泛用于图像分类任务的 10 种不同类别的图像。它由 50，000 张 32×32 的彩色训练图像，10 个类别和 10，000 张测试图像组成。数据集分为五个训练批次，每个批次有 10000 幅图像。测试批次包含每一类中的 1000 张随机选择的图像。训练批次包含随机顺序的剩余图像，但是一些训练批次可能包含来自一个类别的图像多于另一个类别的图像。在它们之间，训练批次恰好包含每个班级的 5000 幅图像。这些类是完全互斥的。汽车和卡车之间没有重叠。类别标签包括:

<figure class="table">

| 标签 | 描述 |
| Zero | 飞机 |
| one | 汽车 |
| Two | 鸟 |
| three | 猫 |
| four | 鹿 |
| five | 狗 |
| six | 青蛙 |
| seven | 马 |
| eight | 船 |
| nine | 卡车 |

</figure>

```
from keras.datasets import cifar10
(x_train, y_train), (x_test, y_test) = cifar10.load_data()
```

**返回:**

*   **x_train，x_test:** 一个无符号整数(0-255)数组的 RGB 图像数据，其形状(num_samples，3，32，32)或(num_samples，32，32，3)分别基于 channels _ first 或 channels _ last 的 image_data_format 后端设置。形状中的值“3”指的是 3 个 RGB 通道。
*   **y_train，y_test:** 带形状(num_samples，1)的类别标签(0-9 范围内的整数)的无符号整数(0-255)数组。

* * *

**CIFAR100 (classification of 100 image labels):**

该数据集包含广泛用于图像分类任务的 10 种不同类别的图像。它由 50，000 幅 32×32 的彩色训练图像和 10，000 幅测试图像组成，标记了 10 个类别。这个数据集就像 CIFAR-10 一样，只是它有 100 个类，每个类包含 600 个图像。每堂课有 500 个训练图像和 100 个测试图像。CIFAR-100 中的 100 个类被分为 20 个超类。每个图像都带有一个“精细”标签(它所属的类)和一个“粗糙”标签(它所属的超类)。

```
from keras.datasets import cifar100
(x_train, y_train), (x_test, y_test) = cifar100.load_data(label_mode='fine')
```

**返回:**

*   **x_train，x_test:** 一个无符号整数(0-255)数组的 RGB 图像数据，其形状(num_samples，3，32，32)或(num_samples，32，32，3)分别基于 channels _ first 或 channels _ last 的 image_data_format 后端设置。形状中的值“3”指的是 3 个 RGB 通道。
*   **y_train，y_test:** 带形状(num_samples，1)的类别标签(0-99 范围内的整数)的无符号整数(0-255)数组。

**论据:**

*   **label_mode** :“细”或“粗”。

* * *

**Boston Housing Prices(Regression):**

该数据集取自卡内基梅隆大学的 StatLib 图书馆。这个数据集包含 13 个属性的房子在不同的位置在波士顿郊区在 20 世纪 70 年代末。目标是某一地点房屋的中值(单位为 k$)。训练集包含 404 个不同家庭的数据，而测试集包含 102 个不同家庭的数据

```
from keras.datasets import boston_housing
(x_train, y_train), (x_test, y_test) = boston_housing.load_data()
```

**返回:**

*   **x_train，x_test:** 具有形状的不同属性的数值的 numpy 数组(num_samples，13)。
*   **y_train，y_test:** 不同属性的数值与形状的 numpy 数组(num_samples，)。

**论据:**

*   **种子**:随机种子，用于在计算测试分割之前对数据进行洗牌。
*   **test_split** :作为测试集保留的数据的一部分。

* * *

**IMDB Movie Reviews (Sentiment Classification) :**

该数据集用于评论的二元分类，即正面或负面。它由来自 IMDB 的 25，000 部电影评论组成，按照情绪(正面/负面)进行标注。这些评论已经过预处理，每个评论都被编码为一系列单词索引(整数)。这些单词按照它们在数据集中出现的总频率进行索引。例如，整数“5”编码数据中第五个最频繁的单词。这允许快速过滤操作，例如仅考虑前 5000 个单词作为模型词汇等..

```
from keras.datasets import imdb
(x_train, y_train), (x_test, y_test) = imdb.load_data()
```

**返回:**

*   **x_train，x_test** :序列列表，为索引(整数)列表。如果 num_words 参数是特定的，则最大可能的索引值是 num_words-1。如果指定了 maxlen 参数，最大可能的序列长度是 maxlen。
*   **y_train，y_test** :整数标签列表(1 表示正，0 表示负)。

**论据:**

*   **num_words(int 或 None)** :考虑次数最多的词。任何频率较低的单词都会在序列数据中显示为“oov_char”值。
*   **skip_top(int)** :最常忽略的单词(它们将在序列数据中显示为 oov_char 值)。
*   **maxlen(int)** :最大序列长度。任何较长的序列都将被截断。
*   **seed(int)** :用于可再现数据洗牌的 seed。
*   **start_char(int)** :一个序列的开始会用这个字符来标记。设置为 1，因为 0 通常是填充字符。
*   **oov_char(int)** :因 num _ words 或 skip_top 限制而被删减的单词将被该字符替换。
*   **index_from(int)** :用这个指数及更高的指数来索引实际单词。

* * *

**Reuters newswire topics classification:**

该数据集用于多类文本分类。它由来自路透社的 11，228 条新闻线组成，标注了超过 46 个主题。就像 IMDB 数据集一样，每条线都被编码为一系列单词索引(相同的约定)。

```
from keras.datasets import reuters
(x_train, y_train), (x_test, y_test) = reuters.load_data()
```

**返回:**

*   **x_train，x_test** :序列列表，为索引(整数)列表。如果 num_words 参数是特定的，则最大可能的索引值是 num_words-1。如果指定了 maxlen 参数，最大可能的序列长度是 maxlen。
*   **y_train，y_test** :整数标签列表(1 表示正，0 表示负)。

**论据:**

*   **num_words(int 或 None)** :考虑次数最多的词。任何频率较低的单词都会在序列数据中显示为“oov_char”值。
*   **skip_top(int)** :最常忽略的单词(它们将在序列数据中显示为 oov_char 值)。
*   **maxlen(int)** :最大序列长度。任何较长的序列都将被截断。
*   **seed(int)** :用于可再现数据洗牌的 seed。
*   **start_char(int)** :一个序列的开始会用这个字符来标记。设置为 1，因为 0 通常是填充字符。
*   **oov_char(int)** :因 num _ words 或 skip_top 限制而被删减的单词将被该字符替换。
*   **index_from(int)** :用这个指数及更高的指数来索引实际单词。