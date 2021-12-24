# Python |在另一个列表中插入列表

> 原文:[https://www . geesforgeks . org/python-insert-list-in-other-list/](https://www.geeksforgeeks.org/python-insert-list-in-another-list/)

在任何索引处插入一个数字是一个很常见的问题。但有时我们需要将整个列表插入另一个列表。这类问题出现在机器学习中玩数据的时候。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 `insert()` +循环**
在这个方法中，我们使用 insert 函数一次一个元素地插入。这样，我们在其他列表的指定索引处添加所有列表元素。

```
# Python3 code to demonstrate 
# to insert one list in another
# using insert() + loop

# initializing lists 
test_list = [4, 5, 6, 3, 9]
insert_list = [2, 3]

# initializing position
pos = 2

# printing original list
print ("The original list is : " + str(test_list))

# printing insert list 
print ("The list to be inserted is : " + str(insert_list))

# using insert() + loop
# to insert one list in another
for i in range(len(insert_list)):
    test_list.insert(i + pos, insert_list[i])

# printing result 
print ("The list after insertion is : " +  str(test_list))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list to be inserted is : [2, 3]
The list after insertion is : [4, 5, 2, 3, 6, 3, 9]

```

**方法#2:使用列表切片**
这是执行这个特殊任务的最蟒化最优雅的方式。在这个方法中，我们只是在需要添加元素的地方对列表进行切片，并分配要插入的列表。

```
# Python3 code to demonstrate 
# to insert one list in another
# using list slicing

# initializing lists 
test_list = [4, 5, 6, 3, 9]
insert_list = [2, 3]

# initializing position
pos = 2

# printing original list
print ("The original list is : " + str(test_list))

# printing insert list 
print ("The list to be inserted is : " + str(insert_list))

# using list slicing
# to insert one list in another
test_list[pos:pos] = insert_list

# printing result 
print ("The list after insertion is : " +  str(test_list))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list to be inserted is : [2, 3]
The list after insertion is : [4, 5, 2, 3, 6, 3, 9]

```