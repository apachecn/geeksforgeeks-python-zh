# Python hasattr()方法

> 原文:[https://www.geeksforgeeks.org/python-hasattr-method/](https://www.geeksforgeeks.org/python-hasattr-method/)

**Python hasattr()函数**是一个内置的实用函数，用于检查对象是否具有给定的命名属性，如果存在则返回 true，否则返回 false。

**hasattr()方法的语法为:**

> **语法:**有一个 ttr(obj，key)
> 
> **参数:**
> 
> *   **对象:**必须检查其哪个属性的对象。
> *   **键:**需要检查的属性。
> 
> **返回:**返回真，如果属性存在，否则返回假。

## Python hasattr()方法示例:

### **例 1:工作温度为()**

## 蟒蛇 3

```py
# Python code to demonstrate
# working of hasattr()

# declaring class

class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object
obj = GfG()

# using hasattr() to check name
print("Does name exist ? " + str(hasattr(obj, 'name')))

# using hasattr() to check motto
print("Does motto exist ? " + str(hasattr(obj, 'motto')))
```

**输出:**

```py
Does name exist ? True
Does motto exist ? False
```

### 示例 hasattr()方法和 try 语句之间的性能分析

## 蟒蛇 3

```py
# Python code to demonstrate
# performance analysis of hasattr()
import time

# declaring class
class GfG:
    name = "GeeksforGeeks"
    age = 24

# initializing object
obj = GfG()

# use of hasattr to check motto
start_hasattr = time.time()
if(hasattr(obj, 'motto')):
    print("Motto is there")
else:
    print("No Motto")

print("Time to execute hasattr : " + str(time.time() - start_hasattr))

# use of try/except to check motto
start_try = time.time()
try:
    print(obj.motto)
    print("Motto is there")
except AttributeError:
    print("No Motto")
print("Time to execute try : " + str(time.time() - start_try))
```

**输出:**

```py
No Motto
Time to execute hasattr : 5.245208740234375e-06
No Motto
Time to execute try : 2.6226043701171875e-06
```

**结果:**常规 try/except 比 hasattr()花费的时间少，但是为了代码的可读性，hasattr()总是更好的选择。

**应用:**该功能可用于检查按键，避免在访问缺席按键时出现不必要的错误。hasattr()的链接有时用于避免在一个关联属性不存在的情况下输入另一个关联属性。