# Python–交错两个不同长度的列表

> 原文:[https://www . geeksforgeeks . org/python-interlace-两个不同长度的列表/](https://www.geeksforgeeks.org/python-interleave-two-lists-of-different-length/)

给定两个不同长度的列表，任务是编写一个 Python 程序来交替获取它们的元素，并重复较小列表的列表元素，直到较大的列表元素耗尽。

**示例:**

> **输入:** test_list1 = ['a '，' b '，' c']，test_list2 = [5，7，3，0，1，8，4]
> 
> **输出:** ['a '，5，' b '，7，' c '，3，' a '，0，' b '，1，' c '，8，' a '，4]
> 
> **说明:**第一个列表中的替代元素一旦耗尽，就会以循环方式打印。耗尽后，第一个列表再次从“a”开始，元素留在第二个列表中。
> 
> **输入:** test_list1 = [3，8，7]，test_list2 = [5，7，3，0，1，8]
> 
> **输出:**【3，5，8，7，7，3，3，0，8，1，7，8】
> 
> **说明:**第一个列表中的替代元素一旦耗尽，就会以循环方式打印。3, 5, 8, 7, 7, 3..然后在耗尽之后，第一个列表再次从 3 开始，元素留在第二个列表中

**方法#1:使用**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**循环()**](https://www.geeksforgeeks.org/python-itertools-cycle/) **+** [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/)

在这种情况下，使用 cycle()处理较小列表中元素的重复，使用 zip()完成连接。列表理解同时执行交错任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Repetitive Interleave 2 lists
# Using zip() + cycle() + list comprehension 
from itertools import cycle

# initializing lists
test_list1 = list('abc')
test_list2 = [5, 7, 3, 0, 1, 8, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# zip() combining list, after Repetitiveness using cycle()
res = [ele for comb in zip(cycle(test_list1), test_list2) for ele in comb]

# printing result
print("The interleaved list : " + str(res))
```

**输出:**

> 原始列表 1 是:['a '，' b '，' c']
> 
> 原始列表 2 是:[5，7，3，0，1，8，4]
> 
> 交错列表:['a '，5，' b '，7，' c '，3，' a '，0，' b '，1，' c '，8，' a '，4]

**方法 2:使用** [**链()**](https://www.geeksforgeeks.org/python-itertools-chain/) **+ zip() + cycle()**

大多数操作与上述方法一样，唯一的区别是交织任务是使用链()执行的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Repetitive Interleave 2 lists
# Using chain() + zip() + cycle()
from itertools import cycle, chain

# initializing lists
test_list1 = list('abc')
test_list2 = [5, 7, 3, 0, 1, 8, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# zip() combining list, after Repetitiveness using cycle()
# chain() gets interleaved done
res = list(chain(*zip(cycle(test_list1), test_list2)))

# printing result
print("The interleaved list : " + str(res))
```

**输出:**

> 原始列表 1 是:['a '，' b '，' c']
> 
> 原始列表 2 是:[5，7，3，0，1，8，4]
> 
> 交错列表:['a '，5，' b '，7，' c '，3，' a '，0，' b '，1，' c '，8，' a '，4]