# Python |计数因子小于等于给定 x 的因子的数组元素

> 原文:[https://www . geeksforgeeks . org/python-用小于或等于给定 x 因子的因子对数组元素进行计数/](https://www.geeksforgeeks.org/python-count-the-array-elements-with-factors-less-than-or-equal-to-the-factors-of-given-x/)

给定一个数组，任务是对因子小于给定数 **x** 的数组元素进行计数。

**示例:**

> **输入:** arr = [2，12，4，6]，x = 6
> **输出:** 2
> 因子 x = 6 为[1，2，3]
> 因子 arr[0] = 2 为[1]
> 因子 arr[1] = 12 为[1，2，3，4]
> 因子 arr[2] = 4 为[1，2]
> 因子 arr[3] = 6 为[1，2，3]
> 
> 所以只有 arr[0]和 arr[2]是答案。

**方法:**
找出所有元素的因子和给定的 **x** 的因子，如果元素的因子小于 x 的因子，则比较所有的因子，然后增加计数。

**以下是上述问题的实现–**

```py
from math import ceil, sqrt

# function to count the factors of an array
def factorscount(x):
    count = 0
    for i in range(1,ceil(sqrt(x))):
        if x%i==i:
            count+=1
        else:
            count+=2
    return count

def Totalcount(arr, x):

    # count of factors of  given x
    count_fac = factorscount(x)

    # store the count of each factors
    arr_fac = [factorscount(i) for i in arr]

    ans = 0

    for i in arr_fac:
        # if factors count of element of array is
        #small than that of given number
        if i<count_fac:
            ans+=1

    return ans

# Driver code

arr = [2,12,4,6]
x = 6
print(Totalcount(arr, x))
```

**Output:**

```py
2

```