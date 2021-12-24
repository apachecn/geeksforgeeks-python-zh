# 使数组所有元素相等的最小步数

> 原文:[https://www . geeksforgeeks . org/使数组所有元素相等的最小步骤数/](https://www.geeksforgeeks.org/minimum-number-of-steps-to-make-all-elements-of-array-equal/)

给定两个相同长度的数组 **A[]** 和 **B[]** ，任务是通过将元素替换为数组 B 中相应元素的差来找到使数组中所有元素相等所需的最小步数。
T5】注:如果不可能，打印-1。
**示例:**

> **输入:** A[] = {5，7，10，5，15} B[] = {2，2，1，3，5}
> **输出:** 8
> **解释:**
> 转换数组元素的步骤相等–
> **索引 0:** 5 不变，采取的步骤= 0
> **索引 1:**7–(2 * 1)= 5，采取的步骤= 1
> 【T16 采取的步骤= 5
> **指数 3:** 5 不变，采取的步骤= 0
> **指数 4:**15 –( 5 * 2)= 5，采取的步骤= 2
> 因此，所需的总步骤= 0 + 1 + 5 + 0 + 2 = 8
> 
> **输入:** A[] = {5，6}，B[] = {4，3}
> **输出:** -1
> **说明:**
> 不可能让数组所有元素相等。

**方法:**思路是找到数组元素可以收敛的值，这个值肯定会在 0 到数组最小值之间。以下是该方法的示例:

*   最初，将标志标记为 False，以检查数组是否可转换。
*   运行 while 循环，直到数组的最小值大于-1。
    *   迭代数组的索引，即从 0 到长度-1
    *   对于每个索引，检查数组 A 中该索引处的元素是否大于数组的最小值，如果是，则将数组元素 A[i]更新为 A[I]–B[I]。
    *   将步数增加 1。
    *   检查所有数组元素是否相等如果是，则将标志标记为真，并中断 while 循环
    *   否则，重复上述步骤来计算所需的总步骤数。
*   最后，检查标志是否为真，如果是，则数组是可转换的。

**举例说明:**
给定数组 be–A[]= { 5，7，10，5，15}，B[] = {2，2，1，3，5}

<figure class="table">

| 数组 A | 当前指数 | 数组 A 的最小值 | 步伐 | 评论 |
| --- | --- | --- | --- | --- |
| {5, 7, 10, 5, 15} | Zero | five | Zero | 不做手术！ |
| {5, 5, 10, 5, 15} | one | five | one | 数组元素被减去一次。7 – 2 = 5 |
| {5, 5, 9, 5, 15} | Two | five | Two | 数组元素被减去一次。10 – 1 = 9 |
| {5, 5, 8, 5, 15} | Two | five | three | 数组元素被减去一次。9 – 1 = 8 |
| {5, 5, 7, 5, 15} | Two | five | four | 数组元素被减去一次。8 – 1 = 7 |
| {5, 5, 6, 5, 15} | Two | five | five | 数组元素被减去一次。7 – 1 = 6 |
| {5, 5, 5, 5, 15} | Two | five | six | 数组元素被减去一次。6 – 1 = 5 |
| {5, 5, 5, 5, 10} | four | five | seven | 数组元素被减去一次。15 – 5 = 10 |
| {5, 5, 5, 5, 5} | four | five | eight | 数组元素被减去一次。10 – 5 = 5 |

</figure>

下面是上述方法的实现:

## C++

```
// C++ implementation to find the
// minimum number of steps to convert
// array by subtracting the corresponding
// element from array B
#include <bits/stdc++.h>
using namespace std;

// Function to find the minimum steps
void minimumSteps(int ar1[], int ar2[], int n)
{

    // Counter to store the steps
    int ans = 0;

    // Flag to check that
    // array is converted
    bool flag = true;

    // Loop until the minimum of the
    // array is greater than -1
    while (*min_element(ar1, ar1 + n) > -1)
    {
        int a = *min_element(ar1, ar1 + n);

        // Loop to convert the array
        // elements by subtraction
        for(int i = 0; i < n; i++)
        {
            if (ar1[i] != a)
            {
                ar1[i] -= ar2[i];
                ans += 1;
            }
        }

        set<int> s1(ar1, ar1 + n);

        // If the array is converted
        if (s1.size() == 1)
        {
            flag = false;
            cout << ans << endl;
            break;
        }
    }

    if (flag)
    {
        cout << -1 << endl;
    }
}

// Driver Code
int main()
{
    int n = 5;
    int ar1[] = { 5, 7, 10, 5, 15 };
    int ar2[] = { 1, 2, 1, 5, 5 };

    // Function call
    minimumSteps(ar1, ar2, n);

    return 0;
}

// This code is contributed by rutvik_56
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation to find the
// minimum number of steps to convert
// array by subtracting the corresponding
// element from array B
import java.util.*;
class GFG{

// Function to find the
// minimum steps
static void minimumSteps(int ar1[],
                         int ar2[],
                         int n)
{
  // Counter to store the steps
  int ans = 0;

  // Flag to check that
  // array is converted
  boolean flag = true;

  // Loop until the minimum of the
  // array is greater than -1
  while (Arrays.stream(ar1).min().getAsInt() > -1)
  {
    int a = Arrays.stream(ar1).min().getAsInt();

    // Loop to convert the array
    // elements by subtraction
    for(int i = 0; i < n; i++)
    {
      if (ar1[i] != a)
      {
        ar1[i] -= ar2[i];
        ans += 1;
      }
    }

    HashSet<Integer> s1 = new HashSet<>();
    for(int i = 0; i < n; i++)
    {
      s1.add(ar1[i]);
    }

    // If the array is converted
    if (s1.size() == 1)
    {
      flag = false;
      System.out.print(ans + "\n");
      break;
    }
  }

  if (flag)
  {
    System.out.print(-1 + "\n");
  }
}

// Driver Code
public static void main(String[] args)
{
  int n = 5;
  int ar1[] = {5, 7, 10, 5, 15};
  int ar2[] = {1, 2, 1, 5, 5};

  // Function call
  minimumSteps(ar1, ar2, n);
}
}

// This code is contributed by Princi Singh
```

## 蟒蛇 3

```
# Python3 implementation to find the
# minimum number of steps to convert
# array by subtracting the corresponding
# element from array B

# Function to find the minimum steps
def minimumSteps(ar1, ar2, n):

    # Counter to store the steps
    ans = 0

    # Flag to check that
    # array is converted
    flag = True

    # Loop until the minimum of the
    # array is greater than -1
    while min(ar1)>-1:
        a = min(ar1)

        # Loop to convert the array
        # elements by subtraction
        for i in range(n):
            if ar1[i]!= a:
                ar1[i]-= ar2[i]
                ans+= 1

        # If the array is converted
        if len(set(ar1))== 1:
            flag = False
            print(ans)
            break
    if flag:
        print(-1)

# Driver Code
if __name__ == "__main__":
    n = 5
    ar1 = [5, 7, 10, 5, 15]
    ar2 = [1, 2, 1, 5, 5]

    # Function Call
    minimumSteps(ar1, ar2, n)
```

## C#

```
// C# implementation to
// find the minimum number
// of steps to convert array
// by subtracting the
// corresponding element from
// array B
using System;
using System.Linq;
using System.Collections.Generic;
class GFG{

// Function to find the
// minimum steps
static void minimumSteps(int []ar1,
                         int []ar2,
                         int n)
{
  // Counter to store the steps
  int ans = 0;

  // Flag to check that
  // array is converted
  bool flag = true;

  // Loop until the minimum of the
  // array is greater than -1
  while (ar1.Min() > -1)
  {
    int a = ar1.Min();

    // Loop to convert the array
    // elements by subtraction
    for(int i = 0; i < n; i++)
    {
      if (ar1[i] != a)
      {
        ar1[i] -= ar2[i];
        ans += 1;
      }
    }

    HashSet<int> s1 = new HashSet<int>();

    for(int i = 0; i < n; i++)
    {
      s1.Add(ar1[i]);
    }

    // If the array is converted
    if (s1.Count == 1)
    {
      flag = false;
      Console.Write(ans + "\n");
      break;
    }
  }

  if (flag)
  {
    Console.Write(-1 + "\n");
  }
}

// Driver Code
public static void Main(String[] args)
{
  int n = 5;
  int []ar1 = {5, 7, 10, 5, 15};
  int []ar2 = {1, 2, 1, 5, 5};

  // Function call
  minimumSteps(ar1, ar2, n);
}
}

// This code is contributed by 29AjayKumar
```

**Output:** 

```
8
```

**性能分析:**

*   **时间复杂度:** **O(N <sup>2</sup> logN)** 和上面的方法一样，有两个循环来转换数组。外环取 0(N)，内环取 0(NlogN)，就像我们在内环中使用 set 一样。
*   **辅助空间:O(N)。**我们正在使用一个占用 O(N)个额外空间的集合。**T3】**