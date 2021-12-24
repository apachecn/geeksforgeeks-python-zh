# Python |检查一个列表是否是其他列表的子集

> 原文:[https://www . geesforgeks . org/python-如果一个列表是另一个列表的子集，请检查/](https://www.geeksforgeeks.org/python-check-if-one-list-is-subset-of-other/)

有时我们会遇到这样的问题:检查一个列表是否只是列表的扩展，即是否只是一个列表的超集。这类问题在竞争性编程中相当普遍。人手不足有助于这一事业。让我们讨论实现这一特定任务的各种方法。
**方法#1:使用 all()**
all()用于只检查一行中容器的所有元素。检查一个列表中的所有元素是否存在于另一个列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if list is subset of other
# using all()

# initializing list
test_list = [9, 4, 5, 8, 10]
sub_list = [10, 5, 4]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original sub list : " + str(sub_list))

# using all() to
# check subset of list
flag = 0
if(all(x in test_list for x in sub_list)):
    flag = 1

# printing result
if (flag) :
    print ("Yes, list is subset of other.")
else :
    print ("No, list is not subset of other.")
```

**输出:**

```
Original list : [9, 4, 5, 8, 10]
Original sub list : [10, 5, 4]
Yes, list is subset of other.
```

**方法#2:使用 set.issubset()**
检查子列表最常用和推荐的方法。这个函数是为执行检查一个列表是否是另一个列表的子集的特定任务而定制的。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if list is subset of other
# using issubset()

# initializing list
test_list = [9, 4, 5, 8, 10]
sub_list = [10, 5]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original sub list : " + str(sub_list))

# using issubset() to
# check subset of list
flag = 0
if(set(sub_list).issubset(set(test_list))):
    flag = 1

# printing result
if (flag) :
    print ("Yes, list is subset of other.")
else :
    print ("No, list is not subset of other.")
```

**输出:**

```
Original list : [9, 4, 5, 8, 10]
Original sub list : [10, 5]
Yes, list is subset of other.
```

**方法#3:使用 set.intersection()**
再一个处理集合的方法，这个方法检查两个列表的交集是否是我们正在检查的子列表。这确认了一个列表是另一个列表的子集。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if list is subset of other
# using intersection()

# initializing list
test_list = [9, 4, 5, 8, 10]
sub_list = [10, 5]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original sub list : " + str(sub_list))

# using intersection() to
# check subset of list
flag = 0
if((set(sub_list) & set(test_list))== set(sub_list)):
    flag = 1

# printing result
if (flag) :
    print ("Yes, list is subset of other.")
else :
    print ("No, list is not subset of other.")
```

**输出:**

```
Original list : [9, 4, 5, 8, 10]
Original sub list : [10, 5]
Yes, list is subset of other.
```

**方法#4:使用迭代和计数器**
使用两个列表中元素的计数来检查第二个列表是否是第一个列表的子集。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if list is subset of other

#Importing
from collections import Counter

def checkInFirst(a, b):
     #getting count
    count_a = Counter(a)
    count_b = Counter(b)

    #checking if element exists in second list
    for key in count_b:
        if key not in  count_a:
            return False
        if count_b[key] > count_b[key]:
            return False
    return True

# initializing list
a = [1, 2,4,5]
b = [1, 2,3]

#Calling function
res = checkInFirst(a, b)

#Printing list
print ("Original list : " + str(a))
print ("Original sub list : " + str(b))

if res==True :
    print ("Yes, list is subset of other.")
else :
    print ("No, list is not subset of other.")

#Added by Paras Jain(everythingispossible)
```

**输出:**

```
Original list : [1, 2, 4, 5]
Original sub list : [1, 2, 3]
No, list is not subset of other.
```

**方法五:使用设定指标**

## 蟒蛇 3

```
# Python3 code to demonstrate
# to check if list is subset of other

# initializing list
one = [1,2,3,4,5]
two = [1,2]

#using set to find if element exists in another list
result = set(x in one for x in two)

flag = 0

for ans in result:
    if ans == False:
        flag=1

#Printing list
print ("Original list : " + str(one))
print ("Original sub list : " + str(two))

if flag==0:
    print("Yes, list is subset of other.")
else:
    print("No, list is not subset of other.")

#Added by Paras Jain(everythingispossible)
```

**输出:**

```
Original list : [1, 2, 3, 4, 5]
Original sub list : [1, 2]
Yes, list is subset of other.
```