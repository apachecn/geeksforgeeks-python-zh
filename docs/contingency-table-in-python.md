# Python 中的列联表

> 原文:[https://www.geeksforgeeks.org/contingency-table-in-python/](https://www.geeksforgeeks.org/contingency-table-in-python/)

在单变量数据分析的情况下，像均值、中值、标准差和方差这样的估计非常有用。但是在双变量分析(比较两个变量)的情况下，相关性开始发挥作用。

**列联表**是探索两个甚至更多变量的技术之一。它基本上是两个或多个分类变量之间的计数。

要获取贷款数据，请点击这里的。

**加载库**

```py
import numpy as np
import pandas as pd
import matplotlib as plt
```

**加载数据**

```py
data = pd.read_csv("loan_status.csv")

print (data.head(10))
```

**输出:**
![](img/ef5525f70a628319ad7c55dd93e16251.png)

**描述数据**

```py
data.describe()
```

**输出:**
![](img/12c357dfe6504c281fa19183b178e0f8.png)

**数据信息**

```py
data.info()
```

**输出:**
![](img/f24a2645f563808dc54f4c62e5aa527c.png)

**数据类型**

```py
# data types of feature/attributes 
# in the data
data.dtypes
```

**输出:**
![](img/b105f928ee25f1c146219fe2553fc6ea.png)

**代码#1:** 列联表，显示等级和贷款状态之间的相关性。

```py
data_crosstab = pd.crosstab(data['grade'],
                            data['loan_status'], 
                               margins = False)
print(data_crosstab)
```

**输出:**
![](img/4ac87bae1a3b1c45cdbad8a29923ba1f.png)

**代码#2:** 列联表，显示目的和贷款状态之间的相关性。

```py
data_crosstab = pd.crosstab(data['purpose'], 
                            data['loan_status'],
                                margins = False)
print(data_crosstab)
```

**输出:**
![](img/3fcdb0691b176ae30c685cef12eca33b.png)

**代码#3:** 列联表，显示等级+目的与贷款状态之间的相关性。

```py
data_crosstab = pd.crosstab([data.grade, data.purpose], 
                             data.loan_status, margins = False)
print(data_crosstab)
```

**输出:**
![](img/4ab2ebf28af8fbf3ba7bf5a8a3fe6088.png)

所以在代码中，列联表给出了两个或更多变量之间明确的相关值。从而使理解数据以便进一步提取信息变得更加有用。
。