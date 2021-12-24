# Python 字典 fromkeys()方法

> 原文:[https://www . geesforgeks . org/python-dictionary-from keys-method/](https://www.geeksforgeeks.org/python-dictionary-fromkeys-method/)

**Python 字典 fromkeys()函数**返回带有映射键和特定值的字典。它根据给定的序列创建一个具有特定值的新字典。

> **语法:**from key(seq，val)
> 
> **参数:**
> 
> *   **序列:**要转换成字典的序列。
> *   **val :** 需要分配给生成的密钥的初始值。默认为无。
> 
> **返回:**如果没有提供值，则键映射到无的字典，否则映射到字段中提供的值。

## Python 字典 fromkeys()方法示例

### **示例 1:** 演示 fromkeys()的工作原理

## 蟒蛇 3

```
# Python 3 code to demonstrate
# working of fromkeys()

# initializing sequence
seq = {'a', 'b', 'c', 'd', 'e'}

# using fromkeys() to convert sequence to dict
# initializing with None
res_dict = dict.fromkeys(seq)

# Printing created dict
print("The newly created dict with None values : " + str(res_dict))

# using fromkeys() to convert sequence to dict
# initializing with 1
res_dict2 = dict.fromkeys(seq, 1)

# Printing created dict
print("The newly created dict with 1 as value : " + str(res_dict2))
```

**输出:**

> 新创建的无值字典:{'d ':无，' a ':无，' b ':无，' c ':无，' e ':无}
> 新创建的以 1 为值的字典:{'d': 1，' a': 1，' b': 1，' c': 1，' e': 1}

## 以可变对象为值的 fromdict()的行为

**fromdict()也可以提供可变对象作为默认值。但是在这种情况下，字典会进行深度复制，也就是说，如果我们在原始列表中追加值，则追加会发生在所有键的值中。**

****预防:**可以使用某些字典理解技术来创建一个新的列表作为键值，而不是将原始列表指向键值。**

### ****示例 2:** 演示可变对象的行为**

## **蟒蛇 3**

```
# Python 3 code to demonstrate
# behaviour with mutable objects

# initializing sequence and list
seq = {'a', 'b', 'c', 'd', 'e'}
lis1 = [2, 3]

# using fromkeys() to convert sequence to dict
# using conventional method
res_dict = dict.fromkeys(seq, lis1)

# Printing created dict
print("The newly created dict with list values : "
      + str(res_dict))

# appending to lis1
lis1.append(4)

# Printing dict after appending
# Notice that append takes place in all values
print("The dict with list values after appending : "
      + str(res_dict))

lis1 = [2, 3]
print('\n')

# using fromkeys() to convert sequence to dict
# using dict. comprehension
res_dict2 = {key: list(lis1) for key in seq}

# Printing created dict
print("The newly created dict with list values : "
      + str(res_dict2))

# appending to lis1
lis1.append(4)

# Printing dict after appending
# Notice that append doesnt take place now.
print("The dict with list values after appending (no change) : "
      + str(res_dict2))
```

****输出:****

> **新创建的带有列表值的 dict:{ ' d ':[2，3]，' e': [2，3]，' c': [2，3]，' a': [2，3]，' b': [2，3]}
> 追加后带有列表值的 dict:{ ' d ':[2，3，4]，' e': [2，3，4]，' c': [2，3，4]，' a': [2，3，4]，' b': [2，3，4]}
> 3]}
> 追加后有列表值的字典(无变化):{'d': [2，3]，' e': [2，3]，' c': [2，3]，' a': [2，3]，' b': [2，3]}**

### **示例 3: Python 字典 fromkeys()默认值**

## **蟒蛇 3**

```
x = ('key1', 'key2', 'key3')
y = 0

d = dict.fromkeys(x, y)

print(d)
```

****输出:****

```
{'key1': 0, 'key2': 0, 'key3': 0}
```

### **示例 4:带空列表的 Python 字典 fromkeys()**

## **蟒蛇 3**

```
# Python3 code to demonstrate
# to initialize dictionary with list
# using fromkeys()

# using fromkeys() to construct
new_dict = dict.fromkeys(range(4), [])

# printing result
print ("New dictionary with empty lists as keys : " + str(new_dict))
```

****输出:****

```
New dictionary with empty lists as keys : {0: [], 1: [], 2: [], 3: []}
```