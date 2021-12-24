# 组成给定字符串回文的最小替换字符数

> 原文:[https://www . geesforgeks . org/给定字符串的最小替换字符数回文/](https://www.geeksforgeeks.org/minimum-number-of-characters-to-be-replaced-to-make-a-given-string-palindrome/)

给定字符串 **str** ，任务是找到要替换的最小字符数，使给定字符串回文。替换字符意味着用同一位置的任何单个字符替换它。我们不允许删除或添加任何字符。

如果有多个答案，打印字典上最小的字符串。

**示例:**

```py
Input: str = "geeks"
Output: 2
geeks can be converted to geeeg to make it palindrome
by replacing minimum characters.

Input: str = "ameba"
Output: 1
We can get "abeba" or "amema" with only 1 change. 
Among those two, "abeba" is lexicographically smallest. 
```

**方法:**运行从 0 到(长度)/2-1 的循环，检查第 I 个索引处的字符是否为 s[i]！=s[length-i-1]，那么我们将用其中字母顺序较小的字符替换字母顺序较大的字符，并继续相同的过程，直到所有元素都被遍历。

下面是上述方法的实现:

## C++

```py
// C++ Implementation of the above approach
#include<bits/stdc++.h>
using namespace std;

// Function to find the minimum number
// character change required

void change(string s)
{

    // Finding the length of the string
    int n = s.length();

    // To store the number of replacement operations
    int cc = 0;

    for(int i=0;i<n/2;i++)
    {

        // If the characters at location
        // i and n-i-1 are same then
        // no change is required
        if(s[i]== s[n-i-1])
            continue;

        // Counting one change operation
        cc+= 1;

        // Changing the character with higher
        // ascii value with lower ascii value
        if(s[i]<s[n-i-1])
            s[n-i-1]= s[i] ;
        else
            s[i]= s[n-i-1] ;
    }
    printf("Minimum characters to be replaced = %d\n", (cc)) ;
    cout<<s<<endl;
}
// Driver code
int main()
{
string s = "geeks";
change((s));
return 0;
}
//contributed by Arnab Kundu
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java Implementation of the above approach
import java.util.*;

class GFG
{

// Function to find the minimum number
// character change required
static void change(String s)
{

    // Finding the length of the string
    int n = s.length();

    // To store the number of replacement operations
    int cc = 0;

    for(int i = 0; i < n/2; i++)
    {

        // If the characters at location
        // i and n-i-1 are same then
        // no change is required
        if(s.charAt(i) == s.charAt(n - i - 1))
            continue;

        // Counting one change operation
        cc += 1;

        // Changing the character with higher
        // ascii value with lower ascii value
        if(s.charAt(i) < s.charAt(n - i - 1))
            s = s.replace(s.charAt(n - i - 1),s.charAt(i));
        else
            s = s.replace(s.charAt(n-1),s.charAt(n - i - 1));
    }
    System.out.println("Minimum characters to be replaced = "+(cc)) ;
    System.out.println(s);
}

// Driver code
public static void main(String args[])
{
    String s = "geeks";
    change((s));

}
}

// This code is contributed by
// Nikhil Gupta
```

## 计算机编程语言

```py
# Python Implementation of the above approach

# Function to find the minimum number
# character change required
import math as ma
def change(s):

    # Finding the length of the string
    n = len(s)

    # To store the number of replacement operations
    cc = 0

    for i in range(n//2):

        # If the characters at location
        # i and n-i-1 are same then
        # no change is required
        if(s[i]== s[n-i-1]):
            continue

        # Counting one change operation
        cc+= 1

        # Changing the character with higher
        # ascii value with lower ascii value
        if(s[i]<s[n-i-1]):
            s[n-i-1]= s[i]
        else:
            s[i]= s[n-i-1]

    print("Minimum characters to be replaced = ", str(cc))
    print(*s, sep ="")

# Driver code
s = "geeks"
change(list(s))
```

## C#

```py
// C# Implementation of the above approach
using System;

class GFG
{

// Function to find the minimum number
// character change required
static void change(String s)
{

    // Finding the length of the string
    int n = s.Length;

    // To store the number of
    //replacement operations
    int cc = 0;

    for(int i = 0; i < n / 2; i++)
    {

        // If the characters at location
        // i and n-i-1 are same then
        // no change is required
        if(s[i] == s[n - i - 1])
            continue;

        // Counting one change operation
        cc += 1;

        // Changing the character with higher
        // ascii value with lower ascii value
        if(s[i] < s[n - i - 1])
            s = s.Replace(s[n - i - 1], s[i]);
        else
            s = s.Replace(s[n], s[n - i - 1]);
    }
    Console.WriteLine("Minimum characters " +
                      "to be replaced = " + (cc));
    Console.WriteLine(s);
}

// Driver code
public static void Main(String []args)
{
    String s = "geeks";
    change((s));
}
}

// This code contributed by Rajput-Ji
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP Implementation of the above approach

// Function to find the minimum number
// character change required

function change($s)
{

    // Finding the length of the string
    $n = strlen($s);

    // To store the number of replacement operations
    $cc = 0;

    for($i=0;$i<$n/2;$i++)
    {

        // If the characters at location
        // i and n-i-1 are same then
        // no change is required
        if($s[$i]== $s[$n-$i-1])
            continue;

        // Counting one change operation
        $cc+= 1;

        // Changing the character with higher
        // ascii value with lower ascii value
        if($s[$i]<$s[$n-$i-1])
            $s[$n-$i-1]= $s[$i] ;
        else
            $s[$i]= $s[$n-$i-1] ;
    }
    echo "Minimum characters to be replaced = ". $cc."\n" ;
    echo $s."\n";
}
// Driver code

$s = "geeks";
change(($s));
return 0;
?>
```

## java 描述语言

```py
<script>

// Javascript Implementation of the above approach

// Function to find the minimum number
// character change required

function change(s)
{

    // Finding the length of the string
    var n = s.length;

    // To store the number of replacement operations
    var cc = 0;

    for(var i=0;i<n/2;i++)
    {

        // If the characters at location
        // i and n-i-1 are same then
        // no change is required
        if(s[i]== s[n-i-1])
            continue;

        // Counting one change operation
        cc+= 1;

        // Changing the character with higher
        // ascii value with lower ascii value
        if(s[i]<s[n-i-1])
            s[n-i-1]= s[i] ;
        else
            s[i]= s[n-i-1] ;
    }
    document.write("Minimum characters to be replaced = " + (cc)+"<br>");
    document.write(s.join('') + "<br>");
}

// Driver code
var s = "geeks".split('');
change((s));

</script>
```

**Output:** 

```py
Minimum characters to be replaced =  2
geeeg
```