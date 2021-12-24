# 写入给定字符串所需的行数

> 原文:[https://www . geesforgeks . org/需要写入给定字符串的行数/](https://www.geeksforgeeks.org/count-of-lines-required-to-write-the-given-string/)

给定一个字符串**字符串**和一个整数数组**宽度[]** ，其中:

> 宽度[0] =字符“a”
> 的宽度[1] =字符“b”
> 的宽度……
> 宽度[25] =字符“z”
> 的宽度

任务是找出在纸上书写字符串**所需的行数和最后一行的宽度。
**注:**一条线的宽度为 **10 单位**。
**示例:**** 

> **输入:**str = " bbbcccddaa "、
> 宽度[] = {4，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1}
> **输出:** (2，8)
> 【bbbcccddd】将覆盖第一行(9 * 1 = 9 个单位)
> As 'a '的宽度为 4，其中
> 必须写在第二行。
> 所以，下一行将包含覆盖 4 * 2 = 8 个单位的“aa”。
> 我们需要 1 条全线和一条宽 8 个单位的线。
> **输入:**str = " abcdefghijklmnopqrstuvwxyz "，
> 宽度[] = {1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1 要写出全部 26 个字符，
> 我们需要 2 个完整的行和一个宽度为 6 个单位的行。

**方法:**我们将把字符串**中的每个字符一个一个写出来。当我们写一个字符时，我们会立即更新(行数、宽度)，记录到目前为止我们已经使用了多少行，最后一行中使用的空间长度是多少。
如果 **str** 中的**宽度【char】**符合我们当前的线，我们将添加它。否则，我们将从一个新的行
开始，下面是上述方法的实现:** 

## C++

```
// CPP implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the number of lines required
pair<int, int> numberOfLines(string S, int *widths)
{
    // If string is empty
    if (S.empty())
        return {0, 0};

    // Initialize lines and width
    int lines = 1, width = 0;

    // Iterate through S
    for (auto character : S)
    {
        int w = widths[character - 'a'];
        width += w;

        if (width >= 10)
        {
            lines++;
            width = w;
        }
    }

    // Return lines and width used
    return {lines, width};
}

// Driver Code
int main()
{
    string S = "bbbcccdddaa";
    int widths[] = {4, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
                    1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1};

    // Function call to print required answer
    pair<int, int> ans = numberOfLines(S, widths);
    cout << ans.first << " " << ans.second << endl;

    return 0;
}

// This code is contributed by
// sanjeev2552
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// JAVA implementation of the approach
class GFG
{

// Function to return the number of lines required
static int[] numberOfLines(String S, int []widths)
{
    // If String is empty
    if (S.isEmpty())
        return new int[]{0, 0};

    // Initialize lines and width
    int lines = 1, width = 0;

    // Iterate through S
    for (char character : S.toCharArray())
    {
        int w = widths[character - 'a'];
        width += w;

        if (width >= 10)
        {
            lines++;
            width = w;
        }
    }

    // Return lines and width used
    return new int[]{lines, width};
}

// Driver Code
public static void main(String[] args)
{
    String S = "bbbcccdddaa";
    int widths[] = {4, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
                    1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1};

    // Function call to print required answer
    int []ans = numberOfLines(S, widths);
    System.out.print(ans[0]+ " " + ans[1] +"\n");
}
}

// This code is contributed by Rajput-Ji
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function to return the number of lines required
def numberOfLines(S, widths):

    # If string is empty
    if(S == ""):
        return 0, 0

    # Initialize lines and width
    lines, width = 1, 0

    # Iterate through S
    for c in S:
        w = widths[ord(c) - ord('a')]
        width += w
        if width > 10:
            lines += 1
            width = w

    # Return lines and width used
    return lines, width

# Driver Code
S = "bbbcccdddaa"
Widths = [4, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1]

# Function call to print required answer
print(numberOfLines(S, Widths))
```

## C#

```
// C# implementation of the approach
using System;

class GFG
{

// Function to return the number of lines required
static int[] numberOfLines(String S, int []widths)
{
    // If String is empty
    if (S.Length == 0)
        return new int[]{0, 0};

    // Initialize lines and width
    int lines = 1, width = 0;

    // Iterate through S
    foreach (char character in S.ToCharArray())
    {
        int w = widths[character - 'a'];
        width += w;

        if (width >= 10)
        {
            lines++;
            width = w;
        }
    }

    // Return lines and width used
    return new int[]{lines, width};
}

// Driver Code
public static void Main(String[] args)
{
    String S = "bbbcccdddaa";
    int []widths = {4, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
                    1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1};

    // Function call to print required answer
    int []ans = numberOfLines(S, widths);
    Console.Write(ans[0]+ " " + ans[1] +"\n");
}
}

// This code is contributed by 29AjayKumar
```

## java 描述语言

```
<script>
// JAVAscript implementation of the approach

// Function to return the number of lines required
function numberOfLines(S,widths)
{
    // If String is empty
    if (S.length==0)
        return [0, 0];

    // Initialize lines and width
    let lines = 1, width = 0;

    // Iterate through S
    for (let character of S.split(""))
    {
        let w = widths[character.charCodeAt(0) - 'a'.charCodeAt(0)];
        width += w;

        if (width >= 10)
        {
            lines++;
            width = w;
        }
    }

    // Return lines and width used
    return [lines, width];
}

// Driver Code
let S = "bbbcccdddaa";
let widths = [4, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
                1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1];

// Function call to print required answer
let ans = numberOfLines(S, widths);
document.write(ans[0]+ " " + ans[1] +"<br>");

// This code is contributed by rag2127

</script>
```

**Output:** 

```
(2, 8)
```