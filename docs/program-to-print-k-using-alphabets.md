# 使用字母打印 K 的程序

> 原文:[https://www . geesforgeks . org/program-to-print-k-using-alphabets/](https://www.geeksforgeeks.org/program-to-print-k-using-alphabets/)

给定一个数字 n，任务是用字母打印“K”。
**例:**

```py
Input: n = 5
Output: 
A B C D E F 
A B C D E 
A B C D 
A B C 
A B 
A 
A 
A B 
A B C 
A B C D 
A B C D E 
A B C D E F 

Input: n = 3
Output:
A B C D 
A B C 
A B 
A 
A 
A B 
A B C 
A B C D
```

下面是实现。

## C++

```py
// C++ Program to design the
// above pattern of K using alphabets
#include<bits/stdc++.h>
using namespace std;

// Function to print
// the above Pattern
void display(int n)
{
  int v = n;

  // This loop is used
  // for rows and prints
  // the alphabets in
  // decreasing order
  while (v >= 0)
  {
    int c = 65;

    // This loop is used
    // for columns
    for(int j = 0; j < v + 1; j++)
    {
      // chr() function converts the
      // number to alphabet
      cout << char(c + j) << " ";
    }

    v--;
    cout << endl;
  }

  // This loop is again used
  // to rows and prints the
  // half remaining pattern in
  // increasing order
  for(int i = 0; i < n + 1; i++)
  {
    int c = 65;

    for(int j = 0; j < i + 1; j++)
    {
      cout << char(c + j) << " ";
    }
    cout << endl;
  }
}

// Driver code
int main()
{
  int n = 5;
  display(n);
  return 0;
}

// This code is contributed by divyeshrabadiya07
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java Program to design the
// above pattern of K using alphabets
public class Main
{
    // Function to print
    // the above Pattern
    public static void display(int n)
    {
      int v = n;

      // This loop is used
      // for rows and prints
      // the alphabets in
      // decreasing order
      while (v >= 0)
      {
        int c = 65;

        // This loop is used
        // for columns
        for(int j = 0; j < v + 1; j++)
        {

          // chr() function converts the
          // number to alphabet
          System.out.print((char)(c + j) + " ");
        }

        v--;
        System.out.println();
      }

      // This loop is again used
      // to rows and prints the
      // half remaining pattern in
      // increasing order
      for(int i = 0; i < n + 1; i++)
      {
        int c = 65;

        for(int j = 0; j < i + 1; j++)
        {
          System.out.print((char)(c + j) + " ");
        }
        System.out.println();
      }
    }

  // Driver code
  public static void main(String[] args)
  {
    int n = 5;
    display(n);
  }
}

// This code is contributed by divyesh072019
```

## 蟒蛇 3

```py
# Python Program to design the
# above pattern of K using alphabets

# Function to print the above Pattern
def display(n):
    v = n

    # This loop is used for rows and
    # prints the alphabets in decreasing
    # order
    while ( v >= 0) :
        c = 65

        # This loop is used for columns
        for j in range(v + 1):

            # chr() function converts the
            # number to alphabet
            print( chr ( c + j ), end = " ")
        v = v - 1
        print()

    # This loop is again used to rows and
    # prints the half remaining pattern in
    # increasing order
    for i in range(n + 1):
        c = 65

        for j in range( i + 1):
            print( chr ( c + j), end =" ")
        print()

# Driver code
n = 5
display(n)
```

## C#

```py
// C# Program to design the
// above pattern of K using alphabets
using System.IO;
using System;

class Gfg
{

    // Function to print
    // the above Pattern
    static void display(int n)
    {
        int v = n;

        // This loop is used
        // for rows and prints
        // the alphabets in
        // decreasing order
        while(v >= 0)
        {
            int c = 65;

            // This loop is used
            // for columns
            for(int j = 0; j < v + 1; j++)
            {

                // chr() function converts the
                // number to alphabet
                Console.Write((char)(c + j) + " ");
            }
            v--;
            Console.WriteLine();
        }

        // This loop is again used
        // to rows and prints the
        // half remaining pattern in
        // increasing order
        for(int i = 0; i < n + 1; i++)
        {
            int c = 65;
            for(int j = 0; j < i + 1; j++)
            {
                Console.Write((char)(c + j) + " ");
            }
            Console.WriteLine();
        }
    }

    // Driver code
    static void Main()
    {
        int n = 5;
        display(n);
    }
}

// This code is contributed by avanitrachhadiya2155
```

## java 描述语言

```py
<script>
    // Javascript Program to design the
    // above pattern of K using alphabets

    // Function to print
    // the above Pattern
    function display(n)
    {
      let v = n;

      // This loop is used
      // for rows and prints
      // the alphabets in
      // decreasing order
      while (v >= 0)
      {
        let c = 65;

        // This loop is used
        // for columns
        for(let j = 0; j < v + 1; j++)
        {
          // chr() function converts the
          // number to alphabet
          document.write(String.fromCharCode(c + j) + " ");
        }

        v--;
        document.write("</br>");
      }

      // This loop is again used
      // to rows and prints the
      // half remaining pattern in
      // increasing order
      for(let i = 0; i < n + 1; i++)
      {
        let c = 65;

        for(let j = 0; j < i + 1; j++)
        {
          document.write(String.fromCharCode(c + j) + " ");
        }
        document.write("</br>");
      }
    }

    let n = 5;
      display(n);

    // This code is contributed by suresh07.
</script>
```

**输出:**

```py
A B C D E F 
A B C D E 
A B C D 
A B C 
A B 
A 
A 
A B 
A B C 
A B C D 
A B C D E 
A B C D E F
```