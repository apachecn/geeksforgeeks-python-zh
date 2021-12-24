# Python |字符串列表中嵌入的数字求和

> 原文:[https://www . geesforgeks . org/python-embedded-numbers-summary-in-string-list/](https://www.geeksforgeeks.org/python-embedded-numbers-summation-in-string-list/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题，即我们需要连接字符串列表中的嵌入数字并执行求和。这可以在处理数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`join()` +循环**
上述功能的组合可用于执行该任务。在这种情况下，我们使用 join()执行提取数字的任务，使用 loop 执行求和的任务。

```
# Python3 code to demonstrate working of 
# Embedded Numbers Summation in String List
# Using join() + loop

# initializing list
test_list = ['g4fg', 'i4s5', 'b9e4st']

# printing original list
print("The original list is : " + str(test_list))

# Embedded Numbers Summation in String List
# Using join() + loop
res = 0
for sub in test_list:
    res += int(''.join(chr for chr in sub if chr.isdigit()))

# printing result 
print("The summation of strings : " + str(res)) 
```

**Output :**

```
The original list is : ['g4fg', 'i4s5', 'b9e4st']
The summation of strings : 143

```