# Python |计数不匹配的元素

> 原文:[https://www . geeksforgeeks . org/python-计数-不匹配-元素/](https://www.geeksforgeeks.org/python-count-unmatched-elements/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时，我们还需要获得与特定条件不匹配的总数，以区分哪种匹配可以进一步利用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们迭代列表，找到不符合特定条件的元素并计数。

## 蟒蛇 3

```
# Python 3 code to demonstrate 
# Count unmatched elements
# using loop

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using loop
# Count unmatched elements
# checks for odd
res = 0
for ele in test_list:
    if not ele % 2 != 0:
        res = res + 1

# printing result
print ("The number of non-odd elements: " + str(res))
```

**Output : **

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of non-odd elements: 1
```

**方法#2:使用 len() +生成器表达式**
每当生成器表达式返回 False 时，该方法就使用对元素计数的技巧来添加 1。当列表耗尽时，返回不匹配条件的数字计数。

## 蟒蛇 3

```
# Python 3 code to demonstrate 
# Count unmatched elements
# using len() + generator expression

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using len() + generator expression
# Count unmatched elements
# checks for odd
res = len(list(i for i in test_list if not i % 2 != 0))

# printing result
print ("The number of non-odd elements: " + str(res))
```

**Output : **

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of non-odd elements: 1
```