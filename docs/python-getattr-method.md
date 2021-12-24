# Python | getattr()方法

> 原文:[https://www.geeksforgeeks.org/python-getattr-method/](https://www.geeksforgeeks.org/python-getattr-method/)

**Python getattr()** **函数**用于访问对象的属性值，还提供了一个在密钥不可用时执行默认值的选项。

> **语法:** getattr(obj，key，def)
> 
> **参数:**
> 
> *   **obj :** 需要处理属性的对象。
> *   **键:**对象的属性
> *   **def :** 找不到属性需要打印的默认值。
> 
> **如果值可用，则返回:**对象值，如果属性不存在，则返回默认值
> ，如果属性不存在，且未指定默认值
> ，则返回属性错误。

## getattr()在 Python 中的工作原理

### **示例 1:** 演示 getattr()的工作

## 蟒蛇 3

```
# Python code to demonstrate
# working of getattr()

# declaring class
class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object and
# python getattr() function call
obj = GfG()

# use of getattr
print("The name is " + getattr(obj, 'name'))

# use of getattr with default
print("Description is " + getattr(obj,
                                  'description',
                                  'CS Portal'))

# use of getattr without default
print("Motto is " + getattr(obj, 'motto'))
```

**输出:**

```
The name is GeeksforGeeks
Description is CS Portal
```

例外:

```
AttributeError: GfG instance has no attribute 'motto'
```

### **示例 2:** 找不到命名属性时的 getattr()

## 蟒蛇 3

```
# Python code to demonstrate
# working of getattr()

# declaring class
class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object
obj = GfG()

# use of getattr without default
print("Gender is " + getattr(obj, 'gender'))
```

**输出:**

```
AttributeError: 'GfG' object has no attribute 'gender'
```

### 示例 3:性能分析和带参数的 getattr python

## 蟒蛇 3

```
# Python code to demonstrate
# performance analysis of getattr()
import time

# declaring class
class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object
obj = GfG()

# use of getattr to print name
start_getattr = time.time()
print("The name is " + getattr(obj, 'name'))
print("Time to execute getattr " + str(time.time() - start_getattr))

# use of conventional method to print name
start_obj = time.time()
print("The name is " + obj.name)
print("Time to execute conventional method " + str(time.time() - start_obj))
```

**输出:**

```
The name is GeeksforGeeks
Time to execute getattr 5.0067901611328125e-06
The name is GeeksforGeeks
Time to execute conventional method 1.1920928955078125e-06
```

### 示例 4: getattr Python 默认值

## 蟒蛇 3

```
# Python code to demonstrate
# working of getattr()

# declaring class
class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object
obj = GfG()

# use of getattr without default
print("Motto is " + getattr(obj, 'motto'))
```

**输出:**

```
AttributeError: 'GfG' object has no attribute 'motto'
```

### 示例 5: Python getattr()函数调用

## 蟒蛇 3

```
# Python code to demonstrate
# working of getattr()

# declaring class
class GfG:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def call(self, x):
        print(f"{self.name} called with parameters '{x}'")
        return

# initializing object
obj = GfG("Vivek", 10)
print(obj)
print(GfG)
print(getattr(obj,'call'))

getattr(obj,'call')('arg')
```

**输出:**

```
<__main__.GfG object at 0x0000023C1ED92748>
<class '__main__.GfG'>
<bound method GfG.call of <__main__.GfG object at 0x0000023C1ED92748>>
Vivek called with parameters 'arg'
```

**结果:**常规方法比 getattr()花费的时间少，但是当在缺少属性的情况下必须使用默认值时，getattr()是一个不错的选择。

**应用程序:**getattr()有许多应用程序，其中一些已经在缺少对象属性的情况下提到过，在 web 开发中，一些表单属性是可选的。在机器学习特征收集的情况下也很有用，以防某些特征有时在数据收集中丢失。