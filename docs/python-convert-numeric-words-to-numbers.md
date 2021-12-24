# Python |将数字单词转换为数字

> 原文:[https://www . geesforgeks . org/python-convert-numeric-word-to-numbers/](https://www.geeksforgeeks.org/python-convert-numeric-words-to-numbers/)

有时，在使用 python Strings 时，我们可能会遇到一个问题，需要将命名数字形式的字符串转换为实际数字。这在数学领域和数据科学领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`loop + join() + split()`**
解决这个问题的方法之一是使用映射，可以将数字与单词映射，然后使用映射到数字来拆分字符串并重新加入。

```py
# Python3 code to demonstrate working of 
# Convert numeric words to numbers
# Using join() + split()

help_dict = {
    'one': '1',
    'two': '2',
    'three': '3',
    'four': '4',
    'five': '5',
    'six': '6',
    'seven': '7',
    'eight': '8',
    'nine': '9',
    'zero' : '0'
}

# initializing string
test_str = "zero four zero one"

# printing original string
print("The original string is : " + test_str)

# Convert numeric words to numbers
# Using join() + split()
res = ''.join(help_dict[ele] for ele in test_str.split())

# printing result 
print("The string after performing replace : " + res) 
```

**Output :**

```py
The original string is : zero four zero one
The string after performing replace : 0401

```