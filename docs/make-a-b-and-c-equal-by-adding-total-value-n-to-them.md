# 将 A、B 和 C 的总值 N 相加使其相等

> 原文:[https://www . geesforgeks . org/make-a-B-和-c-通过将总价值 n 相加等于它们/](https://www.geeksforgeeks.org/make-a-b-and-c-equal-by-adding-total-value-n-to-them/)

给定 3 个整数 **A、B 和 C** ，以及一个整数 **N** ，任务是在所有其他 3 个数字中分配 **N** ，使得在最后 **A = B = C** 。如果可以分发，则打印“是”，否则输出“否”。
**举例:**

> **输入:** A = 5，B = 3，C = 2，N = 8
> **输出:**是
> **说明:**
> 我们可以通过将 1 加到 A，3 加到 B，4 加到 C 来分配 N = 8，得到全部为 6。因此分布是可能的。
> **输入:** A = 10，B = 20，C = 15，N = 14
> **输出:**否
> **说明:**
> 在所有三个整数中分配 N 使其相等是不可能的。

**方法:**
要解决上面提到的问题，我们必须遵循下面给出的步骤:

*   从所有三个整数 A、B 和 c 中找出**最大值**，让它成为整数 *K*
*   将整数 K 乘以 3，然后用三个整数之和减去它。
*   检查那个数和 N 的差是否为 [**被 3**](https://www.geeksforgeeks.org/check-large-number-divisible-3-not/) 整除。
*   如果是，则输出“是”，否则无法分配号码。

以下是上述方法的实现:

## C++

```
// C++ program to distribute integer N
// among A, B, C such that they become equal
#include<bits/stdc++.h>
using namespace std;

void distributeN(int A, int B, int C, int n)
{
    // Find maximum among the three elements
    int max1 = max(A, B);
    int max2 = max(B, C);
    int maximum = max(max1, max2);

    // Summation of three elements
    int sum = A + B + C;
    int p = (3 * maximum) - sum;
    int diff = n - p;

    // Check if difference is divisible by 3
    if (diff < 0 || diff % 3)
        cout << "No";
    else
        cout << "Yes";
}

// Driver code
int main()
{
    int A = 10, B = 20;
    int C = 15, n = 14;

    distributeN(A, B, C, n);
    return 0;
}

// This code is contributed by PratikBasu
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to distribute integer N
// among A, B, C such that they become equal
class GFG{

static void distributeN(int A, int B, int C,
                        int n)
{

    // Find maximum among the three elements
    int max1 = Math.max(A, B);
    int max2 = Math.max(B, C);
    int maximum = Math.max(max1, max2);

    // Summation of three elements
    int sum = A + B + C;
    int p = (3 * maximum) - sum;
    int diff = n - p;

    // Check if difference is divisible by 3
    if (diff < 0 || diff % 3 == 0)
        System.out.print("No");
    else
        System.out.print("Yes");
}

// Driver code
public static void main(String[] args)
{
    int A = 10, B = 20;
    int C = 15, n = 14;

    distributeN(A, B, C, n);
}
}

// This code is contributed by Rajput-Ji
```

## 蟒蛇 3

```
# Python3 Program to Distribute integer N
# among A, B, C such that they become equal

def distributeN(A, B, C, n):

    # find maximum among the three elements
    maximum = max(A, B, C)

    # summation of three elements
    sum = A + B+C

    p = (3 * maximum)-sum

    diff = n-p

    # check if difference is divisible by 3
    if diff < 0 or diff % 3:
        print "No"
    else:
        print "Yes"

# Driver code
A = 10
B = 20
C = 15
n = 14
distributeN(A, B, C, n)
```

## C#

```
// C# program to distribute integer N
// among A, B, C such that they become equal
using System;

class GFG{

static void distributeN(int A, int B, int C,
                        int n)
{

    // Find maximum among the three elements
    int max1 = Math.Max(A, B);
    int max2 = Math.Max(B, C);
    int maximum = Math.Max(max1, max2);

    // Summation of three elements
    int sum = A + B + C;
    int p = (3 * maximum) - sum;
    int diff = n - p;

    // Check if difference is divisible by 3
    if (diff < 0 || diff % 3 == 0)
        Console.Write("No");
    else
        Console.Write("Yes");
}

// Driver code
public static void Main(String[] args)
{
    int A = 10, B = 20;
    int C = 15, n = 14;

    distributeN(A, B, C, n);
}
}

// This code is contributed by Rajput-Ji
```

## java 描述语言

```
<script>

// JavaScript program to distribute integer N
// among A, B, C such that they become equal

function distributeN(A, B, C, n)
{
    // Find maximum among the three elements
    let max1 = Math.max(A, B);
    let max2 = Math.max(B, C);
    let maximum = Math.max(max1, max2);

    // Summation of three elements
    let sum = A + B + C;
    let p = (3 * maximum) - sum;
    let diff = n - p;

    // Check if difference is divisible by 3
    if (diff < 0 || diff % 3)
        document.write("No");
    else
        document.write("Yes");
}

// Driver code
    let A = 10, B = 20;
    let C = 15, n = 14;

    distributeN(A, B, C, n);

// This code is contributed by Surbhi Tyagi.

</script>
```

**Output:** 

```
No
```

***时间复杂度:** O(1)*