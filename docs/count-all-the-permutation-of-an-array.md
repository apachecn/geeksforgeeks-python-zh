# 计算一个数组的所有排列

> 原文:[https://www . geesforgeks . org/count-all-of-array/](https://www.geeksforgeeks.org/count-all-the-permutation-of-an-array/)

给定一个没有重复元素的整数数组 A[]，编写一个函数，为数组 A[]中的每个 I 返回没有子数组[i，i+1]的数组的所有排列的计数。

**示例:**

```
Input  : 1 3 9 
Output : 3
All the permutation of 1 3 9 are : 
[1, 3, 9], [1, 9, 3], [3, 9, 1], [3, 1, 9], [9, 1, 3], [9, 3, 1]
Here [1, 3, 9], [9, 1, 3] are removed as they contain subarray 
[1, 3] from original list and [3, 9, 1] removed as it contains 
subarray [3, 9] from original list so, 
Following are the 3 arrays that satisfy the condition : 
[1, 9, 3], [3, 1, 9], [9, 3, 1]

Input  : 1 3 9 12
Output : 11

```

**天真解决方案:**遍历所有排列的列表，从**A【】**中移除包含任何子阵列**【I，I+1】**的那些阵列。

**代码:找出数组中排列的 Python 代码**

```
# Python implementation of the approach
from itertools import permutations

# Function that returns the count of all the permutation
# having no subarray of [i,i+1]

def count(arr):
    z=[]
    perm = permutations(arr)

    for i in list(perm):
        z.append(list(i))
    q=[]

    for i in range(len(arr)-1):
        x,y=arr[i],arr[i+1]

        for j in range(len(z)):
            if z[j].index(x)!=len(z[j])-1:
                if z[j][z[j].index(x)+1]==y:
                    q.append(z[j])

    for i in range(len(q)):
         if q[i] in z:
             z.remove(q[i])
    return len(z)

# Driver Code
A = [1,3, 8, 9]
print(count(A))
```

**输出:**

```
11
```

**有效解:**以下是基于以下事实的递归解:阵列的长度决定了没有子阵列的所有排列的数量**【I，I+1】**对于**A【】**中的每个 I

假设 A[ ]的长度是 n，那么

```
n        = n-1
count(0) = 1
count(1) = 1
count(n) = n * count(n-1) + (n-1) * count(n-2)
```

**代码:下面是实现返回排列计数的递归函数**
的代码

## C++

```
// C++ implementation of the approach
// Recursive function that return count of 
// permutation based on the length of array.
#include <bits/stdc++.h>
using namespace std;

int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) + 
                        ((n - 1) * count(n - 2));
}

// Driver code
int main()
{
    int A[] = {1, 2, 3, 9};

    int len = sizeof(A) / sizeof(A[0]);
    cout << count(len - 1);
}

// This code is contributed by 29AjayKumar
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
// Recursive function that return count of 
// permutation based on the length of array.
import java.util.*;

class GFG
{

static int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) + 
                        ((n - 1) * count(n - 2));
}

// Driver Code
static public void main(String[] arg) 
{
    int []A = {1, 2, 3, 9};

    System.out.print(count(A.length - 1));
}
}

// This code is contributed by PrinciRaj1992
```

## 蟒蛇 3

```
# Python implementation of the approach
# Recursive function that return count of 
# permutation based on the length of array.

def count(n):
    if n == 0:
        return 1
    if n == 1:
        return 1
    else:
        return (n * count(n-1)) + ((n-1) * count(n-2))

# Driver Code
A = [1, 2, 3, 9]
print(count(len(A)-1))
```

## C#

```
// C# implementation of the approach
// Recursive function that return count of 
// permutation based on the length of array.
using System;

class GFG
{

static int count(int n)
{
    if(n == 0)
        return 1;
    if(n == 1)
        return 1;
    else
        return (n * count(n - 1)) + 
         ((n - 1) * count(n - 2));
}

// Driver Code
static public void Main(String[] arg) 
{
    int []A = {1, 2, 3, 9};

    Console.Write(count(A.Length - 1));
}
}

// This code is contributed by Princi Singh
```

**输出:**

```
11
```