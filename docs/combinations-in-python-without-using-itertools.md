# 不使用 itertools 的 Python 组合

> 原文:[https://www . geesforgeks . org/不使用 itertools 的 python 组合/](https://www.geeksforgeeks.org/combinations-in-python-without-using-itertools/)

[Python 中的 Itertools](https://www.geeksforgeeks.org/python-itertools/) 是一个在迭代器上工作的方法的帮助下产生复杂迭代器的模块。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

### 使用 itertools 打印组合

使用 Itertools，我们可以以一种非常优化的方式显示字符串的所有可能组合。要显示组合，需要 2 个参数。第一个是字符串，第二个是所需子字符串的长度。以下示例使用 itertools 对字符串“abc”进行所有组合。
**例:**

## 蟒蛇 3

```py
# Import combinations from itertools
from itertools import combinations

def n_length_combo(arr, n):

    # using set to deal
    # with duplicates 
    return list(combinations(arr, n))

# Driver Function
if __name__ == "__main__":
    arr = 'abc'
    n = 2
    print (n_length_combo([x for x in arr], n) )
```

**输出**

```py
[('a', 'b'), ('a', 'c'), ('b', 'c')]
```

### 不使用工具打印组合

*   **通过使用递归。**
    要在不使用 itertools 的情况下创建组合，请逐个迭代列表并修复列表的第一个元素，然后与剩余列表进行组合。同样，通过递归剩余的列表，逐个迭代所有列表元素。

## 蟒蛇 3

```py
# Function to create combinations
# without itertools
def n_length_combo(lst, n):

    if n == 0:
        return [[]]

    l =[]
    for i in range(0, len(lst)):

        m = lst[i]
        remLst = lst[i + 1:]

        for p in n_length_combo(remLst, n-1):
            l.append([m]+p)

    return l

# Driver code
if __name__=="__main__":
    arr ="abc"
    print(n_length_combo([x for x in arr], 2))
```

*   **输出**

```py
[('a', 'b'), ('a', 'c'), ('b', 'c')]
```

*   **通过使用迭代**
    在这种情况下，按原样返回字符串中 n 个元素的第一个组合，然后通过考虑每个元素的位置来进行其他组合。每个元素根据其位置而不是其值被视为唯一的。因此，如果输入元素是唯一的，那么在每个组合中都不会有重复值。

## 蟒蛇 3

```py
import numpy

def n_length_combo(iterable, r):

    char = tuple(iterable)
    n = len(char)

    if r > n:
        return

    index = numpy.arange(r)

    # returns the first sequence
    yield tuple(char[i] for i in index)

    while True:

        for i in reversed(range(r)):
            if index[i] != i + n - r:
                break
        else:
            return

        index[i] += 1

        for j in range(i + 1, r):

            index[j] = index[j-1] + 1

        yield tuple(char[i] for i in index)

# Driver code
print([x for x in n_length_combo("abc", 2)])
```

*   **输出**

```py
[('a', 'b'), ('a', 'c'), ('b', 'c')]
```