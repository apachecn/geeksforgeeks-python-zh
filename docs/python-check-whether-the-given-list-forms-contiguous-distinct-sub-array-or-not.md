# Python–检查给定列表是否形成连续的不同子数组

> 原文:[https://www . geesforgeks . org/python-check-给定列表-表单-连续-不同-子数组-or-not/](https://www.geeksforgeeks.org/python-check-whether-the-given-list-forms-contiguous-distinct-sub-array-or-not/)

给你一个由 A1、A2、A3……an 形式的元素组成的数组，任务是找出该数组是否可以形成为**连续的不同子数组**。您需要找到数组是否可以转换为由相似元素组成的连续子数组，并且每个元素都有不同的数量。

曾经遇到的元素不应出现在数组的后面，因为它不是连续的

**示例:**

> **输入:*****【**1 1 3 6 6】*
> **输出:** *是*
> **解释:**
> *的给定元素可以以[1，1] [3] [6，6，6 ]的形式转换为连续相异集合数组，也可以是*
> *1 的数量= 2 个*
> *3 的数量*
> 
> **输入:***【1 1 3 5 2 2 3】*
> **输出:** *否*
> **解释:**
> *的给定元素不能转换为 continental Distinct Set Array 作为子数组【3 5 2 2 2 3】*
> *违反条件(元素需要是连续的)3 再次出现在 5 和 2 之后。*
> 
> **输入*****:**【9 9 4 4 1 6】*
> **输出:** *否*
> **解释:**
> *的给定元素不能转换为连续的相异集合数组*
> *它的形式是【9，9】【4，4，4】【1】【6】， [6]所以元素是连续存在的*
> *但是 9 的数量=2，这也等于 6 的数量=2*
> *因此数组中不同元素的数量不是截然不同的*
> *因此答案是否定的*

**解决方案:**

## 蟒蛇 3

```py
from collections import Counter

# function to check contiguous
# distinct set array
def contig_distinct_setarr(l, n):

    c = Counter(l)
    a = list(set(l))

    b =[]
    flag = True

    for j in c.values():

        # iterating and moving it to another
        # array if already present we print NO
        # when it finds no. of different elements
        # to be equal if no. of x's = no. of y's
        # So we break of the loop
        if j not in b:
            b.append(j)
        else:
            print("NO")
            flag = False
            break

    # If already there are similar elements
    # in c.values()- the count of elements
    # flag = False and we dont need to check
    # the below condition If not flag = False
    # then the iterate through the array loop
    if (flag != False):
        i, k = 0, 0

        # for each elements in set a
        # cou stores the count of a[i]
        while k<len(a):
            cou = c[a[i]]
            x = l.index(a[i])

            # here we extract thecontiguous
            # sub array of length equal to
            # the count of the element
            temp =(l[x:x + cou])

            # if the number of elements of
            # subsequences is not equal to
            # the value of element in the
            # dictionary print NO
            if len(temp) != c[a[i]]:
                print("NO")
                flag = False
                break

            k+= 1
            i+= 1

        # if we have iterated all over the array
        # and the condition is satisfied we print
        # YES
        if flag == True:
            print("YES")
# initialize the array and its length
n = 6
l =[1, 1, 3, 6, 6, 6]
contig_distinct_setarr(l, n)
```

**输出:**

```py
YES
```