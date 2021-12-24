# Python–K 个子字符串的过滤字符串组合

> 原文:[https://www . geesforgeks . org/python-filter-strings-组合拳-k-substrings/](https://www.geeksforgeeks.org/python-filter-strings-combination-of-k-substrings/)

给定一个字符串列表，提取所有由 K 个子字符串组成的字符串。

> **输入**:test _ list =[“geeks 4u”、“allbest”、“abcdef”]，substr _ list =[“s4u”、“est”、“al”、“ge”、“ek”、“def”]，K = 3
> **输出**:[“geeks 4u”]
> **解释** : geeks4u 由 3 个子串–ge、ek、s4u 组成。
> 
> **输入**:test _ list =[“geeks 4u”、“allbest”、“abcdef”]，substr _ list =[“s4u”、“est”、“al”、“ge”、“def”、“lb”]，K = 3
> **输出**:[“all best”]
> **解释** : allbest 由 3 个子 str–al、lb 和 est 组成。

**方法#1:使用置换()+ map() + join() + set() + loop**

在本文中，我们通过从子串列表中获取 K 个子串的所有可能的排列来执行这个任务，然后使用 join 和 map()执行 join 任务。set()用于避免重复。最后，使用循环从字符串列表中进行匹配。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Strings  combination of K substrings
# Using permutations() + map() + join() + set() + loop
from itertools import permutations

# initializing list
test_list = ["geeks4u", "allbest", "abcdef"]

# printing string
print("The original list : " + str(test_list))

# initializing substring list
substr_list = ["s4u", "est", "al", "ge", "ek", "def", "lb"]

# initializing K 
K = 3

# getting all permutations
perms = list(set(map(''.join, permutations(substr_list, r = K))))

# using loop to check permutations with list
res = []
for ele in perms:
    if ele in test_list:
        res.append(ele)

# printing results 
print("Strings after joins : " + str(res))
```

**Output**

```
The original list : ['geeks4u', 'allbest', 'abcdef']
Strings after joins : ['geeks4u', 'allbest']

```

**方法 2:使用交集()**

这利用了上述方法的所有功能，最后一个匹配置换列表和原始列表的任务是通过交集来完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Strings  combination of K substrings
# Using permutations() + map() + join() + set() + intersection()
from itertools import permutations

# initializing list
test_list = ["geeks4u", "allbest", "abcdef"]

# printing string
print("The original list : " + str(test_list))

# initializing substring list
substr_list = ["s4u", "est", "al", "ge", "ek", "def", "lb"]

# initializing K 
K = 3

# getting all permutations
perms = set(map(''.join, permutations(substr_list, r = K)))

# using intersection() to solve this problem 
res = list(set(test_list).intersection(perms))

# printing results 
print("Strings after joins : " + str(res))
```

**Output**

```
The original list : ['geeks4u', 'allbest', 'abcdef']
Strings after joins : ['geeks4u', 'allbest']

```