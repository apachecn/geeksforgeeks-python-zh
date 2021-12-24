# Python 字典 pop()方法

> 原文:[https://www.geeksforgeeks.org/python-dictionary-pop-method/](https://www.geeksforgeeks.org/python-dictionary-pop-method/)

**Python 字典 pop()** 方法从字典中移除并返回指定的元素。

> **语法:** dict.pop(key，def)
> 
> **参数:**
> 
> *   **键:**其键值对必须被返回和移除的键。
> *   **def :** 指定键不存在时返回的默认值。
> 
> **返回:**与已删除的键值对相关联的值(如果键存在)。
> 如果键不存在，则指定默认值。
> 键错误，如果键不存在且未指定默认值。

## Python 字典 pop()方法示例

### **例 1:从**词典**中弹出一个元素**

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of pop()

# initializing dictionary
test_dict = {"Nikhil": 7, "Akshat": 1, "Akash": 2}

# Printing initial dict
print("The dictionary before deletion : " + str(test_dict))

# using pop to return and remove key-value pair.
pop_ele = test_dict.pop('Akash')

# Printing the value associated to popped key
print("Value associated to poppped key is : " + str(pop_ele))

# Printing dictionary after deletion
print("Dictionary after deletion is : " + str(test_dict))
```

**输出:**

```py
The dictionary before deletion : {'Nikhil': 7, 'Akshat': 1, 'Akash': 2}
Value associated to poppped key is : 2
Dictionary after deletion is : {'Nikhil': 7, 'Akshat': 1}
```

### 示例 2: Python 字典弹出第一个元素

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of pop()

# initializing dictionary
test_dict = {"Nikhil": 7, "Akshat": 1, "Akash": 2}

# Printing initial dict
print("The dictionary before deletion : " + str(test_dict))

# using pop to return and remove key-value pair.
pop_first = test_dict.pop("Nikhil")

# Printing the value associated to popped key
print("Value associated to poppped key is : " + str(pop_first))

# Printing dictionary after deletion
print("Dictionary after deletion is : " + str(test_dict))
```

**输出:**

```py
The dictionary before deletion : {'Nikhil': 7, 'Akshat': 1, 'Akash': 2}
Value associated to poppped key is : 7
Dictionary after deletion is : {'Akshat': 1, 'Akash': 2}
```

### **示例 3:** 弹出字典中不存在的元素

字典中没有该键时，pop()函数的行为是**不同的。**在这种情况下，即使不提供默认值，也会返回默认提供的值或 KeyError。

## 蟒蛇 3

```py
# Python 3 code to demonstrate
# working of pop() without key

# initializing dictionary
test_dict = {"Nikhil": 7, "Akshat": 1, "Akash": 2}

# Printing initial dict
print("The dictionary before deletion : " + str(test_dict))

# using pop to return and remove key-value pair
# provided default
pop_ele = test_dict.pop('Manjeet', 4)

# Printing the value associated to popped key
# Prints 4
print("Value associated to poppped key is : " + str(pop_ele))

# using pop to return and remove key-value pair
# not provided default
pop_ele = test_dict.pop('Manjeet')

# Printing the value associated to popped key
# KeyError
print("Value associated to poppped key is : " + str(pop_ele))
```

**输出:**

```py
The dictionary before deletion : {'Nikhil': 7, 'Akshat': 1, 'Akash': 2}
Value associated to poppped key is : 4
Traceback (most recent call last):
  File "main.py", line 20, in 
    pop_ele = test_dict.pop('Manjeet')
KeyError: 'Manjeet'
```