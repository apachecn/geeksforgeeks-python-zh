# Python |索引最小值记录

> 原文:[https://www . geesforgeks . org/python-index-minimum-value-record/](https://www.geeksforgeeks.org/python-index-minimum-value-record/)

在 python 中，我们可以以元组的形式绑定一个结构信息，然后可以检索相同的信息，并有多种应用。但有时我们需要对应于其他元组索引最小值的元组信息。这个功能有很多应用，比如排名。让我们讨论实现这一目标的某些方法。

**方法#1:使用`min() + operator.itemgetter()`**
我们可以使用提供的 key itemgetter 索引从一个列表中获取对应元组索引的最小值，然后在最后使用 index 规范提到所需的索引信息。

```
# Python 3 code to demonstrate 
# Index minimum value Record
# using min() + itemgetter()
from operator import itemgetter

# initializing list 
test_list = [('Rash', 143), ('Manjeet', 200), ('Varsha', 100)]

# printing original list 
print ("Original list : " + str(test_list))

# using min() + itemgetter()
# Index minimum value Record
res = min(test_list, key = itemgetter(1))[0]

# printing result
print ("The name with minimum score is : " + res)
```

**Output :**

```
Original list : [('Rash', 143), ('Manjeet', 200), ('Varsha', 100)]
The name with minimum score is : Varsha

```