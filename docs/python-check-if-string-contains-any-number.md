# Python–检查字符串是否包含任何数字

> 原文:[https://www . geesforgeks . org/python-check-if-string-contains-any-number/](https://www.geeksforgeeks.org/python-check-if-string-contains-any-number/)

给定一个字符串，检查它是否包含任何数字。

> **输入** : test_str = 'geeks4g2eeks'
> 输出:真
> **说明**:包含 4 和 2。
> 
> **输入**:test _ str = ' geeksforgeeks '
> **输出** : False
> **解释**:不含数字。

**方法#1:使用任意()+ isdigit()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 isdigit()检查数字，并使用 any()检查任何事件。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if string contains any number
# Using isdigit() + any()

# initializing string
test_str = 'geeks4geeks'

# printing original string
print("The original string is : " + str(test_str))

# using any() to check for any occurrence
res = any(chr.isdigit() for chr in test_str)

# printing result 
print("Does string contain any digit ? : " + str(res)) 
```

**Output**

```
The original string is : geeks4geeks
Does string contain any digit ? : True

```

**方法 2:使用 next() +生成器表达式+ isdigit()**

这是执行这项任务的另一种方式。这在较大字符串的情况下是推荐的，生成器中的迭代很便宜，但是构造通常效率很低。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if string contains any number
# Using isdigit() + next() + generator expression

# initializing string
test_str = 'geeks4geeks'

# printing original string
print("The original string is : " + str(test_str))

# next() checking for each element, reaches end, if no element found as digit
res = True if next((chr for chr in test_str if chr.isdigit()), None) else False

# printing result 
print("Does string contain any digit ? : " + str(res)) 
```

**Output**

```
The original string is : geeks4geeks
Does string contain any digit ? : True

```