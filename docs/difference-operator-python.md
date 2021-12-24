# Python 中==和 is 运算符的区别

> 原文:[https://www.geeksforgeeks.org/difference-operator-python/](https://www.geeksforgeeks.org/difference-operator-python/)

等式运算符(==) 比较两个操作数的值，并检查值是否相等。而**是** 运算符检查两个操作数是否指向同一个对象(存在于同一个内存位置)。

## 蟒蛇 3

```py
# python3 code to
# illustrate the
# difference between
# == and is operator
# [] is an empty list
list1 = []
list2 = []
list3=list1

if (list1 == list2):
    print("True")
else:
    print("False")

if (list1 is list2):
    print("True")
else:
    print("False")

if (list1 is list3):
    print("True")
else:   
    print("False")

list3 = list3 + list2

if (list1 is list3):
    print("True")
else:   
    print("False")
```

**输出:**

```py
True
False
True
False
```

*   如果条件为“真”，则**首先输出，因为列表 1 和列表 2 都是空列表。**
*   **秒**、**如果**条件显示“假”，因为两个空列表在不同的内存位置。因此，列表 1 和列表 2 引用不同的对象。我们可以用 python 中的 **id()** 函数来检查它，该函数返回一个对象的“身份”。
*   如果条件为“真”，则第三个**的输出为“真”，因为列表 1 和列表 3 都指向同一对象。**
*   如果条件为“假”，则第四个**的输出为“假”，因为两个列表的串联总是产生一个新列表。**

## 蟒蛇 3

```py
list1 = []
list2 = []

print(id(list1))
print(id(list2))
```

**输出:**

```py
139877155242696
139877155253640
```

这表明列表 1 和列表 2 引用不同的对象。