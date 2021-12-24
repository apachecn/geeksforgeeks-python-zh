# Python |检查列表是否排序

> 原文:[https://www . geesforgeks . org/python-检查列表是否已排序/](https://www.geeksforgeeks.org/python-check-if-list-is-sorted-or-not/)

列表的排序操作是许多应用中必不可少的操作。但是它充分利用了时间复杂性，因此人们希望避免这种情况。因此，为了检查这是否是必需的，知道列表是否默认排序，可以检查列表是否排序。让我们讨论实现这一目标的各种方法。

**方法#1:天真的方法**
检查这个最简单的方法是对第一个元素运行一个循环，检查我们是否能在那个元素之后找到比它更小的元素，如果是，则列表没有排序。

```
# Python3 code to demonstrate 
# to check if list is sorted
# using naive method 

# initializing list
test_list = [1, 4, 5, 8, 10]

# printing original list 
print ("Original list : " + str(test_list))

# using naive method to 
# check sorted list 
flag = 0
i = 1
while i < len(test_list):
    if(test_list[i] < test_list[i - 1]):
        flag = 1
    i += 1

# printing result
if (not flag) :
    print ("Yes, List is sorted.")
else :
    print ("No, List is not sorted.")
```

**输出:**

```
Original list : [1, 4, 5, 8, 10]
Yes, List is sorted.

```

**方法 2:使用`sort()`**
可以将新列表制作成原列表的副本，对新列表进行排序，并与旧列表进行比较，得出是否需要排序才能得到排序列表的结果。

```
# Python3 code to demonstrate 
# to check if list is sorted
# using sort()

# initializing list
test_list = [10, 4, 5, 8, 10]

# printing original list 
print ("Original list : " + str(test_list))

# using sort() to 
# check sorted list 
flag = 0
test_list1 = test_list[:]
test_list1.sort()
if (test_list1 == test_list):
    flag = 1

# printing result
if (flag) :
    print ("Yes, List is sorted.")
else :
    print ("No, List is not sorted.")
```

**输出:**

```
Original list : [10, 4, 5, 8, 10]
No, List is not sorted.

```

**方法 3:使用`sorted()`**
使用与上述方法类似的类比，但并不创造一个新的空间，而只是那个时间的一个瞬间空间，因此比上述方法有用、更短、更快。

```
# Python3 code to demonstrate 
# to check if list is sorted
# using sorted()

# initializing list
test_list = [1, 4, 5, 8, 10]

# printing original list 
print ("Original list : " + str(test_list))

# using sorted() to 
# check sorted list 
flag = 0
if(test_list == sorted(test_list)):
    flag = 1

# printing result
if (flag) :
    print ("Yes, List is sorted.")
else :
    print ("No, List is not sorted.")
```

**输出:**

```
Original list : [1, 4, 5, 8, 10]
Yes, List is sorted.

```

**方法#4:使用`all()`**
最优雅、pythonic 化和更快速的检查排序列表的方法是使用`all()`。这使用了与天真相似的方法，但使用`all()`使其更快。

```
# Python3 code to demonstrate 
# to check if list is sorted
# using all()

# initializing list
test_list = [9, 4, 5, 8, 10]

# printing original list 
print ("Original list : " + str(test_list))

# using all() to 
# check sorted list 
flag = 0
if(all(test_list[i] <= test_list[i + 1] for i in range(len(test_list)-1))):
    flag = 1

# printing result
if (flag) :
    print ("Yes, List is sorted.")
else :
    print ("No, List is not sorted.")
```

**输出:**

```
Original list : [9, 4, 5, 8, 10]
No, List is not sorted.

```