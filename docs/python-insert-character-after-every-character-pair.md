# Python |在每个字符对后插入字符

> 原文:[https://www . geesforgeks . org/python-每对字符后插入字符/](https://www.geeksforgeeks.org/python-insert-character-after-every-character-pair/)

有时，我们可能会遇到这样的问题:我们需要在成对(第二个)字符之后插入一个特定的字符。处理数据时可能会出现这种问题，这需要在机器学习领域插入逗号或任何其他特殊字符。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`join()` +列表理解**
以上方法的组合可以用来执行这个特定的任务。列表理解和切片可用于将字符串转换为列表，连接函数可用于通过在它们之间插入所需字符来重新连接它们。

```
# Python3 code to demonstrate working of
# Insert character after every character pair
# Using join() + list comprehension

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + test_str)

# Using join() + list comprehension
# Insert character after every character pair
res = ', '.join(test_str[i:i + 2] for i in range(0, len(test_str), 2))

# printing result 
print("The string after inserting comma after every character pair : " + res)
```

**Output :**

```
The original string is : GeeksforGeeks
The string after inserting comma after every character pair : Ge, ek, sf, or, Ge, ek, s

```