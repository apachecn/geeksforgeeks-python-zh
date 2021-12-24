# Python |两个列表的区别

> 原文:[https://www.geeksforgeeks.org/python-difference-two-lists/](https://www.geeksforgeeks.org/python-difference-two-lists/)

有多种方法可以生成两个列表之间的差异。在本文中，我们将看到实现这一点的两种最重要的方法。一种是使用 set()方法，另一种是不使用它。

**示例:**

```
Input :
list1 = [10, 15, 20, 25, 30, 35, 40]
list2 = [25, 40, 35] 
Output :
[10, 20, 30, 15]
Explanation:
resultant list = list1 - list2

```

> **注意:**当你有多个相同的元素时，这将不起作用。在这种情况下，这段代码将简单地移除相同的元素。
> 在这种情况下，您可以维护两个列表中每个元素的计数。

### **通过使用 set():**

在这种方法中，我们显式地将列表转换成集合，然后使用减法运算符简单地从一个集合中减去另一个集合。关于器械包的更多参考，请访问 Python 中的[器械包](https://www.geeksforgeeks.org/sets-in-python/)。

**示例:**

## 蟒蛇 3

```
# Python code t get difference of two lists
# Using set()
def Diff(li1, li2):
    return list(set(li1) - set(li2)) + list(set(li2) - set(li1))

# Driver Code
li1 = [10, 15, 20, 25, 30, 35, 40]
li2 = [25, 40, 35]
print(Diff(li1, li2))
```

**输出:**

```
[10, 20, 30, 15]
```

### **不使用 set():**

在这个方法中，我们使用基本的组合技术从两个列表中复制元素，并定期检查一个是否存在于另一个中。

**示例:**

## 蟒蛇 3

```
# Python code t get difference of two lists
# Not using set()
def Diff(li1, li2):
    li_dif = [i for i in li1 + li2 if i not in li1 or i not in li2]
    return li_dif

# Driver Code
li1 = [10, 15, 20, 25, 30, 35, 40]
li2 = [25, 40, 35]
li3 = Diff(li1, li2)
print(li3)
```

**输出:**

```
[10, 20, 30, 15]
```