# 如何修复:名称错误名称‘PD’未定义

> 原文:[https://www . geesforgeks . org/how-fix-name error-name-PD-is-undefined/](https://www.geeksforgeeks.org/how-to-fix-nameerror-name-pd-is-not-defined/)

在本文中，我们将讨论如何修复 Python 中没有定义的名称错误 pd。

当我们在没有别名的情况下导入 pandas 模块并在代码中使用 pd 时，出现了错误。

**示例:**描述错误的代码

## 蟒蛇 3

```py
# import pandas module
import pandas

# create dataframe
data = pd.DataFrame({'a': [1, 2], 'b': [3, 4]})

# display
data
```

**输出:**

> —————————————————————————
> 
> 名称错误追溯(最近一次调用最后一次)
> 
> <ipython-input-1-a37aacbaa7a7>中的<module>()</module></ipython-input-1-a37aacbaa7a7>
> 
> three
> 
> 4 #创建数据帧
> 
> —-> 5 数据=pd。DataFrame({'a':[1，2]，' b':[3，4]})
> 
> six
> 
> 7 #显示屏
> 
> 名称错误:未定义名称“pd”

这里 pd 是 pandas 模块的别名，所以我们可以用别名导入 pandas 模块，也可以不用别名导入 pandas，直接使用这个名字。

## 方法 1:通过在导入熊猫时使用别名

我们可以在导入时使用 alias 来解决错误

**语法**:

```py
import pandas as pd
```

**示例**:导入熊猫作为别名的程序

## 蟒蛇 3

```py
# import pandas module
import pandas as pd

# create dataframe
data = pd.DataFrame({'a': [1, 2], 'b': [3, 4]})

# display
data
```

**输出:**

```py
    a    b
0    1    3
1    2    4
```

## 方法二:直接用熊猫

我们可以直接使用熊猫模块在一个数据结构中使用。

**语法**:

```py
import pandas
```

**例:**直接用熊猫

## 蟒蛇 3

```py
# import pandas module
import pandas

# create dataframe
data = pandas.DataFrame({'a': [1, 2], 'b': [3, 4]})

# display
data
```

**输出:**

```py
    a    b
0    1    3
1    2    4
```