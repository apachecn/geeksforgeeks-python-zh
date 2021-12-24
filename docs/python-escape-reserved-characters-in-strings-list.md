# Python–转义字符串列表中的保留字符

> 原文:[https://www . geesforgeks . org/python-escape-保留字符串中的字符-列表/](https://www.geeksforgeeks.org/python-escape-reserved-characters-in-strings-list/)

给定字符串列表，转义每个字符串中的保留字符。

> **输入**:test _ list =【“Gf-g”、“be)s(t)”】
> **输出**:【‘Gf \\-g’、‘be \ \)s \ \(t)】
> **解释**:所有保留的字符元素都转义了，通过加双\ \。
> 
> **输入** : test_list = ["Gf-g"]
> **输出** : ['Gf\\-g']
> **解释**:所有保留的字符元素都转义了，通过加双\\。

**方法一:使用 join() +列表理解**

在这种情况下，我们构造字典将每个保留字符映射到它的转义版本，然后执行列表理解中的替换任务，并将结果连接成字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Escape reserved characters in Strings List
# Using list comprehension + join()

# initializing list
test_list = ["Gf-g", "is*", "be)s(t"]

# printing string
print("The original list : " + str(test_list))

# the reserved string
reserved_str = """? & | ! { } [ ] ( ) ^ ~ * : \ " ' + -"""

# the mapped escaped values
esc_dict = { chr : f"\\{chr}" for chr in reserved_str}

# performing transformation using join and list comprehension
res = [ ''.join(esc_dict.get(chr, chr) for chr in sub) for sub in test_list]

# printing results
print("The resultant escaped String : " + str(res))
```

**Output**

```py
The original list : ['Gf-g', 'is*', 'be)s(t']
The resultant escaped String : ['Gf\\-g', 'is\\*', 'be\\)s\\(t']
```

**方法 2:使用 make trans()+translate()+zip()**

在这种情况下，通过使用 zip()和 maketrans()而不是字典进行映射来进行转义。翻译是使用 maketrans()的结果完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Escape reserved characters in Strings List
# Using maketrans() + translate() + zip()

# initializing list
test_list = ["Gf-g", "is*", "be)s(t"]

# printing string
print("The original list : " + str(test_list))

# reserved_chars
reserved_chars = '''?&|!{}[]()^~*:\\"'+-'''

# the escaping logic
mapper = ['\\' + ele for ele in reserved_chars]
result_mapping = str.maketrans(dict(zip(reserved_chars, mapper)))

# reforming result
res = [sub.translate(result_mapping) for sub in test_list]

# printing results
print("The resultant escaped String : " + str(res))
```

**Output**

```py
The original list : ['Gf-g', 'is*', 'be)s(t']
The resultant escaped String : ['Gf\\-g', 'is\\*', 'be\\)s\\(t']
```