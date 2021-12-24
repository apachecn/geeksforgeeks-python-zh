# Python 字典| values()

> 原文:[https://www.geeksforgeeks.org/python-dictionary-values/](https://www.geeksforgeeks.org/python-dictionary-values/)

**values()** 是 Python 编程语言中的一个内置方法，返回一个 view 对象。视图对象以列表的形式包含字典的值。如果对返回值使用 type()方法，将得到“dict_values 对象”。必须对其进行强制转换才能获得实际列表。

**语法:**

```py
dictionary_name.values()
```

**参数:**
没有参数

**返回:**

```py
returns a list of all the values available in a given dictionary.
the values have been stored in a reversed manner.
```

**错误:**

```py
As we are not passing any parameters there
is no scope for any error.
```

**代码#1:**

```py
# Python3 program for illustration 
# of values() method of dictionary 

# numerical values
dictionary = {"raj": 2, "striver": 3, "vikram": 4}
print(dictionary.values())  

# string values
dictionary = {"geeks": "5", "for": "3", "Geeks": "5"}
print(dictionary.values())  
```

**输出:**

```py
dict_values([2, 3, 4])
dict_values(['5', '3', '5'])

```

**实际应用:**
给定姓名和工资，返回所有员工的工资总额。

**代码#2:**

```py
# Python3 program for illustration 
# of values() method in finding total salary

# stores name and corresponding salaries
salary = {"raj" : 50000, "striver" : 60000, "vikram" : 5000} 

# stores the salaries only
list1 = salary.values() 
print(sum(list1))  # prints the sum of all salaries
```

**输出:**

```py
115000

```