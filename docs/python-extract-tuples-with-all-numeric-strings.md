# Python–提取所有数值字符串的元组

> 原文:[https://www . geesforgeks . org/python-extract-元组-带全数字字符串/](https://www.geeksforgeeks.org/python-extract-tuples-with-all-numeric-strings/)

给定一个元组列表，只提取那些包含所有数字字符串的元组。

> **输入**:test _ list =[(“45”、“86”)、(“Gfg”、“1”)、(“98”、“10”)]
> **输出**:[(“45”、“86”)、(“98”、“10”)]
> **解释**:只过滤代表元组的数字。
> 
> **输入**:test _ list =[(“Gfg”，“1”)]
> **输出** : []
> **解释**:没有只包含数字的元组。

**方法一:使用列表理解+ all() + isdigit()**

在本例中，我们使用 isdigit()检查字符串是否为数字字符串，使用 all()检查所有字符串。列表理解用于迭代所有元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Tuples with all Numeric Strings
# Using all() + list comprehension + isdigit()

# initializing list
test_list = [("45", "86"), ("Gfg", "1"), ("98", "10"), ("Gfg", "Best")]

# printing original list
print("The original list is : " + str(test_list))

# all() checks for all digits()
res = [sub for sub in test_list if all(ele.isdigit() for ele in sub)]

# printing result 
print("Filtered Tuples : " + str(res))
```

**Output**

```py
The original list is : [('45', '86'), ('Gfg', '1'), ('98', '10'), ('Gfg', 'Best')]
Filtered Tuples : [('45', '86'), ('98', '10')]

```

**方法 2:使用 lambda + filter() + isdigit()**

在本例中，我们使用 filter() + lambda 执行过滤任务，isdigit()用于检查数值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Tuples with all Numeric Strings
# Using lambda + filter() + isdigit()

# initializing list
test_list = [("45", "86"), ("Gfg", "1"), ("98", "10"), ("Gfg", "Best")]

# printing original list
print("The original list is : " + str(test_list))

# all() checks for all digits()
res = list(filter(lambda sub : all(ele.isdigit() for ele in sub), test_list))

# printing result 
print("Filtered Tuples : " + str(res))
```

**Output**

```py
The original list is : [('45', '86'), ('Gfg', '1'), ('98', '10'), ('Gfg', 'Best')]
Filtered Tuples : [('45', '86'), ('98', '10')]

```