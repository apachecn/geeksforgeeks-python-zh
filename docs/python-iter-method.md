# Python iter()方法

> 原文:[https://www.geeksforgeeks.org/python-iter-method/](https://www.geeksforgeeks.org/python-iter-method/)

**python iter()方法**返回迭代器对象，它用于将一个 iterable 转换为迭代器。

> **语法:iter(obj，sentinel)**
> 
> **参数:**
> 
> *   **对象:**必须转换为可迭代的对象(通常是迭代器)。
> *   **标记:**用于表示序列结束的值。
> 
> **返回:**迭代器对象

## 迭代器的性质

*   迭代对象通过内部计数变量记住迭代计数。
*   迭代完成后，它会引发 StopIteration 异常，并且迭代计数不能重新分配为 0。
*   因此，它可以用来遍历容器一次。

## **Python iter()示例**

### **示例 1: Python 迭代列表**

## 蟒蛇 3

```py
# Python3 code to demonstrate
# working of iter()

# initializing list
lis1 = [1, 2, 3, 4, 5]

# printing type
print("The list is of type : " + str(type(lis1)))

# converting list using iter()
lis1 = iter(lis1)

# printing type
print("The iterator is of type : " + str(type(lis1)))

# using next() to print iterator values
print(next(lis1))
print(next(lis1))
print(next(lis1))
print(next(lis1))
print(next(lis1))
```

**输出:**

```py
The list is of type : 
The iterator is of type : 
1
2
3
4
5
```

### 示例 2: Python 使用索引迭代列表

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# property of iter()

# initializing list
lis1 = [1, 2, 3, 4, 5]

# converting list using iter()
lis1 = iter(lis1)

# prints this
print("Values at 1st iteration : ")
for i in range(0, 5):
    print(next(lis1))

# doesn't print this
print("Values at 2nd iteration : ")
for i in range(0, 5):
    print(next(lis1))
```

**输出:**

```py
Values at 1st iteration : 
1
2
3
4
5
Values at 2nd iteration : 
```

例外:

```py
Traceback (most recent call last):
  File "/home/0d0e86c6115170d7cd9083bcef1f22ef.py", line 18, in 
    print (next(lis1))
StopIteration
```