# Python–双分裂字符串到矩阵

> 原文:[https://www . geesforgeks . org/python-双拆分-字符串到矩阵/](https://www.geeksforgeeks.org/python-double-split-string-to-matrix/)

给定一个字符串，执行双拆分，第一个用于行，第二个用于单个元素，以便给定的字符串可以转换为矩阵。

**示例:**

> **输入** : test_str = 'Gfg，best*for，all*geeks，and，CS '，row _ splt =“*”，ele _ splt =“
> ”T3】输出 : [['Gfg '，' best']，['for '，' all']，['geeks '，' and '，' CS ']
> **解释**:字符串按行拆分，元素按各自的 delims 拆分。
> 
> **输入** : test_str = 'Gfg！最适合！所有极客！还有！' CS '，row_splt = "* "，ele_splt = "！"
> **输出** : [['Gfg '，' best']，['for '，' all']，['geeks '，' and '，' CS']]
> **解释**:字符串按行拆分，元素按各自的 delims 拆分。

**方法#1:使用 split() +循环**

在这种情况下，首先使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 构造矩阵的行，然后嵌套 split()以获得单个元素之间的分离。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Double Split String to Matrix
# Using split() + loop

# initializing string
test_str = 'Gfg,best#for,all#geeks,and,CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing row split char 
row_splt = "#"

# initializing element split char 
ele_splt = ","

# split for rows
temp = test_str.split(row_splt)
res = []

for ele in temp:

    # split for elements
    res.append(ele.split(ele_splt))

# printing result 
print("String after Matrix conversion : " + str(res)) 
```

**输出:**

> 原字符串为:Gfg，best#for，all#geeks，and，CS
> 矩阵转换后的字符串:[['Gfg '，' best']，['for '，' all']，['geeks '，' and '，' CS']]

**方法 2:使用列表理解+拆分()**

这是执行这项任务的另一种方式。在这种情况下，我们使用类似的过程，但单线解决问题。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Double Split String to Matrix
# Using list comprehension + split()

# initializing string
test_str = 'Gfg,best#for,all#geeks,and,CS'

# printing original string
print("The original string is : " + str(test_str))

# initializing row split char 
row_splt = "#"

# initializing element split char 
ele_splt = ","

# split for rows
temp = test_str.split(row_splt)

# using list comprehension as shorthand
res = [ele.split(ele_splt) for ele in temp]

# printing result 
print("String after Matrix conversion : " + str(res))
```

**输出:**

> 原字符串为:Gfg，best#for，all#geeks，and，CS
> 矩阵转换后的字符串:[['Gfg '，' best']，['for '，' all']，['geeks '，' and '，' CS']]