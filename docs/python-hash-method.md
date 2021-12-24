# Python hash()方法

> 原文:[https://www.geeksforgeeks.org/python-hash-method/](https://www.geeksforgeeks.org/python-hash-method/)

**Python hash()函数**是一个内置函数，如果对象有哈希值，则返回该对象的哈希值。哈希值是一个整数，用于在查看字典时快速比较字典键。

### **Python hash()方法语法:**

> **语法:**杂凑(obj)
> 
> **参数:obj :** 我们需要转换成 hash 的对象。
> 
> **返回:**如果可能，返回散列值。

## hash()函数的属性

*   使用 hash()散列的对象是不可逆的，会导致信息丢失。
*   hash()只为不可变对象返回哈希值，因此可以用作检查可变/不可变对象的指示器。

## Python 哈希()方法示例

### **示例 1:** 演示哈希()的工作原理

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of hash()

# initializing objects
int_val = 4
str_val = 'GeeksforGeeks'
flt_val = 24.56

# Printing the hash values.
# Notice Integer value doesn't change
# You'l have answer later in article.
print("The integer hash value is : " + str(hash(int_val)))
print("The string hash value is : " + str(hash(str_val)))
print("The float hash value is : " + str(hash(flt_val)))
```

**输出:**

```py
The integer hash value is : 4
The string hash value is : -5570917502994512005
The float hash value is : 1291272085159665688
```

### **示例 2:** 演示哈希()的属性

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# property of hash()

# initializing objects
# tuple are immutable
tuple_val = (1, 2, 3, 4, 5)

# list are mutable
list_val = [1, 2, 3, 4, 5]

# Printing the hash values.
# Notice exception when trying
# to convert mutable object
print("The tuple hash value is : " + str(hash(tuple_val)))
print("The list hash value is : " + str(hash(list_val)))
```

**输出:**

```py
The tuple hash value is : 8315274433719620810
```

**异常:**

```py
Traceback (most recent call last):
  File "/home/eb7e39084e3d151114ce5ed3e43babb8.py", line 15, in 
    print ("The list hash value is : " + str(hash(list_val)))
TypeError: unhashable type: 'list'
```

### **示例 3:不可变元组对象的 hash()**

## 蟒蛇 3

```py
# hash() for immutable tuple object
var = ('G','E','E','K')

print(hash(var))
```

**输出:**

```py
5434435027328283763
```

### **示例 4:在**可变对象**上散列()**

在不可变对象上使用的 hash()方法，如果我们在像 list、set、dictionaries 这样的可变对象上使用这个方法，那么它会产生一个错误。

## 蟒蛇 3

```py
l = [1, 2, 3, 4]
print(hash(l))
```

**输出:**

```py
TypeError: unhashable type: 'list'
```

### 示例 5:自定义对象上的哈希()

这里我们将重写 __hash()__ 方法来调用 hash()，而 __eq__()方法将检查两个自定义对象的相等性。

## 蟒蛇 3

```py
class Emp:
    def __init__(self, emp_name, id):
        self.emp_name = emp_name
        self.id = id

    def __eq__(self, other):

        # Equality Comparison between two objects
        return self.emp_name == other.emp_name and self.id == other.id

    def __hash__(self):

        # hash(custom_object)
        return hash((self.emp_name, self.id))

emp = Emp('Ragav', 12)
print("The hash is: %d" % hash(emp))

# We'll check if two objects with the same
# attribute values have the same hash
emp_copy = Emp('Ragav', 12)
print("The hash is: %d" % hash(emp_copy))
```

**输出:**

```py
The hash is: -674930604243231063
The hash is: -674930604243231063
```