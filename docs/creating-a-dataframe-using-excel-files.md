# 使用 Excel 文件创建数据框

> 原文:[https://www . geesforgeks . org/creating-a-data frame-use-excel-files/](https://www.geeksforgeeks.org/creating-a-dataframe-using-excel-files/)

让我们看看如何使用**熊猫**将 excel 文件读取到熊猫数据框对象。
**代码#1 :** 用熊猫的 read_excel()方法读取 excel 文件。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# read by default 1st sheet of an excel file
dataframe1 = pd.read_excel('SampleWork.xlsx')

print(dataframe1)
```

**输出:**

```py
        Name  Age    Stream  Percentage
0      Ankit   18      Math          95
1      Rahul   19   Science          90
2    Shaurya   20  Commerce          85
3  Aishwarya   18      Math          80
4   Priyanka   19   Science          75
```

**代码#2 :** 使用 read_excel()方法的“工作表名称”读取特定工作表。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# read 2nd sheet of an excel file
dataframe2 = pd.read_excel('SampleWork.xlsx', sheet_name = 1)

print(dataframe2)
```

**输出:**

```py
       Name  Age    Stream  Percentage
0     Priya   18      Math          95
1  shivangi   19   Science          90
2      Jeet   20  Commerce          85
3    Ananya   18      Math          80
4   Swapnil   19   Science          75
```

**代码#3 :** 使用 read_excel()方法的“usecols”参数读取特定列。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

require_cols = [0, 3]

# only read specific columns from an excel file
required_df = pd.read_excel('SampleWork.xlsx', usecols = require_cols)

print(required_df)
```

**输出:**

```py
        Name  Percentage
0      Ankit          95
1      Rahul          90
2    Shaurya          85
3  Aishwarya          80
4   Priyanka          75
```

**代码#4 :** 使用 read_excel()方法的“na_values”参数处理丢失的数据。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# Handling missing values of 3rd sheet of an excel file.
dataframe = pd.read_excel('SampleWork.xlsx', na_values = "Missing",
                                                    sheet_name = 2)

print(dataframe)
```

**输出:**

```py
       Name  Age   Stream  Percentage
0     Priya   18     Math          95
1  shivangi   19  Science          90
2      Jeet   20      NaN          85
3    Ananya   18     Math          80
4   Swapnil   19  Science          75
```

**代码#5 :** 使用 read_excel()方法的‘Skip prows’参数读取 Excel 文件时跳过起始行。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# read 2nd sheet of an excel file after
# skipping starting two rows
df = pd.read_excel('SampleWork.xlsx', sheet_name = 1, skiprows = 2)

print(df)
```

**输出:**

```py
  shivangi  19   Science  90
0     Jeet  20  Commerce  85
1   Ananya  18      Math  80
2  Swapnil  19   Science  75
```

**代码#6 :** 使用 read_excel()方法的“header”参数，将标题设置为任意行，并从该行开始读取。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# setting the 3rd row as header.
df = pd.read_excel('SampleWork.xlsx', sheet_name = 1, header = 2)

print(df)
```

**输出:**

```py
  shivangi  19   Science  90
0     Jeet  20  Commerce  85
1   Ananya  18      Math  80
2  Swapnil  19   Science  75
```

**代码#7 :** 使用 read_excel()方法的“工作表名称”参数读取多个 Excel 工作表。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# read both 1st and 2nd sheet.
df = pd.read_excel('SampleWork.xlsx', na_values = "Missing",
                                        sheet_name =[0, 1])

print(df)
```

**输出:**

```py
OrderedDict([(0,         Name  Age    Stream  Percentage
0      Ankit   18      Math          95
1      Rahul   19   Science          90
2    Shaurya   20  Commerce          85
3  Aishwarya   18      Math          80
4   Priyanka   19   Science          75),

(1,        Name  Age    Stream  Percentage
0     Priya   18      Math          95
1  shivangi   19   Science          90
2      Jeet   20  Commerce          85
3    Ananya   18      Math          80
4   Swapnil   19   Science          75)])
```

**代码#8 :** 使用 read_excel()方法的“sheet_name”参数一起读取 excel 文件的所有 Sheets。

## 蟒蛇 3

```py
# import pandas lib as pd
import pandas as pd

# read all sheets together.
all_sheets_df = pd.read_excel('SampleWork.xlsx', na_values = "Missing",
                                                     sheet_name = None)

print(all_sheets_df)
```

**输出:**

```py
OrderedDict([('Sheet1',         Name  Age    Stream  Percentage
0      Ankit   18      Math          95
1      Rahul   19   Science          90
2    Shaurya   20  Commerce          85
3  Aishwarya   18      Math          80
4   Priyanka   19   Science          75),

('Sheet2',        Name  Age    Stream  Percentage
0     Priya   18      Math          95
1  shivangi   19   Science          90
2      Jeet   20  Commerce          85
3    Ananya   18      Math          80
4   Swapnil   19   Science          75), 

('Sheet3',        Name  Age   Stream  Percentage
0     Priya   18     Math          95
1  shivangi   19  Science          90
2      Jeet   20      NaN          85
3    Ananya   18     Math          80
4   Swapnil   19  Science          75)])
```