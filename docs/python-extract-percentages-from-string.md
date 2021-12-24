# Python–从字符串中提取百分比

> 原文:[https://www . geesforgeks . org/python-extract-percents-from-string/](https://www.geeksforgeeks.org/python-extract-percentages-from-string/)

给定一个字符串，提取所有百分比数字。

> **输入** : test_str = 'geeksforgeeks 20%是获得 200%成功的 100%方式'
> **输出** : ['20% '、' 100% '、' 200%']
> **解释** : 20%、100%和 200%是存在的百分比。
> 
> **输入** : test_str = 'geeksforgeeks 是获得成功的途径'
> **输出** : []
> **解释**:不存在百分比。

**方法#1:使用 findall() +正则表达式**

在这种情况下，我们使用后缀中带有“%”符号的适当正则表达式，并使用 findall()从 String 中获取此类数字的所有出现。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Percentages from String 
# Using regex + findall()
import re

# initializing strings
test_str = 'geeksforgeeks is 100 % way to get 200 % success'

# printing original string
print("The original string is : " + str(test_str))

# getting required result from string 
res = re.findall('\d*%', test_str)

# printing result 
print("The percentages : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is 100% way to get 200% success
The percentages : ['100%', '200%']

```

**方法 2:使用 re.sub() + split()**

在这种情况下，我们执行所有单词的拆分，然后从包含%的单词中移除所有非数字字符串。这在某些情况下是有问题的，我们在字符串中有不同的%和数字顺序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Percentages from String 
# Using re.sub() + split()
import re

# initializing strings
test_str = 'geeksforgeeks is 100 % way to get 200 % success'

# printing original string
print("The original string is : " + str(test_str))

# extracting words
temp = test_str.split()

# using 
res = []
for sub in temp:
    if '%' in sub:

        # replace empty string to all non-number chars
        res.append(re.sub(r'[^\d, %]', '', sub))

# printing result 
print("The percentages : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is 100% way to get 200% success
The percentages : ['100%', '200%']

```