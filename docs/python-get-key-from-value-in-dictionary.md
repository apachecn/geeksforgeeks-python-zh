# Python |从字典中的值获取关键字

> 原文:[https://www . geesforgeks . org/python-从字典中的值获取密钥/](https://www.geeksforgeeks.org/python-get-key-from-value-in-dictionary/)

让我们看看如何在 Python 字典中通过值来获取密钥。

**方法 1:** 使用 list.index()

index()方法返回列表中相应值的索引。下面是一个如何使用 index()方法使用值获取字典键的实现。

## 蟒蛇 3

```py
# creating a new dictionary
my_dict ={"java":100, "python":112, "c":11}

# list out keys and values separately
key_list = list(my_dict.keys())
val_list = list(my_dict.values())

# print key with val 100
position = val_list.index(100)
print(key_list[position])

# print key with val 112
position = val_list.index(112)
print(key_list[position])

# one-liner
print(list(my_dict.keys())[list(my_dict.values()).index(112)])
```

**Output:** 

```py
java
python
python
```

**解释:**
这里使用的方法是找到键和值的两个独立列表。然后使用 val_list 中值的**位置** **获取钥匙。因为键列表中任何位置 N 的键在值列表中的位置 N 都有相应的值。** 

**方法#2:** 使用 dict.item()
我们还可以通过匹配所有值从一个值中获取密钥，然后将对应的密钥打印到给定值。

## 蟒蛇 3

```py
# function to return key for any value
def get_key(val):
    for key, value in my_dict.items():
         if val == value:
             return key

    return "key doesn't exist"

# Driver Code

my_dict ={"java":100, "python":112, "c":11}

print(get_key(100))
print(get_key(11))
```

**Output:** 

```py
java
c
```