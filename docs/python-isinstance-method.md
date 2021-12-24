# Python isinstance()方法

> 原文:[https://www.geeksforgeeks.org/python-isinstance-method/](https://www.geeksforgeeks.org/python-isinstance-method/)

**Python isinstance()函数**如果对象是指定的类型，则返回真，如果不匹配，则返回假。

> **语法:** isinstance(obj，class)
> 
> **参数:**
> 
> *   **obj :** 需要作为类的一部分检查的对象。
> *   **类:**类/类型/类或类型的元组，需要对照其检查对象。
> 
> **返回:** True，如果传递了单个类，则对象属于给定的类/类型；如果传递了类/类型的元组，则对象属于任何类/类型，否则返回 False。举起
> 
> **类型错误:**如果不是所提到的有效类类型。

## Python 实例()示例

### **示例 1:** Python 是一个带有 int 和 list 的实例

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of isinstance()
# with native types

# initializing native types
test_int = 5
test_list = [1, 2, 3]

# testing with isinstance
print("Is test_int integer? : " + str(isinstance(test_int, int)))
print("Is test_int string? : " + str(isinstance(test_int, str)))
print("Is test_list integer? : " + str(isinstance(test_list, int)))
print("Is test_list list? : " + str(isinstance(test_list, list)))

# testing with tuple
print("Is test_int integer or list or string? : "
      + str(isinstance(test_int, (list, int))))
```

**输出:**

```py
Is test_int integer? : True
Is test_int string? : False
Is test_list integer? : False
Is test_list list? : True
Is test_int integer or list or string? : True
```

### **示例 2:** 演示将 isinstance()用于对象

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of isinstance()
# with objects

# declaring classes
class gfg1:
    a = 10

# inherited class
class gfg2(gfg1):
    string = 'GeeksforGeeks'

# initializing objects
obj1 = gfg1()
obj2 = gfg2()

# checking instances
print("Is obj1 instance of gfg1? : " + str(isinstance(obj1, gfg1)))
print("Is obj2 instance of gfg2? : " + str(isinstance(obj2, gfg2)))
print("Is obj1 instance of gfg2? : " + str(isinstance(obj1, gfg2)))

# check inheritance case
# return true
print("Is obj2 instance of gfg1? : " + str(isinstance(obj2, gfg1)))
```

**输出:**

```py
Is obj1 instance of gfg1? : True
Is obj2 instance of gfg2? : True
Is obj1 instance of gfg2? : False
Is obj2 instance of gfg1? : True
```

### 示例 3: Python 是一个实例数组

## 蟒蛇 3

```py
test_list = [1, 2, 3]
print ("Is test_list list? : " + str(isinstance(test_list, list)))
```

**输出:**

```py
Is test_list list? : True
```

### 示例 4: Python 是一个实例字符串

## 蟒蛇 3

```py
test_str = "GeeksforGeeks"
print ("Is test_str string? : " + str(isinstance(test_str, str)))
```

**输出:**

```py
Is test_str string? : True
```

### 示例 4: Python 是一个实例字典

## 蟒蛇 3

```py
test_dict = {"apple" : 1, "Ball" : 2 }
print ("Is test_str dictionary? : " + str(isinstance(test_dict, dict)))
```

**输出:**

```py
Is test_str dictionary? : True
```

### 示例 4: Python 是静态类方法

## 计算机编程语言

```py
class geeks:
    course = 'DSA'

    def purchase(obj):
        return obj.course

geeks.purchase = classmethod(geeks.purchase)
str(isinstance(geeks.purchase(), str ))
```

**输出:**

```py
True
```