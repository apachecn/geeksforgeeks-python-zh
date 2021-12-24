# 使用 Python 通过皮褶测量计算体脂百分比

> 原文:[https://www . geeksforgeeks . org/calc te-体脂百分比-带皮褶-测量-使用-python/](https://www.geeksforgeeks.org/calulate-bodyfat-percentage-with-skinfold-measurements-using-python/)

健身对每个人都很重要。所有年龄的儿童和成人都需要有规律的体育活动。体育活动促进身体健康，你可以在任何年龄都保持活跃。让我们编写 python 脚本来帮助他们计算体脂百分比。体脂百分比可以通过皮褶测量(卡尺)来计算。**测径器**是一种可以测量三头肌、二头肌、髂上肌、大腿皮肤褶皱的装置，并将这些测量值代入公式。

我们将使用**健身工具**模块来计算体脂百分比。在开始之前，我们需要安装**健身工具**模块:

### 装置

这个模块不是用 Python 内置的。要安装此软件，请在终端中键入以下命令。

```py
pip install fitness-tools
```

**方法 1:**

考虑一名 25 岁女性，其皮褶测量值以毫米为单位为:

```py
triceps = 5
biceps = 7
thigh = 8
suprailliac = 12
```

**方法:**

*   Import module
*   Pass the following parameters to [T0】 durinwomersley
*   用身体密度()
*   Get body fat with siri ()

**下面是实现:**

## 蟒 3

```py
from fitness_tools.composition.bodyfat import DurninWomersley

data = DurninWomersley(25, 'female', (5, 7, 8, 12))
data.body_density()
```

**输出:**

```py
1.0519807465544626
```

**获取体内脂肪**

## 蟒 3

```py
# pass the body density value to a
# bodyfat equation inherited from
# GenericCalculator
data.siri(data.body_density())
```