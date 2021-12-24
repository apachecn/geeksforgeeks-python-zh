# 用 Python 迭代字典

> 原文:[https://www . geesforgeks . org/iterate-over-a-in-dictionary-in-python/](https://www.geeksforgeeks.org/iterate-over-a-dictionary-in-python/)

Python 中的 Dictionary 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存`key:value`对。

在 Python 中，有多种方法可以迭代字典。

*   遍历所有键
*   遍历所有值
*   遍历所有键、值对

**遍历所有键:**

下面代码中的状态顺序每次都会改变，因为字典没有以特定的顺序存储键。

```py
# Python3 code to iterate through all keys in a dictionary

statesAndCapitals = {
                     'Gujarat' : 'Gandhinagar',
                     'Maharashtra' : 'Mumbai',
                     'Rajasthan' : 'Jaipur',
                     'Bihar' : 'Patna'
                    }

print('List Of given states:\n')

# Iterating over keys
for state in statesAndCapitals:
    print(state)
```

**Output:**

```py
List Of given states:

Rajasthan
Bihar
Maharashtra
Gujarat

```

为了保持字典中键和值的顺序，请使用 OrderedDict。

```py
# Python3 code to iterate through all keys 
# in a dictionary in a specific order

from collections import OrderedDict

statesAndCapitals = OrderedDict([
                                 ('Gujarat', 'Gandhinagar'),
                                 ('Maharashtra', 'Mumbai'),
                                 ('Rajasthan', 'Jaipur'),
                                 ('Bihar', 'Patna')
                                ])

print('List Of given states:\n')

# Iterating over keys
for state in statesAndCapitals:
    print(state)
```

**Output:**

```py
List Of given states:

Gujarat
Maharashtra
Rajasthan
Bihar

```

上面的字典是一个 *OrderedDict* ，因为键和值是按照字典中定义的顺序存储的。因此，当我们想要维护存储在字典中的(键、值)的顺序时，应该使用上面的方法。

**迭代所有值:**

同样，在这种情况下，下面代码中大写字母的打印顺序每次都会改变，因为字典没有以特定的顺序存储它们。

```py
# Python3 code to iterate through all values in a dictionary

statesAndCapitals = {
                     'Gujarat' : 'Gandhinagar',
                     'Maharashtra' : 'Mumbai',
                     'Rajasthan' : 'Jaipur',
                     'Bihar' : 'Patna'
                    }

print('List Of given capitals:\n')

# Iterating over values
for capital in statesAndCapitals.values():
    print(capital)
```

**Output:**

```py
List Of given capitals:

Gandhinagar
Jaipur
Mumbai
Patna

```

**遍历所有键、值对:**

```py
# Python3 code to iterate through all key, value 
# pairs in a dictionary

statesAndCapitals = {
                     'Gujarat' : 'Gandhinagar',
                     'Maharashtra' : 'Mumbai',
                     'Rajasthan' : 'Jaipur',
                     'Bihar' : 'Patna'
                    }

print('List Of given states and their capitals:\n')

# Iterating over values
for state, capital in statesAndCapitals.items():
    print(state, ":", capital)
```

**Output:**

```py
List Of given states and their capitals:

Bihar : Patna
Gujarat : Gandhinagar
Rajasthan : Jaipur
Maharashtra : Mumbai

```