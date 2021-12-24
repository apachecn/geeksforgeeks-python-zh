# Python |分组并统计相似记录

> 原文:[https://www . geesforgeks . org/python-group-and-count-similar-records/](https://www.geeksforgeeks.org/python-group-and-count-similar-records/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要收集和维护记录中的计数器值。这种应用在 web 开发领域非常重要。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+ `Counter() + set()`**
可以使用上述功能的组合来实现该任务。在这种情况下，我们运行一个循环来捕获每个元组并添加到集合中，检查它是否已经存在，然后增加并添加一个计数器值。累计计数通过`Counter()`实现。

```py
# Python3 code to demonstrate working of
# Group and count similar records
# using Counter() + loop + set()
from collections import Counter

# initialize list
test_list = [('gfg', ), ('is', ), ('best', ), ('gfg', ),
                       ('is', ), ('for', ), ('geeks', )]

# printing original list
print("The original list : " + str(test_list))

# Group and count similar records
# using Counter() + loop + set()
res = []
temp = set()
counter = Counter(test_list)
for sub in test_list:
    if sub not in temp:
        res.append((counter[sub], ) + sub)
        temp.add(sub)

# printing result
print("Grouped and counted list is : " + str(res))
```

**Output :**

> 原始列表:[('gfg '，)，(' is '，)，(' best '，)，(' gfg '，)，(' is '，)，(' for '，)，(' geeks '，)]
> 分组计数列表为:[(2，' gfg ')，(2，' is ')，(1，' best '，(1，' for ')，(1，' geeks')]