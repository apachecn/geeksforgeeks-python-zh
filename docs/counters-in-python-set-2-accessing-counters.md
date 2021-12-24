# Python 中的计数器|集合 2(访问计数器)

> 原文:[https://www . geesforgeks . org/counters-in-python-set-2-access-counters/](https://www.geeksforgeeks.org/counters-in-python-set-2-accessing-counters/)

[Python 中的计数器|集合 1(初始化和更新)](https://www.geeksforgeeks.org/counters-in-python-set-1/)

一旦初始化，计数器就像字典一样被访问。此外，它不会引发键值错误(如果键值不存在)，取而代之的是该值的计数显示为 0。

**示例:**

```
# Python program to demonstrate accessing of
# Counter elements
from collections import Counter

# Create a list
z = ['blue', 'red', 'blue', 'yellow', 'blue', 'red']
col_count = Counter(z)
print(col_count)

col = ['blue','red','yellow','green']

# Here green is not in col_count 
# so count of green will be zero
for color in col:
    print (color, col_count[color])
```

**输出:** 

```
Counter({'blue': 3, 'red': 2, 'yellow': 1})
blue 3
red 2
yellow 1
green 0

```

**elements():**
elements()方法返回一个迭代器，该迭代器产生计数器已知的所有项目。
注意:不包括计数< = 0 的元素。

**示例:**

```
# Python example to demonstrate elements() on
# Counter (gives back list)
from collections import Counter

coun = Counter(a=1, b=2, c=3)
print(coun)

print(list(coun.elements()))
```

**输出:**

```
Counter({'c': 3, 'b': 2, 'a': 1})
['a', 'b', 'b', 'c', 'c', 'c']

```

**most _ common():**
most _ common()用于生成 n 个最常遇到的输入值及其各自计数的序列。

```
# Python example to demonstrate most_elements() on
# Counter
from collections import Counter

coun = Counter(a=1, b=2, c=3, d=120, e=1, f=219)

# This prints 3 most frequent characters
for letter, count in coun.most_common(3):
    print('%s: %d' % (letter, count))
```

 **输出:**

```
f: 219
d: 120
c: 3

```

本文由 **Mayank Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。