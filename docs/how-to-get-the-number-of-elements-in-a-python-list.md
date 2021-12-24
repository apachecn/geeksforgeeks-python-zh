# 如何获取 Python 列表中的元素数量？

> 原文:[https://www . geesforgeks . org/如何获取 python 列表中的元素数量/](https://www.geeksforgeeks.org/how-to-get-the-number-of-elements-in-a-python-list/)

在本文中，我们将讨论如何获取 Python 列表中的元素数量。

**示例:**

> **输入:**【1，2，3，4，5】
> 
> **输出:**
> 列表中的元素数量为
> 5
> 
> **输入:**【1.2，4.5，2.2】
> 
> **输出:**
> 列表中的元素数量为
> 3
> 
> **输入:** [“苹果”、“香蕉”、“芒果”]
> 
> **输出:**
> 列表中的元素数量为
> 3

在获取 Python 列表中的元素数量之前，我们必须创建一个空列表。创建一个空列表后，我们必须将项目或元素插入列表。有两种方法可以获得列表中元素的数量，

*   **使用 Len()功能**
*   **用于循环**

### **使用 Len()功能**

我们可以使用 len 函数，即 len()来返回列表中的元素数量

## 蟒蛇 3

```
# Returning the number of elements using
# len() function in python

list = []  # declare empty list
# adding items or elements to the list
list.append(1)
list.append(2)
list.append(3)
list.append(4)

# printing the list
print(list)

# using the len() which return the number
# of elements in the list
print("No of elements in list are")
print(len(list))
```

**Output**

```
[1, 2, 3, 4]
No of elements in list are
4
```

### 用于循环

我们可以使用 for 循环声明一个计数器变量来计算列表中元素的数量，并在循环终止后打印计数器。

## 蟒蛇 3

```
# Python Program for returning the number
# of elements in the list using for loop

list = []  # declaring empty list

# inserting elements in the list using
# append method
list.append(1)
list.append(2)
list.append(3)
list.append(4)

# declaring count variable as integer to keep
# track of the number of elements in for loop
count = 0 

# for loop for iterating through each element
# in the list
for i in list:

    # increments count variable for each
    # iteration
    count = count+1

# prints the count variable i.e the total number
# of elements in the list
print(list)

print("No of elements in the list are")
print(count)
```

**Output**

```
[1, 2, 3, 4]
No of elements in the list are
4
```

因此，通过这种方式，我们可以使用 for 循环返回 python 中列表的元素数量。