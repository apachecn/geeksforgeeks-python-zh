# Python–从字典中获取特定嵌套级别的项目

> 原文:[https://www . geesforgeks . org/python-get-special-nested-level-items-from-dictionary/](https://www.geeksforgeeks.org/python-get-particular-nested-level-items-from-dictionary/)

给定一个字典，从特定级别提取条目。

**示例:**

> **输入**:{“Gfg”:{“n1”:3，“nd2”:{“N2”:6 } }，“is”:{“ne1”:5，“ndi 2”:{“ne2”:8，“ne22”:10 } }，K = 2
> **输出**:{“N2”:6，“ne2”:8，“ne22”:10 }
> **解释**:提取第 2 个嵌套项。
> 
> **输入**:{“Gfg”:{“n1”:3，“nd2”:{“N2”:6 } }，“is”:{“ne1”:5，“ndi 2”:{“ne2”:8，“ne22”:10 } }，K = 1
> **输出**:{“n1”:3，“ne1”:5 }
> **解释**:提取第一个嵌套的元素。

**方法:使用 [isinstance()](https://www.geeksforgeeks.org/python-isinstance-method/) + [递归](https://www.geeksforgeeks.org/recursion/)**

这是执行这项任务的方法之一。在这种情况下，我们为内部嵌套执行所需的递归，isinstance 用于区分 dict 实例和其他数据类型，以测试嵌套。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get particular Nested level Items from Dictionary
# Using isinstance() + recursion

# helper function

def get_items(test_dict, lvl):

    # querying for lowest level
    if lvl == 0:
        yield from ((key, val) for key, val in test_dict.items()
                    if not isinstance(val, dict))
    else:

        # recur for inner dictionaries
        yield from ((key1, val1) for val in test_dict.values()
                    if isinstance(val, dict) for key1, val1 in get_items(val, lvl - 1))

# initializing dictionary
test_dict = {"Gfg": { "n1": 3, "nd2": { "n2": 6 }}, 
             "is": { "ne1": 5, "ndi2": { "ne2": 8, "ne22": 10 } }}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 2

# calling function
res = get_items(test_dict, K)

# printing result
print("Required items : " + str(dict(res)))
```

**Output**

> 原始字典为:{'Gfg': {'n1': 3，' nd2': {'n2': 6}}，' is': {'ne1': 5，' ndi2': {'ne2': 8，' ne22': 10} }
> 必填项:{'n2': 6，' ne2': 8，' ne22 ':10 }