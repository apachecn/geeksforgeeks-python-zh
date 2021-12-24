# Python–带特定字母的字数

> 原文:[https://www . geesforgeks . org/python-带特定字母的字数/](https://www.geeksforgeeks.org/python-count-of-words-with-specific-letter/)

给定一串单词，提取特定字母的字数。

> **输入** : test_str = 'geeksforgeeks 最适合极客'，字母= "g"
> **输出** : 2
> **解释**:“g”出现在 2 个字里。
> 
> **输入** : test_str = 'geeksforgeeks 最适合极客'，字母= "s"
> **输出** : s
> **解释**:“s”出现在 4 个字里。

**方法一:使用列表理解+ len() + split()**

这是执行这项任务的方法之一。在这种情况下，我们使用 split()执行从字符串中提取单词的任务，并使用循环来迭代单词以检查字母是否存在，使用 len()来获取带有字母的单词数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Count of Words with specific letter
# Using list comprehension + len() + split()

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing letter 
letter = "e"

# extracting desired count using len()
# list comprehension is used as shorthand
res = len([ele for ele in test_str.split() if letter in ele])

# printing result 
print("Words count : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks is best for geeks
Words count : 3

```

**方法 2:使用滤镜()+λ+len()+split()**

这是执行这项任务的另一种方式。在本文中，我们使用 filter() + lambda 执行过滤任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Count of Words with specific letter
# Using filter() + lambda + len() + split()

# initializing string
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing letter 
letter = "e"

# extracting desired count using len()
# filter() used to check for letter existence
res = len(list(filter(lambda ele : letter in ele, test_str.split())))

# printing result 
print("Words count : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks is best for geeks
Words count : 3

```