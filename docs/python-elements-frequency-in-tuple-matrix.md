# Python–元组矩阵中的元素频率

> 原文:[https://www . geesforgeks . org/python-elements-frequency-in-tuple-matrix/](https://www.geeksforgeeks.org/python-elements-frequency-in-tuple-matrix/)

有时，在使用 Python Tuple Matrix 时，我们可能会遇到一个问题，即我们需要获取其中每个元素的频率。这种问题可能发生在日常编程和 web 开发领域。让我们讨论一下解决这个问题的某些方法。

> **输入**:test _ list =[(4，5)，(3，2)]，[(2，2)]
> **输出** : {4: 1，5: 1，3: 1，2: 3}
> 
> **输入**:test _ list =[(4，5)，(3，2)]
> **输出** : {4: 1，5: 1，3: 1，2: 1}

**方法#1:使用嵌套`chain() + "*" operator + Counter()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 Counter()和嵌套链来执行获取频率的任务，以迎合嵌套，并使用“*”运算符来执行每个元素的解包和打包。

```
# Python3 code to demonstrate working of 
# Elements frequency in Tuple Matrix
# Using nested chain() + "*" operator + Counter()
from itertools import chain
from collections import Counter

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2)], [(1, 2), (5, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Elements frequency in Tuple Matrix
# Using nested chain() + "*" operator + Counter()
res = dict(Counter(chain(*chain(*test_list))))

# printing result 
print("Elements frequency : " + str(res))
```

**Output :**

```
The original list is : [[(4, 5), (3, 2)], [(2, 2)], [(1, 2), (5, 5)]]
Elements frequency : {4: 1, 5: 3, 3: 1, 2: 4, 1: 1}

```

**方法 2:使用`chain.from_iterables() + Counter()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 chain.from_iterables()执行打包、解包和展平任务。

```
# Python3 code to demonstrate working of 
# Elements frequency in Tuple Matrix
# Using chain.from_iterables() + Counter()
from itertools import chain
from collections import Counter

# initializing lists
test_list = [[(4, 5), (3, 2)], [(2, 2)], [(1, 2), (5, 5)]]

# printing original list
print("The original list is : " + str(test_list))

# Elements frequency in Tuple Matrix
# Using chain.from_iterables() + Counter()
res = dict(Counter(chain.from_iterable(chain.from_iterable(test_list))))

# printing result 
print("Elements frequency : " + str(res))
```

**Output :**

```
The original list is : [[(4, 5), (3, 2)], [(2, 2)], [(1, 2), (5, 5)]]
Elements frequency : {4: 1, 5: 3, 3: 1, 2: 4, 1: 1}

```