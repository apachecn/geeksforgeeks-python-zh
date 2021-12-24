# 从 Python 中的数据集找到 k 个最常出现的单词

> 原文:[https://www . geesforgeks . org/find-k-frequency-words-data-set-python/](https://www.geeksforgeeks.org/find-k-frequent-words-data-set-python/)

给定数据集，我们可以找到 k 个最频繁出现的单词。

这个问题的解决方案已经呈现为[从文件](https://www.geeksforgeeks.org/find-the-k-most-frequent-words-from-a-file/)中找到 k 个最频繁的单词。但是我们可以在 Python 中借助一些高性能模块非常高效地解决这个问题。

为此，我们将使用一个高性能数据类型模块，即**集合**。本模块获得了一些专门的容器数据类型，我们将使用本模块中的 **[计数器](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/)** 类。

举例:

```py
Input : "John is the son of John second. 
         Second son of John second is William second."
Output : [('second', 4), ('John', 3), ('son', 2), ('is', 2)]

Explanation :
1\. The string will converted into list like this :
    ['John', 'is', 'the', 'son', 'of', 'John', 
     'second', 'Second', 'son', 'of', 'John', 
     'second', 'is', 'William', 'second']
2\. Now 'most_common(4)' will return four most 
   frequent words and its count in tuple. 

Input : "geeks for geeks is for geeks. By geeks
         and for the geeks."
Output : [('geeks', 5), ('for', 3)]

Explanation :
most_common(2) will return two most frequent words and their count.

```

**进场:**

```py
1.  从集合模块导入计数器类。2.  使用 Split()将字符串拆分为列表，它将返回单词列表。3.  现在将列表传递给 Counter 类的实例4.  计数器中的函数“最常用()”将返回列表中最常用的单词列表及其计数。
```

下面是上述方法的 Python 实现:

```py
# Python program to find the k most frequent words
# from data set
from collections import Counter

data_set = "Welcome to the world of Geeks " \
"This portal has been created to provide well written well" \
"thought and well explained solutions for selected questions " \
"If you like Geeks for Geeks and would like to contribute " \
"here is your chance You can write article and mail your article " \
" to contribute at geeksforgeeks org See your article appearing on " \
"the Geeks for Geeks main page and help thousands of other Geeks. " \

# split() returns list of all the words in the string
split_it = data_set.split()

# Pass the split_it list to instance of Counter class.
Counter = Counter(split_it)

# most_common() produces k frequently encountered
# input values and their respective counts.
most_occur = Counter.most_common(4)

print(most_occur)
```

输出:

```py
[('Geeks', 5), ('to', 4), ('and', 4), ('article', 3)]

```