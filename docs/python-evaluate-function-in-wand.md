# Python–在魔杖中评估()函数

> 原文:[https://www . geesforgeks . org/python-evaluate-function-in-wand/](https://www.geeksforgeeks.org/python-evaluate-function-in-wand/)

在 **evaluate()** 函数中，可以通过应用算术、关系或逻辑表达式来操作像素通道。

> **语法:**
> 
> ```
> wand.image.evaluate(operator, value, channel)
> ```
> 
> **参数:**
> 
> <figure class="table">
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 操作员 | 基绳 | 要计算的操作类型。 |
> | 价值 | 数字。真实的 | 用运算符
> 计算的数字 |
> | 频道 | 基绳 | 对其应用操作的可选通道。
>  |
> 
> </figure>

以下是魔杖中的评估操作列表:

<figure class="table">

| 评估 _ 操作 | 描述 |
| --- | --- |
| '未定义' | 它是默认的 EVALUATE_OPS。 |
| 腹肌 | 创建一个抽象评估。 |
| “添加” | 添加评估。 |
| ' addmodulus ' | 添加模数评估。 |
| '和' | 和评估。 |
| 余弦 | 从余弦函数计算。 |
| ' gaussiannoise ' | 添加高斯噪声评估 |
| '脉冲噪声' | 添加脉冲噪声评估 |
| 拉普拉斯算子 | 添加拉普拉斯噪声评估 |
| "左移" | 按位左移位 |
| 马克斯 | 最大评估 |
| 意思是 | 添加了均值评估。 |
| '中位数' | 添加了中值评估。 |
| '乘法加权' | 添加乘法噪声评估 |
| “乘法” | 多重图像评估 |
| 或者 | 或评估 |
| “poissonnoise” | 添加泊松噪声评估 |
| “力量” | 添加功耗评估 |
| 右移 | 按位右移 |
| '设置' | 添加集合评估 |
| 正弦曲线 | 添加正弦函数评估 |
| “阈值” | 添加具有特定阈值点的阈值评估。 |
| ' thresholdblack ' | 阈值为黑色时添加评估。 |
| “阈值白色” | 阈值为白色时添加评估。 |
| ' uniformnoise ' | 添加均匀噪声评估 |

</figure>

**来源图片:**

![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**代码示例 1:**

## 蟒蛇 3

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.evaluate(operator ='rightshift', value = 1, channel ='blue')
    img.save(filename ="kl-enhanced.jpeg")
```

**输出图像:**

![](img/66f14398c5e47a72e7afe7940884c22f.png)

**代码示例 2:**

## 蟒蛇 3

```
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    img.evaluate(operator ='leftshift', value = 1, channel ='red')
    img.save(filename ="kl-enhanced2.jpeg")
```

**输出图像:**

![](img/66648003f638c7aae885ae6fdc8bba6e.png)