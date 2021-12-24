# Python |连续字符串比较

> 原文:[https://www . geesforgeks . org/python-continuous-string-comparison/](https://www.geeksforgeeks.org/python-consecutive-string-comparison/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要在一个字符串和它在列表中的下一个元素之间进行比较，并返回下一个元素与列表相似的所有字符串。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +循环**
这是执行该任务的一种方式。在这种情况下，我们使用 zip()来组合元素和它的下一个元素，然后比较真相并将其保存在列表中。

```
# Python3 code to demonstrate working of
# Consecutive String Comparison
# using zip() + loop

# initialize list 
test_list = ['gfg', 'gfg', 'is', 'best', 'best', 'for', 'geeks', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# Consecutive String Comparison
# using zip() + loop
res = []
for i, j in zip(test_list, test_list[1: ]):
    if i == j:
        res.append(i)

# printing result
print("List of Consecutive similar elements : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'gfg', 'is', 'best', 'best', 'for', 'geeks', 'geeks']
List of Consecutive similar elements : ['gfg', 'best', 'geeks']

```