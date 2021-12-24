# 程序打印半菱形星形图案

> 原文:[https://www . geesforgeks . org/program-to-print-半菱形-star-pattern/](https://www.geeksforgeeks.org/program-to-print-half-diamond-star-pattern/)

给定一个整数 **N** ，任务是打印半菱形星图案。

> *
> * *
> * *
> * * *
> * * * * *
> * * * * * * *
> * * *
> * * *
> * * *
> * *
> *

**示例:**

```
Input: N = 3
Output:
*
**
***
**
*

Input: N = 6
Output:
*
**
***
****
*****
******
*****
****
***
**
*

```

**做法:**思路是将图案分成两半，即上半部分和下半部分。然后在[循环](https://www.geeksforgeeks.org/loops-in-c-and-cpp/)的帮助下单独打印。打印上半部和下半部的关键观察如下所述:

*   **上半部分:**图案的上半部分包含星**' ***按递增顺序排列，其中 i <sup>第</sup>行包含以下数量的星:

    ```
    Number of '*' in ith line = 

    ```

*   **Lower Half:** The lower half of the pattern contains star **‘*’** in decreasing order where i<sup>th</sup> line contains following number of star:

    ```
    Number of '*' in ith line = 

    ```

    下面是上述方法的实现:

    ## C++

    ```
    // C++ implementation to print the
    // half diamond star pattern

    #include <iostream>

    using namespace std;

    // Function to print the
    // half diamond star pattern
    void halfDiamondStar(int N)
    {
        int i, j;

        // Loop to print the upper half
        // diamond pattern
        for (i = 0; i < N; i++) {
            for (j = 0; j < i + 1; j++)
                cout << "*";
            cout << "\n";
        }

        // Loop to print the lower half
        // diamond pattern
        for (i = 1; i < N; i++) {
            for (j = i; j < N; j++)
                cout << "*";
            cout << "\n";
        }
    }

    // Driver Code
    int main()
    {
        int N = 5;

        // Function Call
        halfDiamondStar(N);
    }
    ```

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```
    // Java implementation to print the
    // half diamond star pattern
    import java.util.*;

    class GFG{

    // Function to print the
    // half diamond star pattern
    static void halfDiamondStar(int N)
    {
        int i, j;

        // Loop to print the upper half
        // diamond pattern
        for (i = 0; i < N; i++)
        {
            for (j = 0; j < i + 1; j++)
                 System.out.print("*");
            System.out.print("\n");
        }

        // Loop to print the lower half
        // diamond pattern
        for (i = 1; i < N; i++) 
        {
            for (j = i; j < N; j++)
                 System.out.print("*");
            System.out.print("\n");
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int N = 5;

        // Function Call
        halfDiamondStar(N);
    }
    }

    // This code is contributed by Rohit_ranjan
    ```

    ## 蟒蛇 3

    ```
    # Python3 implementation to print the 
    # half diamond star pattern 

    # Function to print the 
    # half diamond star pattern 
    def halfDiamondStar(N):

        # Loop to print the upper half 
        # diamond pattern 
        for i in range(N):

            for j in range(0, i + 1):
                print("*", end = "")
            print()

        # Loop to print the lower half 
        # diamond pattern 
        for i in range(1, N):

            for j in range(i, N):
                print("*", end = "")
            print()

    # Driver Code 
    N = 5; 

    # Function Call 
    halfDiamondStar(N);

    # This code is contributed by skylags
    ```

    ## C#

    ```
    // C# implementation to print the
    // half diamond star pattern
    using System;

    class GFG{

    // Function to print the
    // half diamond star pattern
    static void halfDiamondStar(int N)
    {
        int i, j;

        // Loop to print the upper half
        // diamond pattern
        for(i = 0; i < N; i++)
        {
           for(j = 0; j < i + 1; j++)
               Console.Write("*");
           Console.Write("\n");
        }

        // Loop to print the lower half
        // diamond pattern
        for(i = 1; i < N; i++) 
        {
           for(j = i; j < N; j++)
               Console.Write("*");
           Console.Write("\n");
        }
    }

    // Driver Code
    public static void Main(String[] args)
    {
        int N = 5;

        // Function Call
        halfDiamondStar(N);
    }
    }

    // This code is contributed by Rohit_ranjan
    ```

    **Output:**

    ```
    *
    **
    ***
    ****
    *****
    ****
    ***
    **
    *

    ```