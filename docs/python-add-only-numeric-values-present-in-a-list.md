# Python |仅添加列表中的数值

> 原文:[https://www . geesforgeks . org/python-add-only-numeric-values-present-in-a-list/](https://www.geeksforgeeks.org/python-add-only-numeric-values-present-in-a-list/)

给定一个包含字符和数字的列表，任务是只添加列表中的数字。下面给出了一些完成给定任务的方法。

**方法一:使用`filter()``lambda`**

```py
# Python code to demonstrate
# how to add only numbers present
# in a list of characters and numbers

# initialising lists
ini_list = [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']

# printing initial list
print ("initial list", str(ini_list))

# code to add numbers from list
res = sum(filter(lambda i: isinstance(i, int), ini_list))

# printing result
print ("resultant sum", res)
```

**Output:**

```py
initial list [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']
resultant sum 15

```

**方法 2:使用试除**

```py
# Python code to demonstrate
# how to add only numbers present
# in a list of characters and numbers

# initialising lists
ini_list = [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']

# printing initial list
print ("initial list", str(ini_list))

# code to add numbers from list
res = 0
for item in ini_list:
    try:
        res+= int(item)
    except ValueError:
        pass

# printing result
print ("resultant sum", res)
```

**Output:**

```py
initial list [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']
resultant sum 15

```

**方法 3:使用 isinstance 和条件语句**

```py
# Python code to demonstrate
# how to add only numbers present
# in a list of characters and numbers

# initialising lists
ini_list = [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']

# printing initial list
print ("initial list", str(ini_list))

# code to add numbers from list
res = sum([x for x in ini_list if isinstance(x, int)])

# printing result
print ("resultant sum", res)
```

**Output:**

```py
initial list [1, 2, 3, 4, 'a', 'b', 'x', 5, 'z']
resultant sum 15

```