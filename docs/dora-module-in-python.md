# Python 中的 Dora 模块

> 原文:[https://www.geeksforgeeks.org/dora-module-in-python/](https://www.geeksforgeeks.org/dora-module-in-python/)

*Dora* 是一个旨在简化探索性数据分析的库，这是一个非常痛苦的部分。它自动化了消耗大部分时间的重复任务。

该库具有非常方便的数据清洗、可视化、特征提取和选择、可视化等功能。除此之外，它还用于通过数据分区和数据转换进行模型验证。

该库使用 *scikit-learn* 、*熊猫*和 *matplotlib* 。该库的目的是为前面提到的用于探索性数据分析的通用库添加附加功能。

**安装:**

```
pip install Dora

```

用法:

为了在数据集中实现它，请使用以下语法:

## 蟒蛇 3

```
from Dora import Dora
```

它可以用于:

*   读取数据和配置
*   清洁
*   特征选择和提取
*   形象化
*   模型验证
*   数据版本控制

下面是 Python 中数据集上 *Dora* 模块的最基本实现:

## 计算机编程语言

```
# Import required module
from Dora import Dora

# Create object
dora = Dora()

# Add dataset path as argument 
dora.configure(output = 'A', data = 'data.csv') 

# Display dataset
dora.data
```

**输出:**

![](img/8cac1c2f0399b450bc9181d117c207f0.png)