# Python–查找字符串中所有重复的字符

> 原文:[https://www . geesforgeks . org/python-find-重复字符-string/](https://www.geeksforgeeks.org/python-find-duplicate-characters-string/)

给定一个字符串，找出所有彼此相似的重复字符。

让我们看看这个例子。
示例:

```py
Input : hello
Output : l

Input : geeksforgeeeks
Output : e g k s

```

我们在下面的帖子中讨论了一个解决方案。
[打印输入字符串中的所有重复项](https://www.geeksforgeeks.org/print-all-the-duplicates-in-the-input-string/)

我们可以使用 python Counter()方法快速解决这个问题。方法很简单。

1)首先使用 Counter 方法创建一个字典，将字符串作为键，将它们的频率作为值。
2)声明一个临时变量。
3)打印键中值大于 1 的所有索引。

```py
from collections import Counter

def find_dup_char(input):

    # now create dictionary using counter method
    # which will have strings as key and their 
    # frequencies as value
    WC = Counter(input)
    j = -1

    # Finding no. of  occurrence of a character
    # and get the index of it.
    for i in WC.values():
        j = j + 1
        if( i > 1 ):
            print WC.keys()[j],

# Driver program
if __name__ == "__main__":
    input = 'geeksforgeeks'
    find_dup_char(input)
```

输出:

```py
e g k s

```