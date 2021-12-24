# 创建一个 n×n 的正方形矩阵，其中所有子矩阵的对角元素之和为偶数

> 原文:[https://www . geeksforgeeks . org/create-an-n-x-n-square-matrix-其中所有子矩阵都有对角元素之和作为偶数/](https://www.geeksforgeeks.org/create-an-n-x-n-square-matrix-where-all-the-sub-matrix-have-the-sum-of-opposite-corner-elements-as-even/)

给定一个整数 n，任务是生成一个由**(n×n)**组成的**方阵**,其元素范围从 1 到 n^2，条件如下:

*   矩阵的元素应该是不同的，即只使用一次
*   从 1 到 n^2 的数字
*   您选择的每个子矩阵都应该具有偶数的对角元素的和，即左上和右下元素的和应该是偶数，右上和左下元素的和应该是偶数

这个属性应该适用于矩阵的所有子矩阵。你需要生成一个**偶数子矩阵**

**示例:**

> **输入:**2
> T3】输出:1 2
> 4 3
> T7】说明:这里 1+3=4 的和为偶数，2+4=6 为偶数
> 
> **输入:**4
> T3】输出:1 2 3
> 4 5 6
> 7 8 9
> T8】说明:子矩阵[1 2 4 5]，[2 3 5 6]，[4 5 7 8]，[5 6 8 9]，[1 2 3 4 5 6 7 8 9]满足对角
> 元素具有偶和的条件

**进场:**

正如我们所知，任何两个元素之和为偶数，它可以是奇数和奇数之和或偶数和偶数之和。在两种情况中的任何一种情况下，角元素之和为偶数，我们需要确保对角线模式排列的元素应为奇数或偶数。因此，我们把有对角线的二维数组作为全奇数或全偶数，以找到角元素和为偶数的子矩阵。同样可以遵循下面的方法。

*   当 n 是奇数时，对角线已经在所有奇数或偶数元素中，因此我们不需要修改和生成简单的 2d 阵列
*   当 n 为偶数时，生成的矩阵不满足子矩阵的对角元素具有偶数和的性质，因此我们反转交替行元素，使得每个子矩阵的对角线或者全奇数或者全偶数。

下面是实现。

## C++

```
// C++ program for
// the above approach
#include <bits/stdc++.h>
using namespace std;

void sub_mat_even(int N)
{
  // Counter to initialize
  // the values in 2-D array
  int K = 1;

  // To create a 2-D array
  // from to 1 to N*2
  int A[N][N];

  for(int i = 0; i < N; i++)
  {
    for(int j = 0; j < N; j++)
    {
      A[i][j] = K;
      K++;
    }
  }

  // If found even we reverse
  // the alternate row elements
  // to get all diagonal elements
  // as all even or all odd
  if(N % 2 == 0)
  {
    for(int i = 0; i < N; i++)
    {
      if(i % 2 == 1)
      {
        int s = 0;
        int l = N - 1;

        // Reverse the row
        while(s < l)
        {
          swap(A[i][s],
               A[i][l]);
          s++;
          l--;
        }
      }
    }
  }

  // Print the formed array
  for(int i = 0; i < N; i++)
  {
    for(int j = 0; j < N; j++)
    {
      cout << A[i][j] << " ";
    }
    cout << endl;
  }
}

// Driver code
int main()
{
    int N = 4;

    // Function call
    sub_mat_even(N);
}

// This code is contributed by mishrapriyanshu557
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for
// the above approach
import java.io.*;

class GFG{

static void sub_mat_even(int N)
{

    // Counter to initialize
    // the values in 2-D array
    int K = 1;

    // To create a 2-D array
    // from to 1 to N*2
    int[][] A = new int[N][N];

    for(int i = 0; i < N; i++)
    {
        for(int j = 0; j < N; j++)
        {
            A[i][j] = K;
            K++;
        }
    }

    // If found even we reverse
    // the alternate row elements
    // to get all diagonal elements
    // as all even or all odd
    if (N % 2 == 0)
    {
        for(int i = 0; i < N; i++)
        {
            if (i % 2 == 1)
            {
                int s = 0;
                int l = N - 1;

                // Reverse the row
                while (s < l)
                {
                    swap(A[i], s, l);
                    s++;
                    l--;
                }
            }
        }
    }

    // Print the formed array
    for(int i = 0; i < N; i++)
    {
        for(int j = 0; j < N; j++)
        {
            System.out.print(A[i][j] + " ");
        }
        System.out.println();
    }
}

private static void swap(int[] A, int s, int l)
{
    int temp = A[s];
    A[s] = A[l];
    A[l] = temp;
}

// Driver code
public static void main(String[] args)
{
    int N = 4;

    // Function call
    sub_mat_even(N);
}
}

// This code is contributed by jithin
```

## 蟒蛇 3

```
# Python3 program for
# the above approach
import itertools

def sub_mat_even(n):

    temp = itertools.count(1)

    # create a 2d array ranging
    # from 1 to n^2
    l = [[next(temp)for i in range(n)]for i in range(n)]

    # If found even we reverse the alternate
    # row elements to get all diagonal elements
    # as all even or all odd
    if n%2 == 0:
        for i in range(0,len(l)):
            if i%2 == 1:
                l[i][:] = l[i][::-1]

    # Printing the array formed
    for i in range(n):
        for j in range(n):
            print(l[i][j],end=" ")
        print()

n = 4
sub_mat_even(n)
```

## C#

```
// C# program for
// the above approach
using System;
class GFG {

    static void sub_mat_even(int N)
    {

        // Counter to initialize
        // the values in 2-D array
        int K = 1;

        // To create a 2-D array
        // from to 1 to N*2
        int[,] A = new int[N, N];

        for(int i = 0; i < N; i++)
        {
            for(int j = 0; j < N; j++)
            {
                A[i, j] = K;
                K++;
            }
        }

        // If found even we reverse
        // the alternate row elements
        // to get all diagonal elements
        // as all even or all odd
        if (N % 2 == 0)
        {
            for(int i = 0; i < N; i++)
            {
                if (i % 2 == 1)
                {
                    int s = 0;
                    int l = N - 1;

                    // Reverse the row
                    while (s < l)
                    {
                        int temp = A[i, s];
                        A[i, s] = A[i, l];
                        A[i, l] = temp;
                        s++;
                        l--;
                    }
                }
            }
        }

        // Print the formed array
        for(int i = 0; i < N; i++)
        {
            for(int j = 0; j < N; j++)
            {
                Console.Write(A[i, j] + " ");
            }
            Console.WriteLine();
        }
    }

  static void Main() {

    int N = 4;

    // Function call
    sub_mat_even(N);
  }
}

// This code is contributed by divyeshrabadiya07
```

**输出:**

```
1 2 3 4
8 7 6 5
9 10 11 12
16 15 14 13
```

这种方法需要 0(n * 2)的时间复杂度。