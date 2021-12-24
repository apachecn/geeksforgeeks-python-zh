# 如何用 Python 将多个 excel 文件合并成单个文件？

> 原文:[https://www . geesforgeks . org/如何用 python 将多个 excel 文件合并成一个文件/](https://www.geeksforgeeks.org/how-to-merge-multiple-excel-files-into-a-single-files-with-python/)

通常，我们使用的是 Excel 文件，我们肯定遇到过需要将多个 Excel 文件合并成一个的情况。传统的方法一直是在 excel 中使用 VBA 代码，这是一个多步骤的过程，不太容易理解。另一种方法是手动将长的 Excel 文件复制到一个文件中，这不仅耗时、麻烦，而且容易出错。

使用**熊猫模块**在 **Python** 中只需几行代码就可以轻松快速地完成这项任务。首先，我们需要用 pip 安装模块。所以让我们把这个装置移开。

在终端中使用以下命令:

```
pip install pandas
```

**方法 1:使用** [**数据框追加()**](https://www.geeksforgeeks.org/python-pandas-dataframe-append/#:~:text=append()%20function%20is%20used,are%20populated%20with%20NaN%20value.&text=ignore_index%20%3A%20If%20True%2C%20do%20not%20use%20the%20index%20labels.)

pandas**data frame . append()**函数用于将其他数据帧的行追加到给定数据帧的末尾，返回一个新的数据帧对象。不在原始数据框中的列将作为新列添加，新单元格将填充 NaN 值。

> **语法:** DataFrame.append(other，ignore_index=False，verify_integrity=False，sort=None)
> 
> **参数:**
> 
> *   **Others:** Dataframe or Series/dict class objects, or a list of these.
> *   [T0】 ignore _ index: 【T1] If True, do not use the tab. The default value is False.
> *   **Verify _ Integrity:** If true, a value error will be raised when creating duplicate indexes. The default value is False.
> *   **Sorting:** If it is not aligned with other columns, sort the columns. The default value is False.
> 
> **返回**:附加数据框

**示例:**

**Excel Used:**[food sales 1-1](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210525133803/FoodSales1-1.xlsx)、[food sales 2-1](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210525133804/FoodSales2-1.xlsx)

## python 3

```
# importing the required modules
import glob
import pandas as pd

# specifying the path to csv files
path = "C:/downloads"

# csv files in the path
file_list = glob.glob(path + "/*.xlsx")

# list of excel files we want to merge.
# pd.read_excel(file_path) reads the excel
# data into pandas dataframe.
excl_list = []

for file in excl_list:
    excl_list.append(pd.read_excel(file))

# create a new dataframe to store the 
# merged excel file.
excl_merged = pd.DataFrame()

for excl_file in excl_list:

    # appends the data into the excl_merged 
    # dataframe.
    excl_merged = excl_merged.append(
      excl_file, ignore_index=True)

# exports the dataframe into excel file with
# specified name.
excl_merged.to_excel('total_food_sales.xlsx', index=False)
```