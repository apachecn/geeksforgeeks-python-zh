# Python 假关键词

> 原文:[https://www.geeksforgeeks.org/python-false-keyword/](https://www.geeksforgeeks.org/python-false-keyword/)

一个布尔表达式产生两个值(真，假)与此类似，一个布尔变量也可以赋值(真，假)。这里，False 关键字表示将导致不为真的表达式。

### **例 1 :**

首先在这个例子中，我们将给出一个布尔表达式，其结果为假(10 < 6)。接下来，我们将 False 关键字直接分配给 if 语句。

## 蟒蛇 3

```py
# 10 < 6 is a boolean expression
# which evaluates to False
if(10 < 6):
    print("it is True")
else:
    print("it is False")

# here we directly assigned False
# keyword to if statement
if(False):
    print("it is True")
else:
    print("it is False")
```

**Output**

```py
it is False
it is False
```

### **例 2 :**

在这个例子中，我们将布尔表达式 **(5 > 10** )分配给变量 **gfg_flag** ，然后我们将打印该变量以显示分配给它的值，即 False Keyword。接下来，我们将尝试在 if 语句中使用这个变量，这将导致执行 else 块。

## 蟒蛇 3

```py
# here we assigned the boolean expression to variable
# and the value will be False
gfg_flag = 5 > 10

# printing the variable value
print(gfg_flag)

# now we will be using this variable
if(gfg_flag):
    print("it is True")
else:
    print("it is False")
```

**Output**

```py
False
it is False
```