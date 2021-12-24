# Python–按顺序在开头插入

> 原文:[https://www . geeksforgeeks . org/python-插入-在开始时插入-按顺序排列/T0/](https://www.geeksforgeeks.org/python-insertion-at-the-beginning-in-ordereddict/)

给定一个有序字典，编写一个程序在有序字典的开头插入条目。
**示例–**

```
Input: 
original_dict = {'a':1, 'b':2}
item to be inserted ('c', 3)

Output:  {'c':3, 'a':1, 'b':2}

Input: 
original_dict = {'akshat':1, 'manjeet':2}
item to be inserted ('nikhil', 3)

Output:  {'nikhil':3, 'akshat':1, 'manjeet':2}
```

以下是在有序字典的开始插入条目的各种方法。
**方法#1:使用 ordereddict . move _ to _ end()**

## 蟒蛇 3

```
# Python code to demonstrate
# insertion of items in beginning of ordered dict
from collections import OrderedDict

# initialising ordered_dict
iniordered_dict = OrderedDict([('akshat', '1'), ('nikhil', '2')])

# inserting items in starting of dict
iniordered_dict.update({'manjeet':'3'})
iniordered_dict.move_to_end('manjeet', last = False)

# print result
print ("Resultant Dictionary : "+str(iniordered_dict))
```

**输出:**

> 结果字典:ordereddct([(' manjeet '，' 3 ')，(' akshat '，' 1 '，(' nikhil '，' 2')])

**方法 2:使用天真方法**
该方法仅在唯一键
的情况下有效

## 蟒蛇 3

```
# Python code to demonstrate
# insertion of items in beginning of ordered dict
from collections import OrderedDict

# initialising ordered_dict
ini_dict1 = OrderedDict([('akshat', '1'), ('nikhil', '2')])
ini_dict2 = OrderedDict([("manjeet", '4'), ("akash", '4')])

# adding in beginning of dict
both = OrderedDict(list(ini_dict2.items()) + list(ini_dict1.items()))

# print result
print ("Resultant Dictionary :"+str(both))
```

**输出:**

> 结果字典:ordereddct([(' manjeet '，' 4 ')，(' akash '，' 4 ')，(' akshat '，' 1 ')，(' nikhil '，' 2')])