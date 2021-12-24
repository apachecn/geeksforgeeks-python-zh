# 从 a、b 和 c 中去掉所有零后，检查 a + b = c 是否有效

> 原文:[https://www . geeksforgeeks . org/check-if-a-b-c-is-valid-在从 a-B-和-c 中移除所有零之后/](https://www.geeksforgeeks.org/check-if-a-b-c-is-valid-after-removing-all-zeroes-from-a-b-and-c/)

给定两个整数 **a** 和 **b** 。现在 **c** 可以找到 **a + b = c** 。任务是检查从 **a** 、 **b** 和 **c** 中去掉所有零后，等式是否仍然有效。如果有效，则打印**是**否则打印**否**。

**示例:**

> **输入:** a = 101，b = 102
> **输出:**是
> 当前等式为 101 + 102 = 203
> 去掉 0 后，11 + 12 = 23(仍然正确)
> 
> **输入:** a = 105，b = 106
> **输出:**否
> 105 + 106 = 211
> 15 + 16 = 211(不正确)

**进场:**

*   计算 **c** 。
*   从 **a** 、 **b** 和 **c** 中移除所有 **0s** 。
*   检查新值是否形成正确的等式。

下面是上述方法的实现:

## C++

```
// C++ implementation of the approach
#include<bits/stdc++.h>
#include<string>
#include<iostream>
#include<sstream>

using namespace std;

// Function to remove zeroes from a number
int remove(int x)
{
    // Converting x into a string

    string y = to_string(x);

    // To store the new integer without 0s
    string num;
    int i;
    for(i = 0; i < y.length(); i++)
    {
        // Skip if current character is 0
        if(y[i] == 0)
            continue;
        num += y[i];
    }

    // Return the integer after removing 0s
    return stoi(num);
}

// Function that returns true if
// the given condition is satisfied
bool check(int a, int b)
{
    // Calculate c
    int c = a + b;

    // Remove 0s from a, b and c
    a = remove(a);
    b = remove(b);
    c = remove(c);

    // Check if the equation is still correct
    if((a + b) == c)
        return true;
    else
        return false;
}

// Driver code
int main()
{
    int a = 101;
    int b = 102;

    if(check(a, b))
        cout << "Yes";
    else
        cout << "No";
}

// This code is contributed by ita_c
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
import java.util.*;

class GFG{

// Function to remove zeroes from a number    
public static int remove(int x)
{

    // Converting x into a string
    String y = String.valueOf(x);

    // To store the new integer without 0s
    String num = "";
    int i;

    for(i = 0; i < y.length(); i++)
    {

       // Skip if current character is 0
       if(y.charAt(i) == 0)
          continue;
       num += y.charAt(i);
    }

    // Return the integer after
    // removing 0s
    return Integer.parseInt(num);
}

// Function that returns true if
// the given condition is satisfied
public static boolean check(int a, int b)
{

    // Calculate c
    int c = a + b;

    // Remove 0s from a, b and c
    a = remove(a);
    b = remove(b);
    c = remove(c);

    // Check if the equation is
    // still correct
    if((a + b) == c)
        return true;
    else
        return false;
}

// Driver code
public static void main(String[] args)
{
    int a = 101;
    int b = 102;

    if(check(a, b))
        System.out.println("Yes");
    else
        System.out.println("No");
}
}

// This code is contributed by grandmaster
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function that returns true if
# the given condition is satisfied
def check(a, b):

    # Calculate c
    c = a + b

    # Remove 0s from a, b and c
    a = remove(a)
    b = remove(b)
    c = remove(c)

    # Check if the equation is still correct
    if((a + b) == c):
        return True
    else:
        return False

# Function to remove zeroes from a number
def remove(x):

    # Converting x into a string
    y = str(x)

    # To store the new integer without 0s
    num = ""
    for i in range(len(y)):

        # Skip if current character is 0
        if(y[i] == "0"):
            continue
        num += y[i]

    # Return the integer after removing 0s
    return int(num)

# Driver code
a = 101
b = 102

if(check(a, b)):
    print("Yes")
else:
    print("No")
```

## C#

```
// C# implementation of the approach
using System;

class GFG{

// Function to remove zeroes from a number    
public static int remove(int x)
{

    // Converting x into a string
    string y = x.ToString();

    // To store the new integer without 0s
    string num = "";
    int i;

    for(i = 0; i < y.Length; i++)
    {

        // Skip if current character is 0
        if (y[i] == 0)
            continue;

        num += y[i];
    }

    // Return the integer after
    // removing 0s
    return Int32.Parse(num);
}

// Function that returns true if
// the given condition is satisfied
public static bool check(int a, int b)
{

    // Calculate c
    int c = a + b;

    // Remove 0s from a, b and c
    a = remove(a);
    b = remove(b);
    c = remove(c);

    // Check if the equation is
    // still correct
    if ((a + b) == c)
        return true;
    else
        return false;
}

// Driver code
public static void Main(string[] args)
{
    int a = 101;
    int b = 102;

    if (check(a, b))
        Console.Write("Yes");
    else
        Console.Write("No");
}
}

// This code is contributed by rutvik_56
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?php
// PHP implementation of the approach

// Function that returns true if
// the given condition is satisfied
function check($a, $b)
{

    // Calculate c
    $c = $a + $b ;

    // Remove 0s from a, b and c
    $a = remove($a);
    $b = remove($b);
    $c = remove($c);

    // Check if the equation is
    // still correct
    if(($a + $b) == $c)
        return true;
    else
        return false;
}

// Function to remove zeroes
// from a number
function remove($x)
{

    // Converting x into a string
    $y = (string)$x;

    // To store the new integer without 0s
    $num = "";
    for ($i = 0; $i < strlen($y); $i++)
    {

        // Skip if current character is 0
        if($y[$i] == "0")
            continue ;
        $num .= $y[$i];
    }

    // Return the integer after removing 0s
    return (int)$num;
}

// Driver code
$a = 101;
$b = 102;

if(check($a, $b))
    echo "Yes";
else
    echo "No";

// This code is contributed by Ryuga
?>
```

## java 描述语言

```
<script>

// JavaScript implementation of the approach

// Function to remove zeroes from a number
function remove(x)
{
    // Converting x into a string

    var y = x.toString();

    // To store the new integer without 0s
    var num = "";
    var i;
    for(i = 0; i < y.length; i++)
    {
        // Skip if current character is 0
        if(y[i] == 0)
            continue;
        num += y[i];
    }

    // Return the integer after removing 0s
    return parseInt(num);
}

// Function that returns true if
// the given condition is satisfied
function check(a, b)
{
    // Calculate c
    var c = a + b;

    // Remove 0s from a, b and c
    a = remove(a);
    b = remove(b);
    c = remove(c);

    // Check if the equation is still correct
    if((a + b) == c)
        return true;
    else
        return false;
}

// Driver code
var a = 101;
var b = 102;

if(check(a, b))
    document.write( "Yes");
else
    document.write( "No");

</script>
```

**Output:** 

```
Yes
```

**Python 中的替代实现:**

## 蟒蛇 3

```
# Python3 implementation of the approach

# Calculate the sum with Zero's intact
d=a+b

# Then convert the numbers to string
# replace '0' with '' (blank)

a=str(a).replace('0','')
b=str(b).replace('0','')

# Now convert the strings back to numbers
# Add the numbers
c=int(a)+int(b)

if c==d:
    print('Yes')
else:
    print('No')

# This code is contributed by Sandeep Midde
```