# Python |求数组中给定和的唯一子集个数

> 原文:[https://www . geeksforgeeks . org/python-查找数组中给定和的唯一子集数/](https://www.geeksforgeeks.org/python-find-the-number-of-unique-subsets-with-given-sum-in-array/)

给定一个数组和一个和，求唯一子集的个数，每个子集的和等于给定的和值。

**示例:**

```py
Input : 
4 12 5 9 12
9
Output :
2
(subsets will be [4, 5] and [9])

Input :
1 2 3 4 5
10
Output :
3

```

我们将使用动态规划来解决这个问题，并且这个解决方案具有 O(n <sup>2</sup> 的时间复杂度。以下是代码中使用的`dp[][]`—

```py
   _ | 4 12  5  9 12 
   0 |[1, 1, 1, 1, 1] 
   1 |[0, 0, 0, 0, 0] 
   2 |[0, 0, 0, 0, 0] 
   3 |[0, 0, 0, 0, 0]
   4 |[1, 1, 1, 1, 1] 
   5 |[0, 0, 1, 1, 1] 
   6 |[0, 0, 0, 0, 0] 
   7 |[0, 0, 0, 0, 0] 
   8 |[0, 0, 0, 0, 0] 
   9 |[0, 0, 1, 2, 2]
```

下面是 Python 代码:

```py
# Python code to find the number of unique subsets
# with given sum in the given array

def help(a,s):

        dp = [[0 for i in range(len(a))] for j in range(0,s+1)]
        for i in range(len(a)):
            dp[0][i] = 1
        for i in range(1,s+1):
            if i == a[0]:
                dp[i][0] = 1
        for i in range(1, s+1):
            for j in range(1, len(a)):
                if a[j]<=i:
                        dp[i][j] = dp[i][j-1] + dp[i-a[j]][j-1]
                else:
                        dp[i][j] = dp[i][j-1]
        return dp[s][len(a)-1]

# driver code
a = [4, 12, 5, 9, 12]
s = 9

print(help(a,s))
```

**输出:**

```py
2

```