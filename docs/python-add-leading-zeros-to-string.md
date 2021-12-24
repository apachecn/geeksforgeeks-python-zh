# Python |在字符串中添加前导零

> 原文:[https://www . geesforgeks . org/python-add-前导零到字符串/](https://www.geeksforgeeks.org/python-add-leading-zeros-to-string/)

有时，在字符串操作过程中，我们会遇到一个问题，需要根据需要填充或添加前导零到字符串中。这个问题可能发生在 web 开发中。在许多情况下，用人手解决这个问题会很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`rjust()`**

`**rjust**`功能提供了一种单线方式来执行这一特定任务。因此可以很容易地应用于任何需要填充的字符串。我们可以指定所需的填充量。

```py
# Python3 code to demonstrate
# adding leading zeros
# using rjust()

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string))

# No. of zeros required
N = 4

# using rjust()
# adding leading zero
res = test_string.rjust(N + len(test_string), '0')

# print result
print("The string after adding leading zeros : " + str(res))
```

**Output :**

```py
The original string : GFG
The string after adding leading zeros : 0000GFG

```

**方法 2:使用`zfill()`**

这是执行这个特殊任务的另一种方法，在这个函数中，我们不需要指定需要填充的字母，这个函数专门用于内部填充零，因此推荐使用。

```py
# Python3 code to demonstrate
# adding leading zeros
# using zfill()

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string))

# No. of zeros required
N = 4

# using zfill()
# adding leading zero
res = test_string.zfill(N + len(test_string))

# print result
print("The string after adding leading zeros : " + str(res))
```

**Output :**

```py
The original string : GFG
The string after adding leading zeros : 0000GFG

```