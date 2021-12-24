# 遍历 Python 中的字典列表

> 原文:[https://www . geesforgeks . org/iterate-through-list-of-dictionary-in-python/](https://www.geeksforgeeks.org/iterate-through-list-of-dictionaries-in-python/)

在本文中，我们将学习如何遍历字典列表。

**正在使用的词典列表:**

> [{'Python ':'机器学习'，' R ':'机器学习' }，
> 
> {“Python”:“Web 开发”，“Java 脚本”:“Web 开发”，“HTML”:“Web 开发”}，
> 
> {'C++ ':'游戏开发'，' Python ':'游戏开发' }，{'Java': 'App Development '，' Kotlin': 'App Development'}]

## 方法 1:使用索引

这是一种直接方法，只使用索引提取列表元素。

**语法:**

> 列表[索引]

**示例:**

## 蟒蛇 3

```py
# Create a list of dictionaries
languages = [
    {
        "Python": "Machine Learning",
        "R": "Machine learning",
    },
    {
        "Python": "Web development",
        "Java Script": "Web Development",
        "HTML": "Web Development"
    },
    {
        "C++": "Game Development",
        "Python": "Game Development"
    },
    {
        "Java": "App Development",
        "Kotlin": "App Development"
    }
]

print(languages[0])
print(languages[1])
print(languages[2])
print(languages[3])
```

**输出:**

> {'Python ':'机器学习'，' R ':'机器学习' }
> 
> {'Python': 'Web 开发'，' Java 脚本':' Web 开发'，' HTML': 'Web 开发' }
> 
> {'C++ ':'游戏开发'，' Python ':'游戏开发' }
> 
> {'Java': 'App Development '，' Kotlin': 'App Development'}

使用特定词典的索引后，现在我们可以将列表中的每一项都视为一个词典，

**示例:**从特定字典中提取值

## 蟒蛇 3

```py
# Create a list of dictionaries
languages = [
    {
        "Python": "Machine Learning",
        "R": "Machine learning",
    },
    {
        "Python": "Web development",
        "Java Script": "Web Development",
        "HTML": "Web Development"
    },
    {
        "C++": "Game Development",
        "Python": "Game Development"
    },
    {
        "Java": "App Development",
        "Kotlin": "App Development"
    }
]

for key, val in languages[0].items():
    print("{} : {}".format(key, val))
```

**输出:**

> Python:机器学习
> 
> r:机器学习

## **方法二:使用** [**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

迭代到一个列表后，可以使用 keys()函数进一步提取字典中的键。

**示例:**提取键值

## 蟒蛇 3

```py
# Create a list of dictionaries
languages = [
    {
        "Python": "Machine Learning",
        "R": "Machine learning",
    },
    {
        "Python": "Web development",
        "Java Script": "Web Development",
        "HTML": "Web Development"
    },
    {
        "C++": "Game Development",
        "Python": "Game Development"
    },
    {
        "Java": "App Development",
        "Kotlin": "App Development"
    }
]

# iterate over the list
for i in languages:

    # now i is a dict, now we see the keys
    # of the dict
    for key in i.keys():

        # print every key of each dict
        print(key)

    print("-------------")
```

**输出:**

> 计算机编程语言
> 
> 稀有
> 
> ————-
> 
> 计算机编程语言
> 
> java 描述语言
> 
> 超文本标记语言
> 
> ————-
> 
> C++
> 
> 计算机编程语言
> 
> ————-
> 
> Java 语言(一种计算机语言，尤用于创建网站)
> 
> 我的锅
> 
> ————-

## **方法三:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

使用列表理解简单地迭代列表，然后打印字典。

**示例:**使用列表理解提取关键点

## 蟒蛇 3

```py
# Create a list of dictionaries
languages = [
    {
        "Python" : "Machine Learning",
        "R" : "Machine learning",
    },
    {
        "Python" : "Web development",
        "Java Script" : "Web Development",
        "HTML" : "Web Development"
    },
    {
        "C++" : "Game Development",
        "Python" : "Game Development"
    },
    {
        "Java" : "App Development",
        "Kotlin" : "App Development"
    }
]

# here we are printing the keys of the dictionary
# by using list comprehension and each key will be
# printed in a new line due to the presence of " sep = "\n" ".
# It will add a new line character to our output.

print(*[key for i in languages for key in i.keys()], sep = "\n")
```

**输出:**

> 计算机编程语言
> 
> 稀有
> 
> 计算机编程语言
> 
> java 描述语言
> 
> 超文本标记语言
> 
> C++
> 
> 计算机编程语言
> 
> Java 语言(一种计算机语言，尤用于创建网站)
> 
> 我的锅