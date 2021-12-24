# 用 Python 打印字符串的所有子序列

> 原文:[https://www . geeksforgeeks . org/print-python 中字符串的所有子序列/](https://www.geeksforgeeks.org/print-all-subsequences-of-a-string-in-python/)

给定一个字符串，我们必须找出它的所有子序列。字符串是给定字符串的子序列，它是通过删除给定字符串的某些字符而不改变其顺序来生成的。
示例:

```
Input : abc
Output : a, b, c, ab, bc, ac, abc

Input : aaa
Output : a, aa, aaa

```

**使用拾取和不拾取概念** **:**

## 蟒蛇 3

```
def printSubSequences(STR, subSTR=""):
    """
    function:
        To print all subsequences of string
        concept:
            Pick and Don’t Pick
        variables:
            STR = string
            subSTR = to store subsequence
    """
    if len(STR) == 0:
        print(subSTR, end=" ")
        return

    # we add adding 1st character in string
    printSubSequences(STR[:-1], subSTR + STR[-1])
    """
    Not adding first character of the string
    because the concept of subsequence either
    character will present or not
    """
    printSubSequences(STR[:-1], subSTR)
    return

def main():
    """
    main function to drive code
    """
    STR = "abc"
    printSubSequences(STR)

if __name__ == "__main__":
    main()

# by itsvinayak
```

**输出:**

```
cba cb ca c ba b a  
```

**python 实现:**

先决条件:[Python 中的 itertools.combinations()模块打印所有可能的组合](https://www.geeksforgeeks.org/itertools-combinations-module-python-print-possible-combinations/)

## 蟒蛇 3

```
# Python Implementation of the approach
import itertools

def Sub_Sequences(STR):
    combs = []
    for l in range(1, len(STR)+1):
        combs.append(list(itertools.combinations(STR, l)))
    for c in combs:
        for t in c:
            print (''.join(t), end =' ')

# Testing with driver code
if __name__ == '__main__':
    Sub_Sequences('abc')
```

**Output:** 

```
a b c ab ac bc abc

```