# Python |不使用递归的按字典顺序排列的字符串的所有排列

> 原文:[https://www . geesforgeks . org/python-不使用递归的字典序字符串全排列/](https://www.geeksforgeeks.org/python-all-permutations-of-a-string-in-lexicographical-order-without-using-recursion/)

编写一个 python 程序，按照字典顺序打印字符串的所有排列。

**示例:**

```
Input  : python
Output : hnopty
hnopyt
hnotpy
hnotyp
hnoypt
......
ytpnho
ytpnoh
ytpohn
ytponh

Input  : xyz
Output : xyz
xzy
yxz
yzx
zxy
zyx

```

**方法 1:**
使用默认库 itertools 函数排列。
排列函数将创建给定字符串的所有排列，然后我们对结果进行排序，以获得我们想要的输出。

```
from itertools import permutations

def lexicographical_permutation(str):
    perm = sorted(''.join(chars) for chars in permutations(str))
    for x in perm:
        print(x)

str ='abc'
lexicographical_permutation(str)
```

**输出:**

```
abc
acb
bac
bca
cab
cba
```

**方法二:**

*   首先我们创建一个循环，它将运行 n！其中 n 是字符串的长度，因为将有 n！排列。*   每次迭代都会打印字符串，并在下一次迭代中找到要打印的下一个更大的字典排列。*   下一个更高的排列如下*   假设这个字符串叫做 str，找到最小的索引 I，这样 str[i…end]中的所有元素都是降序的。*   如果 str[i…end]是整个序列，即 i == 0，那么 str 就是最高置换。所以我们简单地反转整个字符串，得到最小的排列，我们认为这是下一个排列。*   如果 i > 0，那么我们反转 str[i…end]。*   然后我们寻找 str[i…end]中大于 str[I–1]的最小元素，并用 str[I–1]交换它的位置。*   This is then the next permutation.

    ```
    # import library
    from math import factorial

    def lexicographical_permutations(str):

        # there are going to be n ! permutations where n = len(seq)
        for p in range(factorial(len(str))):         
            print(''.join(str))  

            i = len(str) - 1

            # find i such that str[i:] is the largest sequence with
            # elements in descending lexicographic order
            while i > 0 and str[i-1] > str[i]:       
                i -= 1

            # reverse str[i:]
            str[i:] = reversed(str[i:]) 

            if i > 0:

                q = i
                # find q such that str[q] is the smallest element
                # in str[p:] such that str[q] > str[i - 1]
                while str[i-1] > str[q]:  
                    q += 1

                # swap str[i - 1] and str[q]
                temp = str[i-1] 
                str[i-1]= str[q]
                str[q]= temp

    s = 'abcd'
    s = list(s)
    s.sort()
    lexicographical_permutations(s)
    ```

    **输出:**

    ```
    abcd
    abdc
    acbd
    acdb
    adbc
    adcb
    bacd
    badc
    bcad
    bcda
    bdac
    bdca
    cabd
    cadb
    cbad
    cbda
    cdab
    cdba
    dabc
    dacb
    dbac
    dbca
    dcab
    dcba
    ```