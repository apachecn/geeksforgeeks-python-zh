# 作为给定有理

的缩减分数的 Python 中的 _integer_ratio()

> 原文:[https://www . geesforgeks . org/as _ integer _ ratio-python-reduced-fraction-given-rational/](https://www.geeksforgeeks.org/as_integer_ratio-python-reduced-fraction-given-rational/)

给定一个有理数 d，打印给出 d 的简化分数
**例:**

```
Input : d = 2.5 
Output : 5/2
Explanation: 5/2 gives 2.5 which is the reduced form
             of any fraction that gives 2.5 

Input : d = 1.5 
Output : 3/2 
```

**as_integer_ratio()函数 Python:**
返回一对整数，它们的比值正好等于原始浮点数，并且有一个正分母。

> 语法:
> float。as_integer_ratio()
> 返回值:
> 元组(一对整数)
> 错误:
> 在不定式上引发 OverflowError，在 NaNs 上引发 ValueError。

在 Python 中，我们有一个内置函数 **as_integer_ratio()** ，它打印任何给定有理数 d 的缩减分数形式。我们需要将它存储在任何变量中，然后打印存储分数的第 0 个索引和第 1 个索引。

## 蟒蛇 3

```
# function to print the fraction of
# a given rational number
def reducedfraction(d):

    # function that converts a rational number
    # to the reduced fraction
    b = d.as_integer_ratio()

    # reduced the list that contains the fraction
    return b

# driver code
b = reducedfraction(2.5)
print (b[0], "/", b[1])
```

**输出:**

```
5 / 2 
```