# 使用 Python 中的运算符重载连接两个字符串

> 原文:[https://www . geesforgeks . org/concatenate-two-string-use-operator-overloading-in-python/](https://www.geeksforgeeks.org/concatenate-two-strings-using-operator-overloading-in-python/)

[**运算符重载**](https://www.geeksforgeeks.org/operator-overloading-in-python/) 是指通过传递不同类型的数据作为参数，使用同一个运算符执行不同的任务。为了理解‘+’运算符在 python 中是如何以两种不同的方式工作的，让我们举下面的例子

## 蟒蛇 3

```
# taking two numbers
a = 2
b = 3

# using '+' operator add them
c = a+b

# printing the result
print("The sum of these two numbers is ", c)
```

**输出:**

```
The sum of these two numbers is  5

```

在本例中，我们使用了“+”运算符来添加数字，现在让我们再举一个例子来了解如何使用“+”运算符来连接字符串。

## 蟒蛇 3

```
# taking two strings from the user
a = 'abc'
b = 'def'

# using '+' operator concatenate them
c = a+b

# printing the result
print("After Concatenation the string becomes", c)
```

**输出:**

```
After Concatenation the string becomes abcdef

```

为了更好地理解运算符重载，这里有一个例子，其中一个**通用方法**用于两个目的。

## 蟒蛇 3

```
# let us define a class with add method
class operatoroverloading:

    def add(self, a, b):
        self.c = a+b
        return self.c

# creating an object of class
obj = operatoroverloading()

# using add method by passing integers
# as argument
result = obj.add(23, 9)
print("sum is", result)

# using same add method by passing strings
# as argument
result = obj.add("23", "9")
print("Concatenated string is", result)
```

**输出:**

```
sum is 32
Concatenated string is 239

```