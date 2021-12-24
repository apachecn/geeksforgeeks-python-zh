# 如何在 Python 等语言中给变量赋值

> 原文:[https://www . geesforgeks . org/如何用 python 和其他语言为变量赋值/](https://www.geeksforgeeks.org/how-to-assign-values-to-variables-in-python-and-other-languages/)

本文讨论给变量赋值的方法。

### 方法 1:直接初始化方法

## C++

```py
// C++ code to demonstrate variable assignment
// upon condition using Direct Initialisation Method

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising variables directly
    int a = 5;

    // printing value of a
    cout << "The value of a is: " << a;
}
```

## C

```py
// C code to demonstrate variable assignment
// upon condition using Direct Initialisation Method

#include <stdio.h>

int main()
{
    // initialising variables directly
    int a = 5;

    // printing value of a
    printf("The value of a is: %d", a);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java code to demonstrate variable assignment
// upon condition using Direct Initialisation Method

import java.io.*;

class GFG {
    public static void main(String args[])
    {

        // initialising variables directly
        int a = 5;

        // printing value of a
        System.out.println("The value of a is: " + a);
    }
}
```

## 蟒蛇 3

```py
# Python 3 code to demonstrate variable assignment
# upon condition using Direct Initialisation Method

# initialising variable directly
a = 5

# printing value of a
print ("The value of a is: " + str(a))
```

## C#

```py
// C# code to demonstrate variable assignment
// upon condition using Direct Initialisation Method
using System;

class GFG{

public static void Main(String []args)
{

    // Initialising variables directly
    int a = 5;

    // Printing value of a
    Console.Write("The value of a is: " + a);
}
}

// This code is contributed by shivanisinghss2110
```

## java 描述语言

```py
<script>

// JavaScript code to demonstrate variable assignment
// upon condition using Direct Initialisation Method
        // initialising variables directly
        var a = 5;

        // printing value of a
        document.write("The value of a is: " + a);

</script>
// this code is contributed by shivanisinghss2110
```

**Output:** 

```py
The value of a is: 5
```

### 方法 2:使用条件运算符(？:)

以下是其他流行语言的语法。

## c++

```py
// C++ code to demonstrate variable assignment
// upon condition using Conditional Operator

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialising variables using Conditional Operator
    int a = 20 > 10 ? 1 : 0;

    // printing value of a
    cout << "The value of a is: " << a;
}
```

## C

```py
// C code to demonstrate variable assignment
// upon condition using Conditional Operator

#include <stdio.h>

int main()
{
    // initialising variables using Conditional Operator
    int a = 20 > 10 ? 1 : 0;

    // printing value of a
    printf("The value of a is: %d", a);
}
```

## Java

```py
// Java code to demonstrate variable assignment
// upon condition using Conditional Operator

import java.io.*;

class GFG {
    public static void main(String args[])
    {

        // initialising variables using Conditional Operator
        int a = 20 > 10 ? 1 : 0;

        // printing value of a
        System.out.println("The value of a is: " + a);
    }
}
```

## python 3

```py
# Python3 code to demonstrate variable assignment
# upon condition using Conditional Operator

# Initialising variables using Conditional Operator
a = 1 if 20 > 10 else 0

# Printing value of a
print("The value of a is: " , str(a))

# This code is contributed by shivanisinghss2110
```

## c#

```py
// C# code to demonstrate variable assignment
// upon condition using Conditional Operator

using System;

class GFG {
    public static void Main(String []args)
    {

        // initialising variables using Conditional Operator
        int a = 20 > 10 ? 1 : 0;

        // printing value of a
        Console.Write("The value of a is: " + a);
    }
}
// this code is contributed by shivanisinghss2110
```

## Javascript

**输出:**

```py
The value of a is: 1
```

### 一行 if-else 而不是条件运算符(？:)在 Python 中

## 蟒蛇 3

```py
# Python 3 code to demonstrate variable assignment
# upon condition using One liner if-else

# initialising variable using Conditional Operator
# a = 20 > 10 ? 1 : 0 is not possible in Python
# Instead there is one liner if-else
a = 1 if 20 > 10 else 0

# printing value of a
print ("The value of a is: " + str(a))
```

**Output:** 

```py
The value of a is: 1
```