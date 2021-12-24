# Python |如何获取列表最后一个元素

> 原文:[https://www . geesforgeks . org/python-如何获取列表中的最后一个元素/](https://www.geeksforgeeks.org/python-how-to-get-the-last-element-of-list/)

List 是一个必不可少的 python 容器，用于日常编程和 web 开发。了解它的运作是必要的。

让我们看看访问列表最后一个元素的所有不同方式。

**方法#1:天真方法**

可以有两种简单的方法来获取列表的最后一个元素。

*   迭代整个列表，得到倒数第二个元素。
*   反转列表并打印第一个元素。

```py
# Python 3 code to demonstrate 
# accessing last element of list
# using naive method 

# initializing list 
test_list = [1, 4, 5, 6, 3, 5]

# printing original list 
print ("The original list is : " + str(test_list))

# First naive method
# using loop method to print last element 
for i in range(0, len(test_list)):

    if i == (len(test_list)-1):
        print ("The last element of list using loop : "
                                  +  str(test_list[i]))

# Second naive method        
# using reverse method to print last element
test_list.reverse()
print("The last element of list using reverse : "
                            +  str(test_list[0]))
```

**输出:**

```py
The original list is : [1, 4, 5, 6, 3, 5]
The last element of list using loop : 5
The last element of list using reverse : 5

```

**方法 2:使用[]运算符**

如果列表中的元素数量已知，则可以轻松评估最后一个元素。Python 中有两个索引指向列表中最后一个元素。

*   **`list[ len - 1 ]` :** 根据定义指向最后一个元素。
*   **`list[-1]` :** 在 python 中，负索引从末尾开始。

```py
# Python3 code to demonstrate 
# accessing last element of list
# using [] operator

# initializing list 
test_list = [1, 4, 5, 6, 3, 5]

# printing original list 
print ("The original list is : " + str(test_list))

# using len - 1 index to print last list element
print ("The last element using [ len -1 ] is : "
           +  str(test_list[len(test_list) -1]))

# using -1 index to print last list element
print ("The last element using [ -1 ] is : "
                      +  str(test_list[-1]))
```

**输出:**

```py
The original list is : [1, 4, 5, 6, 3, 5]
The last element using [ len -1 ] is : 5
The last element using [ -1 ] is : 5

```

**方法三:使用`list.pop()`**

`list.pop()`方法用于访问列表的最后一个元素。这种方法的缺点是，它还删除了列表的最后一个元素，因此只鼓励在不重用列表时使用。

```py
# Python3 code to demonstrate 
# accessing last element of list
# using list.pop()

# initializing list 
test_list = [1, 4, 5, 6, 3, 5]

# printing original list 
print ("The original list is : " + str(test_list))

# using pop() to print last list element
print ("The last element using pop() is : "
                  +  str(test_list.pop()))
```

**输出:**

```py
The original list is : [1, 4, 5, 6, 3, 5]
The last element using pop() is : 5

```

**方法四:使用`reversed()` + `next()`**

`reversed()`加上`next()`可以很容易地用来获取最后一个元素，就像其中一个幼稚的方法一样，reversed 方法返回列表的逆序作为迭代器，`next()`方法打印下一个元素，在这种情况下是最后一个元素。

```py
# Python3 code to demonstrate 
# accessing last element of list
# using reversed() + next()

# initializing list 
test_list = [1, 4, 5, 6, 3, 5]

# printing original list 
print ("The original list is : " + str(test_list))

# using reversed() + next() to print last element
print ("The last element using reversed() + next() is : "
                        +  str(next(reversed(test_list))))
```

**输出:**

```py
The original list is : [1, 4, 5, 6, 3, 5]
The last element using reversed() + next() is : 5

```