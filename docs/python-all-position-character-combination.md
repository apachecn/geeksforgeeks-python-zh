# Python–全位置字符组合

> 原文:[https://www . geesforgeks . org/python-全位置-字符-组合/](https://www.geeksforgeeks.org/python-all-position-character-combination/)

给定一个字符 K，追加到每个索引和所有长度组合。

> **输入** : test_str = 'gfg '，K = ' { content } ' 2019；
> **输出** : ['gfg '，' gf { content }]，' g$g '，' g$ '，' $fg '，' $ f { content } ' 2019；，' $g '，' $ { content } ' 2019；】
> **解释**:所有可能出现替换的配对。
> 
> **输入** : test_str = 'gfg '，K = ' *
> **输出** : ['gfg '，' gf* '，' g*g '，' g** '，' *fg '，' *f* '，' **g '，' ***']
> **解释**:所有可能出现替换的对。

**方法#1:使用 loop + zip() + join() + product()**

在这种情况下，形成组合的任务是使用 product()完成的，loop 用于元素的迭代，join()用于获得所需的结果，zip()用于将每个提取的产品与原始 String 进行组合。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# All Position Character Combination
# Using loop + zip() + join() + product()
import itertools

# initializing strings
test_str = 'gfg'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "{content}quot;

res = [] 

# True and false represent Character from String and K respectively.
for sub in itertools.product((True, False), repeat = len(test_str)):
    res.append("".join(chr if ele else K for chr, ele in zip(test_str, sub)))

# printing result 
print("The required Combinations : " + str(res)) 
```

**Output:**

```
The original string is : gfg
The required Combinations : ['gfg', 'gf{content}apos;, 'g$g', 'g$', '$fg', '$f{content}apos;, '$g', '${content}apos;]

```

**方法 2:使用列表理解**

这类似于上面的方法，唯一的区别是它是一个单一行中所有功能的简写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# All Position Character Combination
# Using list comprehension
import itertools

# initializing strings
test_str = 'abc'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = "{content}quot;

# one liner to perform this task 
res = ["".join(chr if ele else K for chr, ele in zip(test_str, sub)) \
     for sub in itertools.product((True, False), repeat = len(test_str))]

# printing result 
print("The required Combinations : " + str(res)) 
```

**Output:**

```
The original string is : abc
The required Combinations : ['abc', 'ab{content}apos;, 'a$c', 'a$', '$bc', '$b{content}apos;, '$c', '${content}apos;]

```