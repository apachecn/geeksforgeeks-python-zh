# Python–从列表值中提取前一条记录

> 原文:[https://www . geesforgeks . org/python-extract-previous-record-from-list-values/](https://www.geeksforgeeks.org/python-extract-preceding-record-from-list-values/)

有时，在处理元组记录时，我们可能会遇到一个问题，即我们需要提取记录，该记录位于所提供的特定键之前。这种问题可以应用于诸如 web 开发和日常编程等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [('Gfg '，3)、(' is '，4)、(' best '，1)、(' for '，10)、(' geeks '，11)]，键= 'geeks'
> **输出** : ('for '，10)
> **输入** : test_list = [('Gfg '，3)、(' is '，4)、(' best '，1)、(' for '，10)、(' geeks '，11)]，键= 'is '

**方法#1:使用 zip() + enumerate() + loop**
以上功能的组合可以用来执行这个特定的任务。在这里，我们创建了两个列表，一个从下一个索引开始。zip()有助于连接它们，并使用枚举()提取索引来返回所需的结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Preceding Record
# Using zip() + enumerate() + loop

# initializing list
test_list = [('Gfg', 3), ('is', 4), ('best', 1), ('for', 10), ('geeks', 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Key
key = 'for'

# Extract Preceding Record
# Using zip() + enumerate() + loop
for idx, (a, b) in enumerate(zip(test_list, test_list[1:])):
    if b[0] == key:
        res = (a[0], a[1])

# printing result
print("The Preceding record : " + str(res))
```

**Output**

```
The original list is : [('Gfg', 3), ('is', 4), ('best', 1), ('for', 10), ('geeks', 11)]
The Preceding record : ('best', 1)

```

**方法 2:使用列表理解+枚举()**
以上函数的组合可以用来解决这个问题。在这种情况下，我们执行提取前一个元素的任务来手动测试前一个键，而不是像前一个方法那样创建一个单独的列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Preceding Record
# Using list comprehension + enumerate()

# initializing list
test_list = [('Gfg', 3), ('is', 4), ('best', 1), ('for', 10), ('geeks', 11)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Key
key = 'for'

# Extract Preceding Record
# Using list comprehension + enumerate()
res = [(test_list[idx - 1][0], test_list[idx - 1][1])
      for idx, (x, y) in enumerate(test_list) if x == key and idx > 0]

# printing result
print("The Preceding record : " + str(res))
```

**Output**

```
The original list is : [('Gfg', 3), ('is', 4), ('best', 1), ('for', 10), ('geeks', 11)]
The Preceding record : [('best', 1)]

```