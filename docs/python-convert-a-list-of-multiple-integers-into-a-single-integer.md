# Python 程序将多个整数列表转换为单个整数

> 原文:[https://www . geesforgeks . org/python-convert-a-list-of-multiple-integer-a-single-integer/](https://www.geeksforgeeks.org/python-convert-a-list-of-multiple-integers-into-a-single-integer/)

给定一个整数列表，编写一个 Python 程序将给定的列表转换成一个整数。

**示例:**

```
Input : [1, 2, 3]
Output : 123

Input : [55, 32, 890]
Output : 5532890
```

有多种方法可以将给定列表转换为单个整数。让我们一个一个地看。

**方法#1 :** 简单方法
简单地迭代列表中的每个元素，并打印它们，中间没有空格。

```
# Python3 program to convert a list
# of integers into a single integer

# creating a list
lst = [12, 15, 17]

# iterating each element
for i in lst:
    print(i, end="")
```

**输出:**

```
121517
```

**进场#2 :** 使用 [`join()`](https://www.geeksforgeeks.org/join-function-python/)

使用 Python 的`join()`方法。首先将整数列表转换成字符串列表(因为`join()`只处理字符串)。然后，简单地使用`join()`方法加入他们。需要`O(n)`的时间复杂度。

```
# Python3 program to convert a list
# of integers into a single integer
def convert(list):

    # Converting integer list to string list
    s = [str(i) for i in list]

    # Join list items using join()
    res = int("".join(s))

    return(res)

# Driver code
list = [1, 2, 3]
print(convert(list))
```

**输出:**

```
123
```

**进场#3 :** 使用 [`map()`](https://www.geeksforgeeks.org/python-map-function/)

将多个整数列表转换为单个整数的另一种方法是使用 Python 的`map()`函数和 *str* 函数将整数列表转换为字符串列表。之后，在空字符串上连接它们，然后转换回整数。

```
# Python3 program to convert a list
# of integers into a single integer
def convert(list):

    # Converting integer list to string list
    # and joining the list using join()
    res = int("".join(map(str, list)))

    return res

# Driver code
list = [1, 2, 3]
print(convert(list))
```

**输出:**

```
123
```

**逼近#4 :** 乘以相应的 10 次方

一种更数学的方法，不需要将整数列表转换为字符串列表，就是将每个整数元素乘以其对应的 10 的幂，然后求和。需要`O(n)`的时间复杂度。

```
# Python3 program to convert a list
# of integers into a single integer
def convert(list):

    # multiply each integer element with its 
    # corresponding power and perform summation

    res = sum(d * 10**i for i, d in enumerate(list[::-1]))

    return(res)

# Driver code
list = [1, 2, 3]
print(convert(list))
```

**输出:**

```
123
```

这个程序的一个小变化导致在计算和时计算量减少，即使用 [`reduce()`](https://www.geeksforgeeks.org/reduce-in-python/) 。这利用了霍纳规则，该规则对代表数字的多项式进行因子化，以减少乘法次数。

```
res = functools.reduce(lambda total, d: 10 * total + d, list, 0)
```