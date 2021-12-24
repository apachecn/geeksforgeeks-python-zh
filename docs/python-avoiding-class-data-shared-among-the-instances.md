# Python |避免实例间共享类数据

> 原文:[https://www . geesforgeks . org/python-避免类数据-实例间共享/](https://www.geeksforgeeks.org/python-avoiding-class-data-shared-among-the-instances/)

类属性属于类本身，它们将由所有实例共享，因此包含每个实例的相同值。这样的属性通常在类主体部分的顶部定义，以便于阅读。

假设我们有以下代码片段:

## python 3

```
# Python code to demonstrate
# the working of the sharing
# of data variables

# Creating a class
class Geek_Class:
    geek = []

x = Geek_Class()
y = Geek_Class()

# Appending the values
x.geek.append(1)
y.geek.append(2)
x.geek.append(3)
y.geek.append(4)

# Printing the values for x and y
print(x.geek)
print(y.geek)
```

**输出:**

```
[1, 2, 3, 4]
[1, 2, 3, 4]
```