# 程序打印给定数字的所有可被 5 或 7 整除的数字

> 原文:[https://www . geesforgeks . org/program-to-print-all-the-numbers-除尽-5 或-7-对于给定的数字/](https://www.geeksforgeeks.org/program-to-print-all-the-numbers-divisible-by-5-or-7-for-a-given-number/)

给定整数 N，任务是打印所有小于 N 的数字，这些数字可以被 5 或 7 整除。

**例:**

```py
Input : 20
Output : 5 7 10 14 15 20 

Input: 50
Output: 5 7 10 14 15 20 21 25 28 30 35 40 42 45 49 50
```

**逼近:**比如我们以 N = 20 为极限，那么程序应该打印出所有小于 20 且能被 5 或 7 整除的数字。为此，将从 0 到 N 的每个数字除以 5 和 7，并检查它们的余数。如果两种情况下的余数都是 0，那么只需打印该数字。

下面是实现:

## c++

```py
// C++ program to print all the numbers
// divisible by 5 or 7 for a given number
# include<bits/stdc++.h>
using namespace std;

// Result generator with N
int NumGen(int n)
{

    // Iterate from 0 to N
    for(int j = 1; j < n + 1; j++)
    {

        // Short-circuit operator is used
        if (j % 5 == 0 || j % 7 == 0)
            cout << j << " ";
    }
    return n;
}

// Driver code
int main()
{
    // Input goes here
    int N = 50;

    // Iterating over generator function
    NumGen(N);

    return 0;
}

// This code is contributed by Code_Mech
```

## Java

```py
// Java program to print all the numbers
// divisible by 5 or 7 for a given number
import java.util.*;

class GFG{

// Result generator with N
static int NumGen(int n)
{

    // Iterate from 0 to N
    for(int j = 1; j < n + 1; j++)
    {

       // Short-circuit operator is used
       if (j % 5 == 0 || j % 7 == 0)
           System.out.print(j + " ");
    }
    return n;
}

// Driver code
public static void main(String args[])
{
    // Input goes here
    int N = 50;

    // Iterating over generator function
    NumGen(N);
}
}

// This code is contributed by AbhiThakur
```

## python 3

T2

## c#

```py
// C# program to print all the numbers
// divisible by 5 or 7 for a given number
using System;

class GFG{

// Result generator with N
static int NumGen(int n)
{

    // Iterate from 0 to N
    for(int j = 1; j < n + 1; j++)
    {

       // Short-circuit operator is used
       if (j % 5 == 0 || j % 7 == 0)
           Console.Write(j + " ");
    }
    return n;
}

// Driver code
public static void Main()
{

    // Input goes here
    int N = 50;

    // Iterating over generator
    // function
    NumGen(N);
}
}

// This code is contributed by Code_Mech
```

T21

## Javascript

T4T26】

**输出:**

```py
5 7 10 14 15 20 21 25 28 30 35 40 42 45 49 50 
```

**时间复杂度:** O(N)

**辅助空间:** O(1)