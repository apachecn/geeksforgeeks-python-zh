# 分棒问题

> 原文:[https://www.geeksforgeeks.org/dividing-sticks-problem/](https://www.geeksforgeeks.org/dividing-sticks-problem/)

给定一个整数列表，每个整数代表每根棍子的长度，一个整数告诉我们可以把一根棍子分成两半多少次，我们必须从这组棍子中找到最大期望的棍子长度。
***注 1:** 当我们折断一根棍子时，它被分成两个半部分，例如，对于长度为 10 的棍子，可以得到长度为 5 的两根棍子，对于长度为 5 的棍子，可以分别得到长度为 2 和 3 的两根棍子。*

**示例:**

> **输入:**
> 列表= [2，3，4，11]
> n = 2
> 期望 _ 长度= 3
> **输出:**
> 可以获得的期望长度的最大棒是:3
> **解释:**
> 我们已经有一根长度为 3 的棒，通过将长度为 11 的棒分成[5，3，3]块可以获得另外两根棒
> ，因此棒总数将为 3。
> 
> **输入:**
> 列表= [2，1，4，5]
> n = 2
> 期望 _ 长度= 4
> **输出:**
> 可以获得的期望长度的最大棒是:1
> **解释:**
> 我们已经有一根长度为 4 的棒，通过折断任何棒都无法获得更多的棒
> ，因此棒总数将为 1

**方法:**
为了解决上面提到的问题，我们将首先进行线性搜索操作，以找到与期望的棒长度具有完全相同长度的所有棒，并对它们进行计数。然后我们将计数存储在变量中。显然，我们必须丢弃所有长度小于所需长度的棍子，因为我们无法制造任何所需长度的棍子。然后将长度超过所需长度的棒的值传递给一个函数，该函数计算通过折断它们可以获得多少根棒。在递归的帮助下，找到许多获得棒的方法。
以下是上述方法的实施:

## C++

```
#include<bits/stdc++.h>
using namespace std;

// Method to find number of sticks by breaking them
int sticks_break(int stick_length,int n,
                 int desired_length)
{

    // If stick cant be break any more
    if (n < 1)
        return 0;

    // Check if stick length became
    // smaller than the desired length
    if (stick_length < desired_length)
        return 0;

    // Check if stick length is even number
    if (stick_length % 2 == 0)

        // Check if half of stick
        // length is equal to desired length
        if (stick_length / 2 == desired_length)
            return 2;

        // Check if half of stick length
        // is greater than the desired length
        else if (stick_length / 2 > desired_length)
            return (sticks_break(stick_length / 2,
                        n - 1, desired_length));

    // Check if stick length is odd number
    if (stick_length % 2 != 0)

        // For odd number two halves will be
        // generated checking if first half
        // is equal to desired length
        if (stick_length / 2 == desired_length)
            return 1;

        // Checking if second half
        // is equal to desired length
        if (stick_length / 2 + 1 == desired_length)
            return 1;

        // Check if half of stick length
        // is greater than the desired length
        if (stick_length/2 > desired_length)
            return (max (sticks_break(
                         stick_length / 2, n - 1,
                         desired_length),
                         sticks_break(
                         stick_length / 2 + 1,
                         n - 1, desired_length)));

    return 0;
}

// Method to find number of sticks    
int numberOfSticks(vector<int>list_length,
                   int n, int desired_length)
{
    int count = 0;

    for(auto stick_lenght : list_length)
    {

        // Check if desired length is found
        if (desired_length == stick_lenght)

            // Incrementing the count
            count = count + 1;

        // Check if stick length is
        // greater than desired length
        else if (stick_lenght> desired_length)

            // Incrementing count
            // after break the sticks
            count = count + sticks_break(
                            stick_lenght, n,
                            desired_length);
    }

    // Return count
    return count;
}

// Driver code
int main()
{

    // List of integers
    vector<int>list_length = { 1, 2, 3, 21 };

    // Number of ways stick can be break
    int n = 3;

    // Desired length
    int desired_length = 3;

    int count = numberOfSticks(list_length, n,
                            desired_length);

    // Print result
    cout << count << endl;
}

// This code is contributed by Stream_Cipher
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;

class GFG{

// Method to find number of sticks by breaking them
static int sticks_break(int stick_length,
                        int n, int desired_length)
{

    // If stick cant be break any more
    if (n < 1)
        return 0;

    // Check if stick length became
    // smaller than the desired length
    if (stick_length < desired_length)
        return 0;

    // Check if stick length is even number
    if (stick_length % 2 == 0)

        // Check if half of stick
        // length is equal to desired length
        if (stick_length / 2 == desired_length)
            return 2;

        // Check if half of stick length
        // is greater than the desired length
        else if (stick_length / 2 > desired_length)
            return (sticks_break(stick_length / 2,
                        n - 1, desired_length));

    // Check if stick length is odd number
    if (stick_length % 2 != 0)

        // For odd number two halves will be
        // generated checking if first half
        // is equal to desired length
        if (stick_length / 2 == desired_length)
            return 1;

        // Checking if second half
        // is equal to desired length
        if (stick_length / 2 + 1 == desired_length)
            return 1;

        // Check if half of stick length
        // is greater than the desired length
        if (stick_length/2 > desired_length)
            return (Math.max (sticks_break(
                               stick_length / 2,
                               n - 1, desired_length),
                               sticks_break(
                               stick_length / 2 + 1,
                               n - 1, desired_length)));

    return 0;
}

// Method to find number of sticks
static int numberOfSticks(int list_length[],
                          int n, int desired_length)
{
    int count = 0;

    for(int i = 0; i < list_length.length; i++)
    {

        // Check if desired length is found
        if (desired_length == list_length[i])

            // Incrementing the count
            count = count + 1;

        // Check if stick length is
        // greater than desired length
        else if (list_length[i]> desired_length)

            // Incrementing count
            // after break the sticks
            count = count + sticks_break(list_length[i],
                                   n, desired_length);
    }

    // Return count
    return count;
}

// Driver code
public static void main(String args[])
{

    // List of integers
    int[] list_length = new int[]{ 1, 2, 3, 21 };

    // Number of ways stick can be break
    int n = 3;

    // Desired length
    int desired_length = 3;

    int count = numberOfSticks(list_length, n,
                            desired_length);

    // Print result
    System.out.println(count);
}
}

// This code is contributed by Stream_Cipher
```

## 蟒蛇 3

```
# method to find number of sticks by breaking them
def sticks_break(stick_length, n, desired_length):

    # if stick cant be break any more
    if n < 1:

        return 0

    # check if stick length became
    # smaller than the desired length
    if stick_length < desired_length:

        return 0

    # check if stick length is even number
    if stick_length % 2 == 0:

        # check if half of stick
        # length is equal to desired length
        if stick_length / 2 == desired_length:

            return 2

        # check if half of stick length
        # is greater than the desired length
        elif stick_length / 2 > desired_length:

            return sticks_break(stick_length / 2, n-1, desired_length)

    # check if stick length is odd number
    if stick_length % 2 != 0:

        # for odd number two halves will be generated
        # checking if first half is equal to desired length
        if stick_length // 2 == desired_length:

            return 1

        # checking if second half
        # is equal to desired length
        if stick_length // 2 + 1 == desired_length:

            return 1

        # check if half of stick length
        # is greater than the desired length
        if stick_length//2 > desired_length:

            return max (sticks_break(stick_length//2, n-1, desired_length), sticks_break(stick_length//2 + 1, n-1, desired_length))

    return 0

# method to find number of sticks
def numberOfSticks(list_length, n, desired_length):

    count = 0

    for stick_length in list_length:

        # check if desired length is found
        if desired_length == stick_length:

            # incrementing the count
            count = count + 1

        # check if stick length is
        # greater than desired length
        elif stick_length > desired_length:

            # incrementing count
            # after break the sticks
            count = count + sticks_break(stick_length, n, desired_length)

    # return count    
    return count

# driver code
if __name__ == "__main__":

    # list of integers
    list_length =[1, 2, 3, 21]

    # number of ways stick can be break
    n = 3

    # desired length
    desired_length = 3

    count = numberOfSticks(list_length, n, desired_length)

    # print result
    print(str(count))
```

## C#

```
using System;
class GFG{

// Method to find number of sticks by breaking them
static int sticks_break(int stick_length,
                        int n, int desired_length)
{

    // If stick cant be break any more
    if (n < 1 )
        return 0;

    // Check if stick length became
    // smaller than the desired length
    if (stick_length < desired_length)
        return 0;

    // Check if stick length is even number
    if (stick_length % 2 == 0)

        // Check if half of stick
        // length is equal to desired length
        if (stick_length / 2 == desired_length)
            return 2;

        // Check if half of stick length
        // is greater than the desired length
        else if (stick_length / 2 > desired_length)
            return (sticks_break(stick_length / 2,
                        n - 1, desired_length));

    // Check if stick length is odd number
    if (stick_length % 2 != 0)

        // For odd number two halves will be
        // generated checking if first half
        // is equal to desired length
        if (stick_length / 2 == desired_length)
            return 1;

        // Checking if second half
        // is equal to desired length
        if (stick_length / 2 + 1 == desired_length)
            return 1;

        // Check if half of stick length
        // is greater than the desired length
        if (stick_length/2 > desired_length)
            return (Math.Max(sticks_break(
                             stick_length / 2,
                             n - 1, desired_length),
                             sticks_break(
                             stick_length / 2 + 1,
                             n - 1, desired_length)));

    return 0;
}

// Method to find number of sticks
static int numberOfSticks(int []list_length,
                          int n, int desired_length)
{
    int count = 0;
    for(int i = 0; i < list_length.Length; i++)
    {

        // Check if desired length is found
        if (desired_length == list_length[i])

            // Incrementing the count
            count = count + 1;

        // Check if stick length is
        // greater than desired length
        else if (list_length[i]> desired_length)

            // Incrementing count
            // after break the sticks
            count = count + sticks_break(list_length[i],
                                   n, desired_length);
    }

    // Return count
    return count;
}

// Driver code
public static void Main()
{

    // list of integers
    int []list_length = { 1, 2, 3, 21 };

    // Number of ways stick can be break
    int n = 3;

    // Desired length
    int desired_length = 3;
    int count = numberOfSticks(list_length,
                         n, desired_length);

    // Print result
    Console.WriteLine(count);
}
}

// This code is contributed by Stream_Cipher
```

## java 描述语言

```
<script>
    // Method to find number of sticks by breaking them
    function sticks_break(stick_length, n, desired_length)
    {

        // If stick cant be break any more
        if (n < 1)
            return 0;

        // Check if stick length became
        // smaller than the desired length
        if (stick_length < desired_length)
            return 0;

        // Check if stick length is even number
        if (stick_length % 2 == 0)

            // Check if half of stick
            // length is equal to desired length
            if (parseInt(stick_length / 2, 10) == desired_length)
                return 2;

            // Check if half of stick length
            // is greater than the desired length
            else if (parseInt(stick_length / 2, 10) > desired_length)
                return (sticks_break(parseInt(stick_length / 2, 10),
                            n - 1, desired_length));

        // Check if stick length is odd number
        if (stick_length % 2 != 0)

            // For odd number two halves will be
            // generated checking if first half
            // is equal to desired length
            if (parseInt(stick_length / 2, 10) == desired_length)
                return 1;

            // Checking if second half
            // is equal to desired length
            if (parseInt(stick_length / 2, 10) + 1 == desired_length)
                return 1;

            // Check if half of stick length
            // is greater than the desired length
            if (parseInt(stick_length/2, 10) > desired_length)
                return (Math.max(sticks_break(
                                   parseInt(stick_length / 2, 10),
                                   n - 1, desired_length),
                                   sticks_break(
                                   parseInt(stick_length / 2, 10) + 1,
                                   n - 1, desired_length)));

        return 0;
    }

    // Method to find number of sticks
    function numberOfSticks(list_length, n, desired_length)
    {
        let count = 0;

        for(let i = 0; i < list_length.length; i++)
        {

            // Check if desired length is found
            if (desired_length == list_length[i])

                // Incrementing the count
                count = count + 1;

            // Check if stick length is
            // greater than desired length
            else if (list_length[i]> desired_length)

                // Incrementing count
                // after break the sticks
                count = count + sticks_break(list_length[i],
                                       n, desired_length);
        }

        // Return count
        return count;
    }

    // List of integers
    let list_length = [ 1, 2, 3, 21 ];

    // Number of ways stick can be break
    let n = 3;

    // Desired length
    let desired_length = 3;

    let count = numberOfSticks(list_length, n,
                            desired_length);

    // Print result
    document.write(count);

</script>
```

**Output:** 

```
3
```

**时间复杂度:**o(n^2)
T3】辅助空间: O(N)