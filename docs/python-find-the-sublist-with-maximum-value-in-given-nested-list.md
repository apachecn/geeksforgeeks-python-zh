# Python |在给定的嵌套列表中找到最大值的子列表

> 原文:[https://www . geeksforgeeks . org/python-find-the-sublist-with-value-in-给定嵌套列表/](https://www.geeksforgeeks.org/python-find-the-sublist-with-maximum-value-in-given-nested-list/)

给定一个列表列表，任务是在第二列中找到具有最大值的子列表。

**示例:**

```
Input : [['Paras', 90], ['Jain', 32], ['Geeks', 120],
                        ['for', 338], ['Labs', 532]]
Output :['Labs', 532]

Input: [['Geek', 90], ['For', 32], ['Geeks', 120]]
Output: ['Geeks', 120]

```

下面是一些完成上述任务的任务。

**方法#1:使用λ**

```
# Python code to find maximum value 
# in second column of list of list

# Input list initialization
Input = [['Paras', 90], ['Jain', 32], ['Geeks', 120],
                        ['for', 338], ['Labs', 532]]
# Using lambda 
Output = max(Input, key = lambda x: x[1])

# printing output
print("Input List is :", Input)
print("Output list is : ", Output)
```

**Output:**

> 输入列表为:[['Paras '，90]，['Jain '，32]，['Geeks '，120]，['for '，338]，['Labs '，532]]
> 输出列表为:['Labs '，532]

**方法 2:使用 itemgetter**

```
# Python code to find maximum value 
# in second column of list of list

# Importing
import operator 

# Input list initialization
Input = [['Paras', 90], ['Jain', 32], ['Geeks', 120],
                        ['for', 338], ['Labs', 532]]
# Using itemgetter
Output = max(Input, key = operator.itemgetter(1))

# Printing output
print("Input List is :", Input)
print("Output list is : ", Output)
```

**Output:**

> 输入列表为:[['Paras '，90]，['Jain '，32]，['Geeks '，120]，['for '，338]，['Labs '，532]]
> 输出列表为:['Labs '，532]