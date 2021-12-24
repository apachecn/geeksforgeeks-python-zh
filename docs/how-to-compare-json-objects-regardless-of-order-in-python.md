# 如何在 Python 中不分先后地比较 JSON 对象？

> 原文:[https://www . geesforgeks . org/how-to-compare-JSON-objects-不管 python 中的顺序如何/](https://www.geeksforgeeks.org/how-to-compare-json-objects-regardless-of-order-in-python/)

[JSON](https://www.geeksforgeeks.org/javascript-json/) 是 Java 脚本对象符号。这些是用于数据交换的独立于语言的源代码，本质上通常是轻量级的。它充当了 XML 的替代。这些通常是人类可以轻松读写的文本，机器解析 JSON 和生成结果也更容易。JSON 主要用于服务器和网络应用程序之间的数据传输。。

在本文中，我们将学习如何比较 JSON 对象，而不管它们在 Python 中的存在顺序如何。

**进场:**

*   导入模块
*   创建 JSON 字符串
*   将字符串转换为 python 词典
*   分类词典
*   比较
*   打印结果

下面给出了实现相同功能的各种实现方式，

**例 1:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)

## 蟒蛇 3

```
import json

# JSON string
json_1 = '{"Name":"GFG", "Class": "Website", "Domain":"CS/IT", "CEO":"Sandeep Jain"}'

json_2 = '{"CEO":"Sandeep Jain", "Domain":"CS/IT","Name": "GFG","Class": "Website"}'

# Converting string into Python dictionaries
json_dict1 = json.loads(json_1)
json_dict2 = json.loads(json_2)

print(sorted(json_dict1.items()) == sorted(json_dict2.items()))
```

**输出:**

```
True
```

**示例 2:** 更复杂的比较

## 蟒蛇 3

```
import json

# JSON string
json_1 = '{"Name":"GFG", "Class": "Website", "Domain":"CS/IT", "CEO":"Sandeep Jain","Subjects":["DSA","Python","C++","Java"]}'

json_2 = '{"CEO":"Sandeep Jain","Subjects":["C++","Python","DSA","Java"], "Domain":"CS/IT","Name": "GFG","Class": "Website"}'

# Convert string into Python dictionary
json1_dict = json.loads(json_1)
json2_dict = json.loads(json_2)

print(sorted(json1_dict.items()) == sorted(json2_dict.items()))

print(sorted(json1_dict.items()))
print(sorted(json2_dict.items()))
```

**输出:**

> 错误的
> 
> [('CEO '，' Sandeep Jain ')，(' Class '，'网站')，(' Domain '，' CS/IT ')，(' Name '，' GFG '，(' Subjects '，['DSA '，' Python '，' C++ '，' Java'])]
> 
> [('CEO '，' Sandeep Jain ')，(' Class '，'网站')，(' Domain '，' CS/IT ')，(' Name '，' GFG '，(' Subjects '，['C++ '，' Python '，' DSA '，' Java'])]

在这种情况下，我们得到的结果是 False，因为 sorted()方法的问题是它只在字典的顶层工作，即在键上工作，而不是在它们的值上工作，这可以通过上面的代码来验证。因此，在这种情况下，我们可以自己定义一个自定义函数，它可以递归地对任何列表或字典进行排序(通过将字典转换为键值对的列表)，从而使它们适合于比较。下面给出了使用这种替代方案的实现。

**示例:**

## 蟒蛇 3

```
import json

# JSON string
json_1 = '{"Name":"GFG", "Class": "Website", "Domain":"CS/IT", "CEO":"Sandeep Jain","Subjects":["DSA","Python","C++","Java"]}'

json_2 = '{"CEO":"Sandeep Jain","Subjects":["C++","Python","DSA","Java"], "Domain":"CS/IT","Name": "GFG","Class": "Website"}'

# Convert string into Python dictionary
json1_dict = json.loads(json_1)
json2_dict = json.loads(json_2)

def sorting(item):
    if isinstance(item, dict):
        return sorted((key, sorting(values)) for key, values in item.items())
    if isinstance(item, list):
        return sorted(sorting(x) for x in item)
    else:
        return item

print(sorting(json1_dict) == sorting(json2_dict))
```

**输出:**

```
True
```