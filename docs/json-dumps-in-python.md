# Python 中的 json.dumps()

> 原文:[https://www.geeksforgeeks.org/json-dumps-in-python/](https://www.geeksforgeeks.org/json-dumps-in-python/)

JSON 的完整形式是 JavaScript 对象符号。这意味着由编程语言中的文本组成的脚本(可执行)文件用于存储和传输数据。Python 通过一个名为 json 的内置包支持 JSON。为了使用这个特性，我们在 Python 脚本中导入 json 包。JSON 中的文本是通过带引号的字符串完成的，该字符串包含{ }内键值映射中的值。它类似于 Python 中的字典。
**注:**更多信息请参考[用 Python 读写解析 JSON](https://www.geeksforgeeks.org/read-write-and-parse-json-using-python/)T5】

## Json.dumps()

json.dumps()函数将 Python 对象转换为 json 字符串。

> **语法:**
> json.dumps(obj，* skipkeys = False，确保 _ascii=True，check_circular=True，allow_nan=True，cls=None，缩进=None，分隔符=None，默认值=None，sort _ keys = False，**kw)
> **参数:**
> **obj:** 将 obj 序列化为 json 格式的流
> **skipkeys:** 如果 skipkeys 为 True(默认值:False)，则 dict
> **保证 _ascii:** 如果保证 _ascii 为真(默认)，输出保证所有传入的非 ascii 字符都被转义。如果 confirm _ ascii 为 false，这些字符将按原样输出。
> **check_circular :** 如果 check_circular 为 false(默认值:True)，则将跳过容器类型的循环引用检查，循环引用将导致 OverflowError(或更糟)。
> **allow_nan :** 如果 allow_nan 为 false(默认值:True)，那么严格按照 JSON 规范序列化超范围浮点值(nan，inf，-inf)将是一个 ValueError。如果 allow_nan 为真，将使用它们的等效 JavaScript，Infinity，-Infinity)。
> **缩进:**如果缩进是一个非负整数或字符串，那么 JSON 数组元素和对象成员将被漂亮地打印出该缩进级别。缩进量为 0、负数或""时只会插入新行。无(默认值)选择最紧凑的表示。使用正整数缩进，每级缩进许多空格。如果缩进是一个字符串(如“\t”)，则该字符串用于缩进每个级别。
> **分隔符:**如果指定，分隔符应为(item_separator，key_separator)元组。如果缩进为无，默认值为('，'，': ')，否则为('，'，':')。为了获得最紧凑的 JSON 表示，您应该指定('，'，':')来消除空白。
> **默认值:**如果指定，默认值应该是为无法序列化的对象调用的函数。它应该返回对象的 JSON 可编码版本，或者引发类型错误。如果未指定，将引发类型错误。
> **sort_keys :** 如果 sort_keys 为真(默认值:False)，则字典的输出将按键排序。

**示例#1:** 将 Python 字典传递给 json.dumps()函数将返回一个字符串。

## 蟒蛇 3

```
import json

# Creating a dictionary
Dictionary ={1:'Welcome', 2:'to',
            3:'Geeks', 4:'for',
            5:'Geeks'}

# Converts input dictionary into
# string and stores it in json_string
json_string = json.dumps(Dictionary)
print('Equivalent json string of input dictionary:',
      json_string)
print("        ")

# Checking type of object
# returned by json.dumps
print(type(json_string))
```

**输出**T2】

> 字典的等效 json 字符串:{“1”:“欢迎”、“2”:“to”、“3”:“Geeks”、“4”:“for”、“5”:“Geeks”}
> <类“str”>

**示例#2:** 通过将 skipkeys 设置为 True(默认值:False)，我们自动跳过非基本类型的键。

## 蟒蛇 3

```
import json

Dictionary ={(1, 2, 3):'Welcome', 2:'to',
            3:'Geeks', 4:'for',
            5:'Geeks'}

# Our dictionary contains tuple
# as key, so it is automatically
# skipped If we have not set
# skipkeys = True then the code
# throws the error
json_string = json.dumps(Dictionary,
                         skipkeys = True)

print('Equivalent json string of dictionary:',
      json_string)
```

**输出**T2】

> 字典的等效 json 字符串:{“2”:“to”、“3”:“Geeks”、“4”:“for”、“5”:“Geeks”}

**例 3:**

## 蟒蛇 3

```
import json

# We are adding nan values
# (out of range float values)
# in dictionary
Dictionary ={(1, 2, 3):'Welcome', 2:'to',
            3:'Geeks', 4:'for',
            5:'Geeks', 6:float('nan')}

# If we hadn't set allow_nan to
# true we would have got
# ValueError: Out of range float
# values are not JSON compliant
json_string = json.dumps(Dictionary,
                         skipkeys = True,
                         allow_nan = True)

print('Equivalent json string of dictionary:',
      json_string)
```

**输出:**

> 字典的等效 json 字符串:{“2”:“to”、“3”:“Geeks”、“4”:“for”、“5”:“Geeks”、“6”:NaN }

**例 4:**

## 蟒蛇 3

```
import json

Dictionary ={(1, 2, 3):'Welcome', 2:'to',
            3:'Geeks', 4:'for',
            5:'Geeks', 6:float('nan')}

# Indentation can be used
# for pretty-printing
json_string = json.dumps(Dictionary,
                         skipkeys = True,
                         allow_nan = True,
                         indent = 6)

print('Equivalent json string of dictionary:',
      json_string)
```

**输出:**

```
Equivalent json string of dictionary: {
      "2": "to",
      "3": "Geeks",
      "4": "for",
      "5": "Geeks",
      "6": NaN
}
```

**例 5:**

## 蟒蛇 3

```
import json

Dictionary ={(1, 2, 3):'Welcome', 2:'to',
            3:'Geeks', 4:'for',
            5:'Geeks', 6:float('nan')}

# If specified, separators should be
# an (item_separator, key_separator)tuple
# Items are separated by '.' and key,
# values are separated by '='
json_string = json.dumps(Dictionary,
                         skipkeys = True,
                         allow_nan = True,
                         indent = 6,
                         separators =(". ", " = "))

print('Equivalent json string of dictionary:',
      json_string)
```

**输出:**

```
Equivalent json string of dictionary: {
      "2" = "to". 
      "3" = "Geeks". 
      "4" = "for". 
      "5" = "Geeks". 
      "6" = NaN
}
```

**例 6:**

## 蟒蛇 3

```
import json

Dictionary ={'c':'Welcome', 'b':'to',
            'a':'Geeks'}

json_string = json.dumps(Dictionary,
                         indent = 6,
                         separators =(". ", " = "),
                         sort_keys = True)

print('Equivalent json string of dictionary:',
      json_string)
```

**输出:**

```
Equivalent json string of dictionary: {
      "a" = "Geeks". 
      "b" = "to". 
      "c" = "Welcome"
}
```