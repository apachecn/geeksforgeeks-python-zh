# 使用字典 Get()方法结合 Python 中的相似字符

> 原文:[https://www . geesforgeks . org/combine-相似字符-in-python-use-dictionary-get-method/](https://www.geeksforgeeks.org/combine-similar-characters-in-python-using-dictionary-get-method/)

让我们看看如何在列表中组合相似的字符。

**示例:**

> **输入:** ['g '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' g '，' e '，' e '，' k '，' s']
> **输出:** ['gg '，' eeee '，' kk '，' ss '，' f '，' o '，' r']

我们将使用`dictionary`课的`[get()](https://www.geeksforgeeks.org/get-method-dictionaries-python/)`方法。

## dictionary.get()

`get()`方法用指定的键返回项目的值。

> **语法:**字典. get(键名，值)
> 参数:
> 
> *   **关键字名称:**字典项目的关键字名称。
> *   **值:**(可选)如果指定的键不存在，则返回一个值。
> 
> **返回:**具有指定键的项目的值

**算法:**

1.  宣布名单。
2.  申报字典。
3.  使用`get()`方法遍历列表，如果找到一个新的键，则值 0 被赋给它，1 被加上，最终值为 1。否则，如果重复该键，则将 1 添加到先前计算的值中。这样，现在每个键都有一个赋值，并且记录所有字符的频率。
4.  分离所有键和值，并将其存储在两个不同的列表中。
5.  使用`zip()`功能在结果列表中存储键的乘积及其各自的值。
6.  显示结果。

**例 1 :**

```py
# declaring the list of characters
mylist = ['g', 'e', 'e', 'k', 's', 'f', 
          'o', 'r', 'g', 'e', 'e', 'k', 's'] 

# declaring the dictionary
dictionary = {} 

# counting the frequency of the keys
for key in mylist: 
    dictionary[key] = dictionary.get(key, 0) + 1

# storing the of keys and values
k = list(dictionary.keys())
v = list(dictionary.values())

# declaring the result list
result = []

# storing the product of keys and 
# their respective values in result
for i, j in zip(k, v):
    result.append(i * j)

# displaying the result
print(result)
```

**输出:**

```py
['gg', 'eeee', 'kk', 'ss', 'f', 'o', 'r']
```

**例 2 :**

```py
# declaring the list of characters
mylist = ['p', 'y', 't', 'h', 'o', 'n', 't', 
          'u', 't', 'o', 'r', 'i', 'a', 'l']

# declaring the dictionary
dictionary = {} 

# counting the frequency of the keys
for key in mylist: 
    dictionary[key] = dictionary.get(key, 0) + 1

# storing the of keys and values
k = list(dictionary.keys())
v = list(dictionary.values())

# declaring the reslt list
result = []

# storing the product of keys and 
# their respective values in result
for i, j in zip(k, v):
    result.append(i * j)

# displaying the result
print(result)
```

**输出:**

```py
['a', 'h', 'i', 'l', 'n', 'oo', 'p', 'r', 'ttt', 'u', 'y']
```