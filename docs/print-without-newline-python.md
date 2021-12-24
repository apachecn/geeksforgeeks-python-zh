# Python 中没有换行符怎么打印？

> 原文:[https://www.geeksforgeeks.org/print-without-newline-python/](https://www.geeksforgeeks.org/print-without-newline-python/)

一般来说，从 C/C++切换到 python 的人会想，如何打印两个或更多的变量或语句，而不进入 Python 中的新行。因为默认情况下 python print()函数以换行符结束。Python 有一个预定义的格式，如果你使用 print(a_variable)，那么它会**自动转到下一行。**

**例如:**

## 蟒蛇 3

```py
print("geeks")
print("geeksforgeeks")
```

会导致这样的结果:

```py
geeks
geeksforgeeks
```

但有时可能会发生这样的情况，我们不想进入下一行，而是想在同一行打印。那么我们能做什么呢？

**例如:**

```py
Input : print("geeks") print("geeksforgeeks")
Output : geeks geeksforgeeks

Input : a = [1, 2, 3, 4]
Output : 1 2 3 4 
```

这里讨论的解决方案完全取决于您使用的 python 版本。

### **Python 2 . x 中无换行符打印**

## 大蟒

```py
# Python 2 code for printing
# on the same line printing
# geeks and geeksforgeeks
# in the same line

print("geeks"),
print("geeksforgeeks")

# array
a = [1, 2, 3, 4]

# printing a element in same
# line
for i in range(4):
    print(a[i]),
```

**输出:**

```py
geeks geeksforgeeks
1 2 3 4
```

### **Python 3 . x 中无换行符打印**

## 蟒蛇 3

```py
# Python 3 code for printing
# on the same line printing
# geeks and geeksforgeeks
# in the same line

print("geeks", end =" ")
print("geeksforgeeks")

# array
a = [1, 2, 3, 4]

# printing a element in same
# line
for i in range(4):
    print(a[i], end =" ")
```

**输出:**

```py
geeks geeksforgeeks
1 2 3 4
```

### **在 Python 3.x 中打印无换行符，不使用 for 循环**

## 蟒蛇 3

```py
# Print without newline in Python 3.x without using for loop

l=[1,2,3,4,5,6]

# using * symbol prints the list
# elements in a single line
print(*l)

#This code is contributed by anuragsingh1022
```

**输出:**

```py
1 2 3 4 5 6
```