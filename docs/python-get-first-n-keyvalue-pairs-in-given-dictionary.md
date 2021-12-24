# Python |获取给定字典中的第一个 N 键:值对

> 原文:[https://www . geesforgeks . org/python-get-first-n-key value-pairs-in-given-dictionary/](https://www.geeksforgeeks.org/python-get-first-n-keyvalue-pairs-in-given-dictionary/)

给定一个字典，任务是从给定的字典中获取 N 个键:值对。这类问题在某些情况下会很有用，比如在 web 开发中获取前 N 个值。

请注意，给定的字典是无序的，前 N 对在这里不会一直相同。如果你需要在你的问题中维持秩序，你可以使用有序字典。

**代码#1:** 使用 itertools.islice()方法

```
# Python program to get N key:value pairs in given dictionary
# using itertools.islice() method

import itertools 

# Initialize dictionary
test_dict = {'Geeks' : 1, 'For':2,  'is' : 3, 'best' : 4, 'for' : 5, 'CS' : 6} 

# printing original dictionary 
print("The original dictionary : " +  str(test_dict)) 

# Initialize limit 
N = 3

# Using islice() + items() 
# Get first N items in dictionary 
out = dict(itertools.islice(test_dict.items(), N)) 

# printing result  
print("Dictionary limited by K is : " + str(out)) 
```

**输出:**

> 原词典:{'for': 5，' best': 4，' CS': 6，' is': 3，' Geeks': 1，' For': 2}
> 受 K 限制的词典是:{'for': 5，' best': 4，' CS': 6}

**代码#2:** 对字典项目列表使用切片

```
# Python program to get N key:value pairs in given dictionary
# using list slicing

# Initialize dictionary
test_dict = {'Geeks' : 1, 'For':2,  'is' : 3, 'best' : 4, 'for' : 5, 'CS' : 6} 

# printing original dictionary 
print("The original dictionary : " +  str(test_dict)) 

# Initialize limit 
N = 3

# Using items() + list slicing 
# Get first K items in dictionary 
out = dict(list(test_dict.items())[0: N]) 

# printing result  
print("Dictionary limited by K is : " + str(out)) 
```

**输出:**

> 原词典:{'best': 3，' gfg': 1，' is': 2，' CS': 5，' for': 4}
> 受 K 限制的词典是:{'best': 3，' gfg': 1，' is': 2}