# 尽量减少要分发的 teddies 总数

> 原文:[https://www . geeksforgeeks . org/最小化待分发的 teddies 总数/](https://www.geeksforgeeks.org/minimize-the-total-number-of-teddies-to-be-distributed/)

给定 N 个坐在一条线上的学生，他们每个人都在考试中得了分。任务是分发满足给定条件的泰迪熊

1.  所有学生必须至少有一个泰迪熊
2.  如果两个学生挨着坐，那么分数高的那一个一定会得到更多的泰迪。

所以，任务是最小化泰迪熊的总数。
**例** :

```
Input: n = 3, marks = [ 1, 2, 2 ]
Output: 4
Here 1, 2, 2 is the marks. 
Note that when two students have equal marks 
they are allowed to have a different number of teddies. 
Hence optimal distribution will be 1, 2, 1.

Input: n = 6, marks = [ 1, 4, 5, 2, 2, 1 ]
Output: 10
```

**方法:**方法是用动态规划求解给定问题:

1.  初始化大小为 n 的表。
2.  循环运行 n 次。
3.  如果左邻的学生分数较高，请检查并更改之前作为解决方案分配的所有表值，直到根据给定的约束发现作为解决方案分配的表值错误。
4.  如果右边相邻的学生分数较高，则在左边相邻的解中加一，并分配给右边的解。

以下是上述方法的实现:

## C++

```
// C++ implementation of the
// above approach
#include<bits/stdc++.h>
using namespace std;

long long fun(int marks[],int n)
{
    // Initializing one tablet
    // for each student
    long long dp[n], temp;
    fill(dp, dp + n, 1);

    for(int i = 0; i < n - 1; i++)
    {
        // if left adjacent is having
        // higher marks review and change
        // all the dp values assigned before
        // until assigned dp values are found
        // wrong according to given constrains
        if (marks[i] > marks[i + 1])
        {
            temp = i;
            while (true)
            {
                if ((marks[temp] > marks[temp + 1]) &&
                                         temp >= 0)
                {
                    if (dp[temp] > dp[temp + 1])
                    {
                        temp -= 1;
                        continue;
                    }
                    else
                    {
                        dp[temp] = dp[temp + 1] + 1;
                        temp -= 1;
                    }
                }                    
                else
                    break;
            }
        }

        // if right adjacent is having higher
        // marks add one in dp of left adjacent
        // and assign to right one
        else if( marks[i] < marks[i + 1])
            dp[i + 1] = dp[i] + 1;
    }

    int sum = 0;

    for(int i = 0; i < n; i++)
    sum += dp[i];

    return sum;
}

// Driver Code
int main()
{
    // n number of students
    int n = 6;

    // marks of students
    int marks[6] = { 1, 4, 5, 2, 2, 1};

    // solution of problem
    cout << fun(marks, n);

    return 0;
}

// This code is contributed by ash264
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the
// above approach

public class GFG {

    static long fun(int marks[],int n)
    {
        // Initializing one tablet 
        // for each student
        long dp[] = new long[n] ;
        int temp;

        for (int i = 0;i < n;i ++)
            dp[i] = 1 ;

        for(int i = 0; i < n - 1; i++)
        {
            // if left adjacent is having 
            // higher marks review and change 
            // all the dp values assigned before
            // until assigned dp values are found 
            // wrong according to given constrains
            if (marks[i] > marks[i + 1])
            { 
                temp = i;
                while (true)
                {
                    if ((marks[temp] > marks[temp + 1]) && 
                                             temp >= 0)
                    {
                        if (dp[temp] > dp[temp + 1])
                        {
                            temp -= 1;
                            continue;
                        }
                        else
                        {
                            dp[temp] = dp[temp + 1] + 1;
                            temp -= 1;
                        }
                    }                    
                    else
                        break; 
                } 
            }

            // if right adjacent is having higher
            // marks add one in dp of left adjacent
            // and assign to right one
            else if( marks[i] < marks[i + 1])
                dp[i + 1] = dp[i] + 1;
        }

        int sum = 0;

        for(int i = 0; i < n; i++)
        sum += dp[i];

        return sum;
    }

    public static void main(String args[])
    {
        // n number of students
        int n = 6;

        // marks of students
        int marks[] = { 1, 4, 5, 2, 2, 1};

        // solution of problem
        System.out.println(fun(marks, n));
    }
    // This code is contributed by ANKITRAI1
}
```

## 蟒蛇 3

```
# Python implementation of the above approach

def fun(marks, n):
    # Initializing one tablet for each student
    dp = [ 1 for i in range(0, n) ]

    for i in range(0, n-1):

        # if left adjacent is having higher marks
        # review and change all the dp values assigned before
        # until assigned dp values are found wrong
        # according to given constrains
        if marks[i] > marks[i + 1]:
            temp = i
            while True:
                if marks[temp] > marks[temp + 1] and temp >= 0:
                    if dp[temp] > dp[temp + 1]:
                        temp -= 1
                        continue
                    else:
                        dp[temp] = dp[temp + 1] + 1
                        temp -= 1                       
                else:
                    break   

        # if right adjacent is having higher marks
        # add one in dp of left adjacent and assign to right one
        elif marks[i] < marks[i + 1]:
            dp[i + 1] = dp[i] + 1

    return(sum(dp))

# driver code

# n number of students
n = 6

# marks of students
marks = [ 1, 4, 5, 2, 2, 1]

# solution of problem
print(fun(marks, n))
```

## C#

```
// C# implementation of the
// above approach
using System;

class GFG
{
    public static long fun(int[] marks,int n)
    {
        // Initializing one tablet 
        // for each student
        long[] dp = new long[n];
        long temp;

        for(int i = 0; i < n; i++)
            dp[i] = 1;

        for(int i = 0; i < n - 1; i++)
        {
            // if left adjacent is having 
            // higher marks review and change 
            // all the dp values assigned before
            // until assigned dp values are found 
            // wrong according to given constrains
            if (marks[i] > marks[i + 1])
            { 
                temp = i;
                while (true)
                {
                    if ((marks[temp] > marks[temp + 1]) && 
                                             temp >= 0)
                    {
                        if (dp[temp] > dp[temp + 1])
                        {
                            temp -= 1;
                            continue;
                        }
                        else
                        {
                            dp[temp] = dp[temp + 1] + 1;
                            temp -= 1;
                        }
                    }                     
                    else
                        break; 
                } 
            }

            // if right adjacent is having higher
            // marks add one in dp of left adjacent
            // and assign to right one
            else if( marks[i] < marks[i + 1])
                dp[i + 1] = dp[i] + 1;
        }

        long sum = 0;

        for(int i = 0; i < n; i++)
            sum += dp[i];

        return sum;
    }

    // Driver Code
    static void Main()
    {
        // n number of students
        int n = 6;

        // marks of students
        int[] marks = new int[]{ 1, 4, 5, 2, 2, 1};

        // solution of problem
        Console.Write( fun(marks, n) ); 
    }
    //This code is contributed by DrRoot_
}
```

## java 描述语言

```
<script>
    // Javascript implementation of the above approach

    function fun(marks, n)
    {
        // Initializing one tablet 
        // for each student
        let dp = new Array(n);
        let temp;

        for(let i = 0; i < n; i++)
            dp[i] = 1;

        for(let i = 0; i < n - 1; i++)
        {
            // if left adjacent is having 
            // higher marks review and change 
            // all the dp values assigned before
            // until assigned dp values are found 
            // wrong according to given constrains
            if (marks[i] > marks[i + 1])
            { 
                temp = i;
                while (true)
                {
                    if ((marks[temp] > marks[temp + 1]) && 
                                             temp >= 0)
                    {
                        if (dp[temp] > dp[temp + 1])
                        {
                            temp -= 1;
                            continue;
                        }
                        else
                        {
                            dp[temp] = dp[temp + 1] + 1;
                            temp -= 1;
                        }
                    }                     
                    else
                        break; 
                } 
            }

            // if right adjacent is having higher
            // marks add one in dp of left adjacent
            // and assign to right one
            else if( marks[i] < marks[i + 1])
                dp[i + 1] = dp[i] + 1;
        }

        let sum = 0;

        for(let i = 0; i < n; i++)
            sum += dp[i];

        return sum;
    }

    // n number of students
    let n = 6;

    // marks of students
    let marks = [ 1, 4, 5, 2, 2, 1];

    // solution of problem
    document.write( fun(marks, n) ); 

// This code is contributed by divyesh072019.
</script>
```

**Output:** 

```
10
```