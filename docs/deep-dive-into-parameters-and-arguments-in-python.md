# 深入探究 Python 中的参数和参数

> 原文:[https://www . geeksforgeeks . org/深入探究 python 中的参数和参数/](https://www.geeksforgeeks.org/deep-dive-into-parameters-and-arguments-in-python/)

对于一个参数和一个参数，初露头角的开发人员总会有一点点困惑，本文着重阐明它们之间的区别，帮助您有效地使用它们。

### 参数:

参数是在函数定义过程中在括号内定义的变量。简单地说，它们是在我们声明函数时编写的。

**示例:**

## 蟒蛇 3

```
# Here a,b are the parameters
def sum(a,b):
  print(a+b)

sum(1,2)
```

**输出:**

```
3

```

### **论据:**

参数是调用函数时传递给函数的值。它可能是作为输入传递给函数或方法的变量、值或对象。它们是在我们调用函数时编写的。

**示例:**

## 蟒蛇 3

```
def sum(a,b):
  print(a+b)

# Here the values 1,2 are arguments
sum(1,2)
```

**输出:**

```
3

```

### python 中的参数类型:

Python 函数可以包含两种类型的参数:

*   位置参数
*   关键字参数

#### 位置参数:

需要以适当的顺序包含位置参数，即调用函数时，第一个参数总是排在第一位，第二个参数需要排在第二位，以此类推。

**示例:**

## 蟒蛇 3

```
def person_name(first_name,second_name):
  print(first_name+second_name)

# First name is Ram placed first
# Second name is Babu place second
person_name("Ram","Babu")
```

**输出:**

```
RamBabu

```

#### 关键字参数:

关键字参数是传递给函数或方法的参数，其前面带有关键字和等号。关键字参数相对于另一个关键字参数的顺序并不重要，因为这些值是显式赋值的。

## 蟒蛇 3

```
def person_name(first_name,second_name):
  print(first_name+second_name)

# Here we are explicitly assigning the values 
person_name(second_name="Babu",first_name="Ram")
```

**输出:**

```
RamBabu

```