# Python |字符串中每个字符的出现频率

> 原文:[https://www . geesforgeks . org/python-字符串中每个字符的出现频率/](https://www.geeksforgeeks.org/python-frequency-of-each-character-in-string/)

给定一个字符串，任务是找到该字符串中所有字符的频率，并返回一个字典，其中`key` 是该字符，其`value` 是其在给定字符串中的频率。

**方法#1 :** 幼稚方法

只需遍历字符串并在新出现元素的字典中形成一个键，或者如果元素已经出现，将其值增加 1。

```py
# Python3 code to demonstrate 
# each occurrence frequency using 
# naive method 

# initializing string 
test_str = "GeeksforGeeks"

# using naive method to get count 
# of each element in string 
all_freq = {}

for i in test_str:
    if i in all_freq:
        all_freq[i] += 1
    else:
        all_freq[i] = 1

# printing result 
print ("Count of all characters in GeeksforGeeks is :\n "
                                        +  str(all_freq))
```

**输出:**

```py
Count of all characters in GeeksforGeeks is :
 {'r': 1, 'e': 4, 'k': 2, 'G': 2, 's': 2, 'f': 1, 'o': 1}

```

**方法 2 :** 使用`collections.Counter()`

可以用来查找所有出现的最建议的方法是这个方法，它实际上获取所有元素频率，如果需要，也可以用来打印单个元素频率。

```py
# Python3 code to demonstrate 
# each occurrence frequency using 
# collections.Counter()
from collections import Counter

# initializing string 
test_str = "GeeksforGeeks"

# using collections.Counter() to get 
# count of each element in string 
res = Counter(test_str)

# printing result 
print ("Count of all characters in GeeksforGeeks is :\n "
                                           +  str(res))
```

**输出:**

```py
Count of all characters in GeeksforGeeks is : 
Counter({'e': 4, 's': 2, 'k': 2, 'G': 2, 'o': 1, 'r': 1, 'f': 1})

```

**方法 3 :** 使用`dict.get()`

`get()`方法用于检查字符串中以前出现的字符，如果它是新的，它会将 0 指定为初始值并附加 1，否则会将 1 附加到字典中该元素以前保存的值。

```py
# Python3 code to demonstrate 
# each occurrence frequency using 
# dict.get()

# initializing string 
test_str = "GeeksforGeeks"

# using dict.get() to get count 
# of each element in string 
res = {}

for keys in test_str:
    res[keys] = res.get(keys, 0) + 1

# printing result 
print ("Count of all characters in GeeksforGeeks is : \n"
                                             +  str(res))
```

**输出:**

```py
Count of all characters in GeeksforGeeks is :
 {'k': 2, 'e': 4, 's': 2, 'G': 2, 'f': 1, 'r': 1, 'o': 1}

```

**方法 4 :** 使用`set() + count()`

`count()`再加上`set()`也可以实现这个任务，在这种情况下我们只需迭代集合转换后的字符串，得到原始字符串中每个字符的计数，并使用`count()`为该元素赋值。

```py
# Python3 code to demonstrate 
# each occurrence frequency using 
# set() + count()

# initializing string 
test_str = "GeeksforGeeks"

# using set() + count() to get count 
# of each element in string 
res = {i : test_str.count(i) for i in set(test_str)}

# printing result 
print ("The count of all characters in GeeksforGeeks is :\n "
                                               +  str(res))
```

**输出:**

```py
Count of all characters in GeeksforGeeks is :
 {'G': 2, 's': 2, 'k': 2, 'e': 4, 'o': 1, 'r': 1, 'f': 1}

```