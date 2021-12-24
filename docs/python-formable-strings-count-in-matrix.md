# Python-矩阵中可成型字符串的数量

> 原文:[https://www . geesforgeks . org/python-formulated-strings-count-in-matrix/](https://www.geeksforgeeks.org/python-formable-strings-count-in-matrix/)

给定字符串矩阵，任务是编写一个 Python 程序来计算字符串，这些字符串可以由给定列表中的字母组成。

**示例:**

> **输入**:test _ list =[[“gfg”、“best”]，[“all”、“love”、“gfg”]，[“gfg”、“is”、“good”]，[“geeksforgeeks”]，tar _ list =[“g”、“f”、“s”、“b”、“o”、“d”、“e”、“t”]
> **输出** : 5
> **解释** : gfg、best、gfg、gfg、good 都是可以由目标列表字符组成的字符串。
> 
> **输入**:test _ list =[[“gfg”、“best”]，[“all”、“love”、“gfg”]，[“gfg”、“is”、“good”]，[“geeksforgeeks”]，tar _ list =[“g”、“f”、“s”、“b”、“d”、“e”、“t”]
> **输出** : 4
> **解释** : gfg、best、gfg、gfg 都是可以由目标列表字符组成的字符串。

**方法#1:使用 loop +** [**all()**](https://www.geeksforgeeks.org/any-all-in-python/)

在本例中，我们使用 for 循环执行循环迭代任务，all()用于检查字符串的每个元素是否包含目标列表中的所有字母。如果找到，计数器将递增。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Formable Strings Count in Matrix
# Using loop

# initializing list
test_list = [["gfg", "best"], ["all", "love", "gfg"],
             ["gfg", "is", "good"], ["geeksforgeeks"]]

# printing original list
print("The original list is : " + str(test_list))

# initializing target list
tar_list = ["g", "f", "s", "b", "o", "d", "e", "t"]

res = 0
for sub in test_list:
    for ele in sub:

        # checking for all elements present using all()
        if all(el in tar_list for el in ele):
            res += 1

# printing result
print("The computed count : " + str(res))
```

**输出:**

> 原始列表为:[['gfg '，' best']，['all '，' love '，' gfg']，['gfg '，' is '，' good']，[' geeksforgeeks ']
> 计算出的计数:5

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/) **+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/)

在这种情况下，使用列表理解在一行中解决问题，all()用于检查所有存在的字符，sum()用于计算字符串过滤后的字符串数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Formable Strings Count in Matrix
# Using list comprehension + all() + sum()

# initializing list
test_list = [["gfg", "best"], ["all", "love", "gfg"],
             ["gfg", "is", "good"], ["geeksforgeeks"]]

# printing original list
print("The original list is : " + str(test_list))

# initializing target list
tar_list = ["g", "f", "s", "b", "o", "d", "e", "t"]

# computing summation using sum()
# list comprehension used to provide one liner solution
res = sum([sum([1 for ele in sub if all(el in tar_list for el in ele)])
           for sub in test_list])

# printing result
print("The computed count : " + str(res))
```

**输出:**

> 原始列表为:[['gfg '，' best']，['all '，' love '，' gfg']，['gfg '，' is '，' good']，[' geeksforgeeks ']
> 计算出的计数:5