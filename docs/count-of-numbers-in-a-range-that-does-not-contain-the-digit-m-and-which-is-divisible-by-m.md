# 不包含数字 M 且可被 M 整除的范围内的数字计数

> 原文:[https://www . geeksforgeeks . org/不包含数字 m 和可被 m 整除的数字范围计数/](https://www.geeksforgeeks.org/count-of-numbers-in-a-range-that-does-not-contain-the-digit-m-and-which-is-divisible-by-m/)

给定三个整数，下范围 **L** ，上范围 **U** ，一个数字 **M** 。任务是计算 L 和 U 之间的所有数字，这样这个数字就可以被 M 整除，而且它不包含数字 M

**示例:**

```
Input: M = 9 ,L = 16 , U = 26
Output: 1
Explanation:
Within this given range ,the number that 
follows the above two given conditions is: 18.

Input: M = 6 ,L = 88 , U = 102
Output: 2
Explanation:
Within this given range ,the numbers that 
follows the above two given conditions are: 90 and 102.
```

**进场:**

*   想法是从较低的范围(L)迭代到较高的范围(U ),
*   我们会将数字的不同数字存储在一个 ***num*** 变量中，并根据给定的条件检查集合是否包含数字 M。如果该数字不包含给定的数字 M，并且可被 M 整除，则计数器递增 1。

## C++

```
// C++ implementation to illustrate
// the program
#include<bits/stdc++.h>
using namespace std;

// Function to count all the numbers
// which does not contain the digit 'M'
// and is divisible by M
void contain(int L, int U, int M)
{
    int count = 0;
    for(int j = L; j < U; j++)
    {

    // Storing all the distinct
    // digits of a number
    set<string> num;
    string str = to_string(j);
    num.insert(str);

    // Checking if the two conditions
    // are satisfied or not
    if (j % M == 0 and
        num.find(to_string(M)) == num.end())
    {
        count += 1;
    }
    }
    cout << count - 2;
}

// Driver code
int main()
{
    // Lower Range
    int L = 106;

    // Upper Range
    int U = 200;

    // The digit
    int M = 7;

    contain(L, U, M);
}

// This code is contributed by BhupendraSingh
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation to illustrate
// the program
import java.util.*;

class GFG{

// Function to count all the numbers
// which does not contain the digit 'M'
// and is divisible by M
static void contain(int L, int U, int M)
{
    int count = 0;
    for(int j = L; j < U; j++)
    {

        // Storing all the distinct
        // digits of a number
        HashSet<String> num = new HashSet<>();
        String str = Integer.toString(j);
        num.add(str);

        // Checking if the two conditions
        // are satisfied or not
        if (j % M == 0 && !num.contains(
            Integer.toString(M)))
        {
            count += 1;
        }
    }
    System.out.println(count - 2);
}

// Driver code
public static void main(String[] args)
{

    // Lower Range
    int L = 106;

    // Upper Range
    int U = 200;

    // The digit
    int M = 7;

    contain(L, U, M);
}
}

// This code is contributed by jrishabh99
```

## 蟒蛇 3

```
# Python3 implementation to illustrate
# the program

# Function to count all the numbers
# which does not contain the digit 'M'
# and is divisible by M
def contain (L,U,M):
    count = 0
    for j in range (L,U+1):

        # Storing all the distinct
        # digits of a number
        num = set(str(j))

        # Checking if the two conditions
        # are satisfied or not
        if (j % M == 0 and str(M) not in num):
            count += 1
    print (count)

#Driver code
if __name__== '__main__':

    L = 106 # Lower Range
    U = 200 # Upper Range
    M = 7 # The digit

    contain(L,U,M)

# This code is contributed by parna_28
```

## C#

```
// C# implementation to illustrate
// the program
using System;
using System.Collections.Generic;

class GFG{

// Function to count all the numbers
// which does not contain the digit 'M'
// and is divisible by M
static void contain(int L, int U, int M)
{
    int count = 0;
    for(int j = L; j < U; j++)
    {

        // Storing all the distinct
        // digits of a number
        HashSet<string> num = new HashSet<string>();

        string str = j.ToString();
        num.Add(str);

        // Checking if the two conditions
        // are satisfied or not
        if (j % M == 0 && !num.Contains(M.ToString()))
        {
            count += 1;
        }
    }
    Console.Write(count - 2);
}

// Driver code
public static void Main(string[] args)
{

    // Lower Range
    int L = 106;

    // Upper Range
    int U = 200;

    // The digit
    int M = 7;

    contain(L, U, M);
}
}

// This code is contributed by rutvik_56
```

## java 描述语言

```
<script>
// Javascript implementation to illustrate
// the program

// Function to count all the numbers
// which does not contain the digit 'M'
// and is divisible by M
function contain(L, U, M)
{
    let count = 0;
    for(let j = L; j < U; j++)
    {

        // Storing all the distinct
        // digits of a number
        let num = new Set();
        let str = String(j);
        num.add(str);

        // Checking if the two conditions
        // are satisfied or not
        if (j % M == 0 && !num.has(String(M)))
        {
            count += 1;
        }
    }
    document.write(count - 2);
}

// Driver code

    // Lower Range
    let L = 106;

    // Upper Range
    let U = 200;

    // The digit
    let M = 7;

    contain(L, U, M);

// This code is contributed by _saurabh_jaiswal
</script>
```

**Output**

```
11
```

**时间复杂度:O(U)**

**辅助空间:O(U)**