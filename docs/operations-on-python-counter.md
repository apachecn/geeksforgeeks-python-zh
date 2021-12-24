# Python 计数器上的操作

> 原文:[https://www.geeksforgeeks.org/operations-on-python-counter/](https://www.geeksforgeeks.org/operations-on-python-counter/)

计数器可用于计算列表或字符串中的频率，因为当任何列表或字符串作为输入传递时，它会以字典的形式返回输出，其中键是列表的唯一元素，值是元素的相应频率。
在下面给出的代码中，导入 Collection Python 库中的 Counter 来查找该字符串中每个唯一字符出现的频率，通过使用列表上的 Counter，也可以找到列表中每个唯一元素出现的频率。

## 蟒蛇 3

```
# Write Python3 code here
# Counter used in string to find frequencies of all its unique Characters

from collections import Counter
s1 ='aabbbcccdeff'
c1 = Counter(s1)
print("c1 :", c1)

# Counter used in List to find frequencies of all its unique elements of list
L1 =[1, 2, 1, 1, 4, 4, 4, 5, 6, 6, 3, 3, 0, 0]
t1 = Counter(L1)

print("t1 :", t1)
```

**Output:** 

```
c1 : Counter({'b': 3, 'c': 3, 'a': 2, 'f': 2, 'e': 1, 'd': 1})
t1 : Counter({1: 3, 4: 3, 0: 2, 3: 2, 6: 2, 2: 1, 5: 1})
```

如果 **d** 是输出字典，则对返回的输出字典执行某些操作，如 **d.items()，d . key()，d.values()**

## 蟒蛇 3

```
from collections import Counter
d ='aabbbcccdeff'
d = Counter(d)

# To print Counter value
print("d :", d)

# To access the values corresponds to each keys of the returned dictionary
print("d.values() : ", d.values()) 

# To get the keys and values both of dictionary
print("d.items() :", d.items())

# To get only the keys
print("d.keys() :", d.keys())

# To sort the values of dictionary
print("sorted(d) :", sorted(d))
```

**Output:** 

```
d : Counter({'b': 3, 'c': 3, 'a': 2, 'f': 2, 'e': 1, 'd': 1})
d.values() :  dict_values([2, 3, 3, 2, 1, 1])
d.items() : dict_items([('a', 2), ('b', 3), ('c', 3), ('f', 2), ('e', 1), ('d', 1)])
d.keys() : dict_keys(['a', 'b', 'c', 'f', 'e', 'd'])
sorted(d) : ['a', 'b', 'c', 'd', 'e', 'f']
```

**两个计数器的相加**
两个计数器的相加产生对应于每个键的值的相加，如果一个键存在于一个计数器中而不存在于另一个计数器中，在这种情况下，该键值也进入最终输出。

## 蟒蛇 3

```
from collections import Counter
t1 = Counter('aabbddffggjik')
t2 = Counter('aaabbbssshhhggdkkll')

print("t1:", t1)
print("t2:", t2)
print("t1 + t2 :", t1 + t2)
```

**Output:** 

```
t1: Counter({'g': 2, 'a': 2, 'b': 2, 'f': 2, 'd': 2, 'k': 1, 'j': 1, 'i': 1})
t2: Counter({'a': 3, 'b': 3, 'h': 3, 's': 3, 'l': 2, 'g': 2, 'k': 2, 'd': 1})
t1+t2 : Counter({'a': 5, 'b': 5, 'g': 4, 'k': 3, 'h': 3, 'd': 3, 's': 3, 'l': 2, 'f': 2, 'j': 1, 'i': 1})
```

**两个计数器的相减**
公共元素的计数相互相减(只保留正计数)

## 蟒蛇 3

```
from collections import Counter
t1 = Counter('aabbddffggjik')
t2 = Counter('aaabbbssshhhggdkkll')

print("t1:", t1)
print("t2:", t2)
print("t1-t2 :", t1-t2)
print("t2-t1 :", t2-t1)
```

**Output:** 

```
t1: Counter({'f': 2, 'd': 2, 'b': 2, 'a': 2, 'g': 2, 'k': 1, 'i': 1, 'j': 1})
t2: Counter({'h': 3, 'b': 3, 'a': 3, 's': 3, 'l': 2, 'k': 2, 'g': 2, 'd': 1})
t1-t2 : Counter({'f': 2, 'i': 1, 'j': 1, 'd': 1})
t2-t1 : Counter({'h': 3, 's': 3, 'l': 2, 'k': 1, 'b': 1, 'a': 1})
```

两个计数器
交叉点(&)的**交叉点(&)将只保留相应计数的最小值:min(t1[x]，t2[x]):**

## 蟒蛇 3

```
from collections import Counter
t1 = Counter('aaabbbbccdeeee')
t2 = Counter('aabbccccdddee')

print("t1 :", t1)
print("t2 :", t2)
print("t1&t2 :", t1&t2)
```

**Output:** 

```
t1 : Counter({'e': 4, 'b': 4, 'a': 3, 'c': 2, 'd': 1})
t2 : Counter({'c': 4, 'd': 3, 'a': 2, 'e': 2, 'b': 2})
t1&t2 : Counter({'c': 2, 'a': 2, 'e': 2, 'b': 2, 'd': 1})
```

**两个计数器的并集(|)**
并集(|)将只保留相应计数的最大值:max(c[x]，d[x]):

## 蟒蛇 3

```
from collections import Counter
t1 = Counter('aaabbbbccdeeee')
t2 = Counter('aabbccccdddee')

print("t1 :", t1)
print("t2 :", t2)
print("t1|t2 :", t1|t2)
```

**Output:** 

```
t1 : Counter({'b': 4, 'e': 4, 'a': 3, 'c': 2, 'd': 1})
t2 : Counter({'c': 4, 'd': 3, 'a': 2, 'b': 2, 'e': 2})
t1|t2 : Counter({'b': 4, 'e': 4, 'c': 4, 'a': 3, 'd': 3})
```