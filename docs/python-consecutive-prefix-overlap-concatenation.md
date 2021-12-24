# Python |连续前缀重叠拼接

> 原文:[https://www . geesforgeks . org/python-continuous-prefix-overlap-concation/](https://www.geeksforgeeks.org/python-consecutive-prefix-overlap-concatenation/)

有时，在使用 Python 字符串时，我们可能会有需要执行字符串列表中所有元素的连接的应用程序。这可能是棘手的情况下，我们需要重叠当前元素的后缀与前缀的下一个匹配的情况下。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `endswith() + join() + list comprehension + zip()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用循环作为使用 endswith()的连接/不连接的逻辑。如果是联接，则使用联接()执行。整个逻辑是在列表理解中编译的。

```
# Python3 code to demonstrate working of 
# Consecutive prefix overlap concatenation
# Using endswith() + join() + list comprehension + zip() + loop

def help_fnc(i, j):
    for ele in range(len(j), -1, -1):
        if i.endswith(j[:ele]):
            return j[ele:]

# initializing list
test_list = ["gfgo", "gone", "new", "best"]

# printing original list
print("The original list is : " + str(test_list))

# Consecutive prefix overlap concatenation
# Using endswith() + join() + list comprehension + zip() + loop
res = ''.join(help_fnc(i, j) for i, j in zip([''] + 
                           test_list, test_list))

# printing result 
print("The resultant joined string : " + str(res)) 
```

**Output :**

```
The original list is : ['gfgo', 'gone', 'new', 'best']
The resultant joined string : gfgonewbest

```