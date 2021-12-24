# Python |在数字之间添加逗号

> 原文:[https://www . geesforgeks . org/python-add-逗号分隔数字/](https://www.geeksforgeeks.org/python-add-comma-between-numbers/)

有时，在处理货币时，我们需要在数字之间放置逗号来表示货币，因此给定一个字符串，我们在其中插入逗号可能会有问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用`str.format()`**
字符串格式函数可以通过提供有效的格式化程序来执行格式化。使用值作为参数调用字符串格式化程序来执行此特定任务。

```
# Python3 code to demonstrate working of
# Adding comma between numbers
# Using str.format()

# initializing number
test_num = 1234567

# printing original number 
print("The original number is : " + str(test_num))

# Using str.format()
# Adding comma between numbers
res = ('{:, }'.format(test_num))

# printing result 
print("The number after inserting commas : " + str(res))
```

**Output :**

```
The original number is : 1234567
The number after inserting commas : 1, 234, 567

```