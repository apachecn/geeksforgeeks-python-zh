# 程序打印给定数字的所有可被 3 和 5 整除的数字

> 原文:[https://www . geesforgeks . org/program-print-numbers-除尽-3-5-给定-number/](https://www.geeksforgeeks.org/program-print-numbers-divisible-3-5-given-number/)

给定整数 N，任务是打印所有小于 N 的数字，这些数字可以被 3 和 5 整除。
**例:**

```py
Input : 50
Output : 0 15 30 45 

Input : 100
Output : 0 15 30 45 60 75 90 
```

**逼近:**比如我们以 N = 20 为极限，那么程序应该打印出所有小于 20 且能被 3 和 5 整除的数字。为此，将从 0 到 N 的每个数字除以 3 和 5，并检查它们的余数。如果两种情况下余数都是 0，那么只需打印该数字。
下面是实现:

## C++

```py
// C++ program to print all the numbers
// divisible by 3 and 5 for a given number
#include <iostream>
using namespace std;

// Result function with N
void result(int N)
{    
    // iterate from 0 to N
    for (int num = 0; num < N; num++)
    {    
        // Short-circuit operator is used
        if (num % 3 == 0 && num % 5 == 0)
            cout << num << " ";
    }
}

// Driver code
int main()
{    
    // input goes here
    int N = 100;

    // Calling function
    result(N);
    return 0;
}

// This code is contributed by Manish Shaw
// (manishshaw1)
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java program to print all the numbers
// divisible by 3 and 5 for a given number

class GFG{

    // Result function with N
    static void result(int N)
    {    
        // iterate from 0 to N
        for (int num = 0; num < N; num++)
        {    
            // Short-circuit operator is used
            if (num % 3 == 0 && num % 5 == 0)
                System.out.print(num + " ");
        }
    }

    // Driver code
    public static void main(String []args)
    {
        // input goes here
        int N = 100;

        // Calling function
        result(N);
    }
}
```

## 蟒蛇 3

```py
# Python program to print all the numbers
# divisible by 3 and 5 for a given number

# Result function with N
def result(N):

    # iterate from 0 to N
    for num in range(N):

            # Short-circuit operator is used
            if num % 3 == 0 and num % 5 == 0:
                print(str(num) + " ", end = "")

            else:
                pass

# Driver code
if __name__ == "__main__":

    # input goes here
    N = 100

    # Calling function
    result(N)
```

## C#

```py
// C# program to print all the numbers
// divisible by 3 and 5 for a given number
using System;
public class GFG{

    // Result function with N
    static void result(int N)
    {    
        // iterate from 0 to N
        for (int num = 0; num < N; num++)
        {    
            // Short-circuit operator is used
            if (num % 3 == 0 && num % 5 == 0)
                Console.Write(num + " ");
        }
    }

    // Driver code
    static public void Main (){
        // input goes here
        int N = 100;
        // Calling function
        result(N);
    }
//This code is contributed by ajit.   
}
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP program to print all the numbers
// divisible by 3 and 5 for a given number

// Result function with N
function result($N)
{
    // iterate from 0 to N
    for ($num = 0; $num < $N; $num++)
    {
        // Short-circuit operator is used
        if ($num % 3 == 0 && $num % 5 == 0)
            echo $num, " ";
    }
}

// Driver code

// input goes here
$N = 100;

// Calling function
result($N);

// This code is contributed by ajit
?>
```

## java 描述语言

```py
<script>

// Javascript  program to
// print all the numbers
// divisible by 3 and 5
// for a given number

// Result function with N
function result(N)
{
    // iterate from 0 to N
    for (let num = 0; num < N; num++)
    {
        // Short-circuit operator is used
        if (num % 3 == 0 && num % 5 == 0)
            document.write( num+ " ");
    }
}

// Driver code

// input goes here
let N = 100;

// Calling function
result(N);

// This code is contributed by Bobby

</script>
```

**输出:**

```py
0 15 30 45 60 75 90 
```