# Python 字典副本()

> 原文:[https://www.geeksforgeeks.org/python-dictionary-copy/](https://www.geeksforgeeks.org/python-dictionary-copy/)

**Python 字典副本()方法**返回字典的一个**浅副本**。

### **Python** 字典副本()**语法:**

> dict.copy()

### **Python** 字典副本()**参数:**

> copy()方法不接受任何参数。

### **Python** 字典副本()**返回:**

> 这个方法不修改原字典，只返回字典的副本。

## **Python** 字典副本()示例:

```py
Input : original = {1:'geeks', 2:'for'}
        new = original.copy()
Output : original:  {1: 'one', 2: 'two'}
         new:  {1: 'one', 2: 'two'}
```

### **Python** 字典副本()**错误:**

```py
As we are not passing any parameters 
there is no chance of any error.
```

### 示例 1:使用 **Python** 字典副本()

## 蟒蛇 3

```py
# Python program to demonstrate working
# of dictionary copy
original = {1: 'geeks', 2: 'for'}

# copying using copy() function
new = original.copy()

# removing all elements from the list
# Only new list becomes empty as copy()
# does shallow copy.
new.clear()

print('new: ', new)
print('original: ', original)
```

**输出:**

```py
new:  {}
original:  {1: 'geeks', 2: 'for'}
```

### **示例 2:** Python 字典复制()并更新

## 蟒蛇 3

```py
# given dictionary
dict1 = {10: 'a', 20: [1, 2, 3], 30: 'c'}
print("Given Dictionary:", dict1)

# new dictionary and
# copying using copy() method
dict2 = dict1.copy()
print("New copy:", dict2)

# Updating dict2 elements and
# checking the change in dict1
dict2[10] = 10
dict2[20][2] = '45'  # list item updated

print("Updated copy:", dict2)
```

**输出:**

```py
Given Dictionary: {10: 'a', 20: [1, 2, 3], 30: 'c'}
New copy: {10: 'a', 20: [1, 2, 3], 30: 'c'}
Updated copy: {10: 10, 20: [1, 2, '45'], 30: 'c'}
```

## **与简单赋值“=”有何不同？**

与 copy()不同，赋值运算符执行深度复制。

## 蟒蛇 3

```py
# Python program to demonstrate difference
# between = and copy()
original = {1: 'geeks', 2: 'for'}

# copying using copy() function
new = original.copy()

# removing all elements from new list
# and printing both
new.clear()
print('new: ', new)
print('original: ', original)

original = {1: 'one', 2: 'two'}

# copying using =
new = original

# removing all elements from new list
# and printing both
new.clear()
print('new: ', new)
print('original: ', original)
```

**输出:**

```py
new:  {}
original:  {1: 'geeks', 2: 'for'}
new:  {}
original:  {}
```