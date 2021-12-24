# Python |将单个值与所有列表项相关联

> 原文:[https://www . geesforgeks . org/python-将单值与所有列表项相关联/](https://www.geeksforgeeks.org/python-associating-a-single-value-with-all-list-items/)

有时我们遇到一个工具，其中我们有一个列表，我们希望将其与任何一个给定的值相关联。这可能发生在编程的许多阶段，知道它的不足可能是有用的。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map()` + lambda**
这个任务可以使用 map 函数来完成，map 函数是内置的 python 函数，通常用于关联或聚合值。Lambda 函数可以为 map 函数提供一个特定的值来执行它。

```
# Python3 code to demonstrate
# associate value in list 
# using map() + lambda

# initializing list
test_list = [1, 4, 5, 8, 3, 10]

# initializing value to associate
val = 'geeks'

# printing the original list
print ("The original list is : " + str(test_list))

# printing value 
print ("The value to be attached to each value : " +  str(val))

# using map() + lambda
# associate value in list 
res = list(map(lambda i: (i, val), test_list))

# printing result
print ("The modified attached list is : " + str(res))
```

**Output :**

> 原列表为:【1、4、5、8、3、10】
> 每个值要附加的值:极客
> 修改后的附加列表为:[(1，‘极客’)、(4，‘极客’)、(5，‘极客’)、(8，‘极客’)、(3，‘极客’)、(10，‘极客’)]