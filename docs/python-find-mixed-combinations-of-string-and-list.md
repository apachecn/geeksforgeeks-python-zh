# Python |查找字符串和列表的混合组合

> 原文:[https://www . geesforgeks . org/python-find-字符串和列表的混合组合/](https://www.geeksforgeeks.org/python-find-mixed-combinations-of-string-and-list/)

有时，在使用 Python 时，我们可能会遇到一个问题，即需要对字符串和字符列表进行组合。这类问题可能出现在我们需要交错数据的领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `enumerate() + replace()`**
该任务可以使用上述功能的组合来执行。在这种情况下，我们只需迭代字符列表的每个元素，并使用强力方式插入每个组合。

```py
# Python3 code to demonstrate working of
# Mixed Combinations of string and list
# using loop + enumerate() + replace()

# initialize list and string 
test_list = ["a", "b", "c"]
test_str = "gfg"

# printing original list and string
print("The original list : " + str(test_list))
print("The original string : " + test_str)

# Mixed Combinations of string and list
# using loop + enumerate() + replace()
res = []
for idx, ele in enumerate(test_str):
    res += [test_str[ : idx] + test_str[idx : ].replace(ele, k, 1)
            for k in test_list]

# printing result
print("The list after mixed Combinations : " + str(res))
```

**Output :**

> 原列表:['a '，' b '，' c']
> 原字符串:gfg
> 混合组合后的列表:['afg '，' bfg '，' cfg '，' gag '，' gbg '，' gcg '，' gfa '，' gfb '，' gfc']