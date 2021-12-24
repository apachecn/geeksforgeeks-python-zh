# Python |列表中偶数前位数测试

> 原文:[https://www . geesforgeks . org/python-偶数-前位数-列表测试/](https://www.geeksforgeeks.org/python-even-front-digits-test-in-list/)

有时我们可能会遇到一个问题，如果一个列表包含偶数，我们需要查找它。这个特殊的工具在日常编程中有应用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用列表理解+ `map()`**
我们可以通过将元素转换为字符串，然后测试字符串的起始元素来解决这个问题，如果它们是偶数，我们可以返回 true，然后转换为 set，并测试结果的大小是否为 1。转换是通过映射完成的，set 函数将字符串的第一个元素转换为 set 并列出理解检查。

```py
# Python3 code to demonstrate 
# Even Front digits Test in List
# using list comprehension + map() 

# initializing list 
test_list = [25, 6, 828829, 432] 

# printing original list 
print("The original list : " + str(test_list)) 

# using list comprehension + map() 
# Even Front digits Test in List 
res = len(set((int(sub[0]) % 2) for sub in map(str, test_list))) == 1

# print result 
print("Does each element start with even digit ? " + str(res)) 
```

**Output :**

```py
The original list : [25, 6, 828829, 432]
Does each element start with even digit ? True

```