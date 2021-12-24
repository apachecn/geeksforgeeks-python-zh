# Python–字符替换组合

> 原文:[https://www . geesforgeks . org/python-字符-替换-组合/](https://www.geeksforgeeks.org/python-character-replacement-combination/)

给定字符映射到替换字符值列表的字符串和字典，在用映射值替换当前字符后，构造所有可能的字符串。

> **输入** : test_str = "geeks "，test_dict = {'s' : ['1 '，' 5']，' k' : ['3']}
> **输出** : ['gee31 '，' geek1 '，' gee35 '，' geek5 '，' gee3s '，' geeks']
> **解释**:所有可能的字符串替换，例如在' gee35 '中，k 被' 3 '替换，s 被' 5 '替换。
> 
> **输入** : test_str = "geeks "，test_dict = {'s' : ['1']，' k' : ['3']}
> **输出** : ['gee31 '，' geek1 '，' gee3s '，' geeks']
> **解释**:字符串所有可能的替换，例如在' gee31 '中，k 被' 3 '替换，s 被' 1 '替换。

**方法:使用 zip() +列表理解+替换()+产品()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 product 提取所有组合字符，并使用 zip()一次配对一个字符，使用 replace()进行替换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Character Replacement Combination
# Using zip() + list comprehension + replace() + product()
from itertools import product

# initializing string
test_str = "geeks"

# printing original string
print("The original string is : " + str(test_str))

# initializing dictionary
test_dict = {'s' : ['1', '2'], 'k' : ['3']}

# adding original character to possible characters 
for key in test_dict.keys():
    if key not in test_dict[key]:
        test_dict[key].append(key)

res = []

# constructing all possible combination of values using product
# mapping using zip()
for sub in [zip(test_dict.keys(), chr) for chr in product(*test_dict.values())]:
    temp = test_str
    for repls in sub:

        # replacing all elements at once using * operator
        temp = temp.replace(*repls)
    res.append(temp)

# printing result 
print("All combinations : " + str(res)) 
```

**Output**

```
The original string is : geeks
All combinations : ['gee31', 'geek1', 'gee32', 'geek2', 'gee3s', 'geeks']

```