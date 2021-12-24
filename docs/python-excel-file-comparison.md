# Python | Excel 文件对比

> 原文:[https://www.geeksforgeeks.org/python-excel-file-comparison/](https://www.geeksforgeeks.org/python-excel-file-comparison/)

给定两个 Excel 文件，我们希望在对值进行排序后逐行比较每列的值，并打印更改的列名和行号以及值的更改。

```
Input : 
Two Excel files

Output :
Column name : 'location' and Row Number : 0
Column name : 'location' and Row Number : 3
Column name : 'date' and Row Number     : 1

```

**代码:比较两个 excel 文件的 Python 代码**

```
# Write Python3 code here
# importing Pandas

import pandas as pd

#Reading two Excel Sheets

sheet1 = pd.read_excel(r'Book1.xlsx')
sheet2 = pd.read_excel(r'Book2.xlsx')

# Iterating the Columns Names of both Sheets
for i,j in zip(sheet1,sheet2):

    # Creating empty lists to append the columns values    
    a,b =[],[]

    # Iterating the columns values
    for m, n in zip(sheet1[i],sheet2[j]):

        # Appending values in lists
        a.append(m)
        b.append(n)

    # Sorting the lists
    a.sort()
    b.sort()

    # Iterating the list's values and comparing them
    for m, n in zip(range(len(a)), range(len(b))):
        if a[m] != b[n]:
            print('Column name : \'{}\' and Row Number : {}'.format(i,m))
```