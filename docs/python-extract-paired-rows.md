# Python–提取成对行

> 原文:[https://www.geeksforgeeks.org/python-extract-paired-rows/](https://www.geeksforgeeks.org/python-extract-paired-rows/)

给定一个矩阵，任务是编写一个 Python 程序来提取具有成对元素的所有行。即元素具有 mod 2 的频率。

> **输入** : test_list = [[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2]]
> **输出** : [[5，5，4，7，7，4]，[1，1，2，2]]
> **解释**:所有行都有对元素，即有偶发生。
> 
> **输入** : test_list = [[10，2，3，2，3]，[5，5，4，7，4]，[1，2]，[1，1，2，2]]
> **输出** : [[1，1，2，2]]
> **解释**:所有行都有对元素，即偶有出现。

**方法一:使用**[**all()**](https://www.geeksforgeeks.org/python-all-function/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在这种情况下，我们使用 *count()* 来检查每个元素的计数，并且使用 *all()* 来测试所有元素的频率是否可被 2 整除。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Paired Rows
# Using all() + list comprehension + count()

# initializing list
test_list = [[10, 2, 3, 2, 3], [5, 5, 4, 7, 7, 4],
             [1, 2], [1, 1, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# count() checks for frequency to be mod 2
res = [row for row in test_list if all(
  row.count(ele) % 2 == 0 for ele in row)]

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2]]
> 提取的行:[[5，5，4，7，7，4]，[1，1，2，2]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+**[**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)**+**[T21【all()](https://www.geeksforgeeks.org/python-all-function/)**T25】**

在本例中，我们使用 *filter()* 和 *lambda* 函数代替列表理解来执行过滤任务。*计数()*和 *all()* 用于检查行中所有元素的频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Paired Rows
# Using filter() + lambda + count() + all()

# initializing list
test_list = [[10, 2, 3, 2, 3], [5, 5, 4, 7, 7, 4],
             [1, 2], [1, 1, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# count() checks for frequency to be mod 2
# filter() and lambda used to perform filtering
res = list(filter(lambda row: all(
  row.count(ele) % 2 == 0 for ele in row), test_list))

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2]]
> 提取的行:[[5，5，4，7，7，4]，[1，1，2，2]]