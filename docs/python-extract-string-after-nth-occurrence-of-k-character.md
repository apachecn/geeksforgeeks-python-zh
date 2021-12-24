# Python–K 字符第 n 次出现后提取字符串

> 原文:[https://www . geesforgeks . org/python-extract-n 次出现后的字符串-k-character/](https://www.geeksforgeeks.org/python-extract-string-after-nth-occurrence-of-k-character/)

给定一个字符串，在第 n 次出现一个字符后提取该字符串。

> **输入**:test _ str = ' geek forgeks '，K = ' e '，N = 2
> **输出**:kforgeks
> **解释**:第二次出现后。的“e”字符串被提取。
> 
> **输入**:test _ str = ' geek forgeks '，K = ' e '，N = 4
> **输出** : ks
> **解释**:第 4 次发生后。的“e”字符串被提取。

**方法#1:使用 split()**

这是执行这项任务的方法之一。在本例中，我们将 split()自定义为在第 n 次出现时拆分，然后使用“-1”打印后面提取的字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract String after Nth occurrence of K character 
# Using split()

# initializing string
test_str = 'geekforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "e"

# initializing N 
N = 3

# using split() to perform required string split
# "-1" to extract required part
res = test_str.split(K, N)[-1]

# printing result 
print("The extracted string : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks
The extracted string : eks

```

**方法 2:使用 re.split()**

这是解决这个问题的另一种方法。类似于上面的函数，我们执行 split()来执行拆分任务，但是从 regex 库中，它也提供了在第 n 次出现时进行拆分的灵活性。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract String after Nth occurrence of K character 
# Using re.split()
import re

# initializing string
test_str = 'geekforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "e"

# initializing N 
N = 3

# using split() to perform required string split
# "-1" to extract required part
res = re.split(K, test_str, N)[-1]

# printing result 
print("The extracted string : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks
The extracted string : eks

```