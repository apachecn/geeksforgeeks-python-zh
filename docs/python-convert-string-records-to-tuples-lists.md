# Python–将字符串记录转换为元组列表

> 原文:[https://www . geesforgeks . org/python-convert-string-records-to-元组-list/](https://www.geeksforgeeks.org/python-convert-string-records-to-tuples-lists/)

有时，在处理数据时，我们可能会遇到这样的问题:需要将字符串格式的数据列表转换为元组列表。这可能发生在我们有交叉类型输入的域中。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `eval()`**
以上方法的组合可以用来解决这个任务。在这种情况下，我们在对 eval 函数的输入进行处理以转换为 Tuple 列表后，重新构建字符串。

```
# Python3 code to demonstrate working of 
# Convert String Records to Tuples Lists
# Using loop + eval()

# initializing string
test_str = '[(gfg, ), (is, ), (best, )]'

# printing original string
print("The original string is : " + test_str)

# Convert String Records to Tuples Lists
# Using loop + eval()
res = ''
temp = True
for chr in test_str:
    if chr == '(' and temp:
        res += '("'
        temp = False
        continue
    if chr == ', ' and not temp:
        res += '"'
        temp = True
    res += chr
res = eval(res)

# printing result 
print("The list of Tuples is : " + str(res)) 
```

**Output :**

```
The original string is : [(gfg, ), (is, ), (best, )]
The list of Tuples is : [('gfg', ), ('is', ), ('best', )]

```