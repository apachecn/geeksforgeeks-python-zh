# 求一个度序列是否能组成一个简单的图|哈维尔-哈基米算法

> 原文:[https://www . geesforgeks . org/find-if-a-degree-sequence-can-form-a-simple-graph-Havel-hakimi-algorithm/](https://www.geeksforgeeks.org/find-if-a-degree-sequence-can-form-a-simple-graph-havel-hakimi-algorithm/)

给定一个非负整数序列 **arr[]** ，任务是检查是否存在对应于这个度序列的简单图。**注意**简单图是没有自环和平行边的图。

**示例:**

> **输入:** arr[] = {3，3，3，3}
> **输出:**是
> 这其实是一个完整的图(K <sub>4</sub>
> 
> **输入:** arr[] = {3，2，1，0}
> **输出:**否
> 一个顶点的度数为 n-1，因此它与所有其他 n-1 个顶点相连。
> 但另一个顶点的度数为 0，即孤立。这是矛盾的。

**方法:**检查简单图形存在的一种方法是通过下面给出的[哈维尔-哈基米算法](https://en.wikipedia.org/wiki/Havel%E2%80%93Hakimi_algorithm):

*   按非递增顺序对非负整数序列进行排序。
*   删除第一个元素(比如 V)。从下一个 V 元素中减去 1。
*   重复 1 和 2，直到满足其中一个停止条件。

停止条件:

*   剩余的所有元素都等于 0(简单图形存在)。
*   减法后遇到负数(不存在简单图)。
*   减法步骤剩余的元素不足(不存在简单的图形)。

下面是上述方法的实现:

## C++

```
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function that returns true if
// a simple graph exists
bool graphExists(vector<int> &a, int n)
{
    // Keep performing the operations until one
    // of the stopping condition is met
    while (1)
    {
        // Sort the list in non-decreasing order
        sort(a.begin(), a.end(), greater<>());

        // Check if all the elements are equal to 0
        if (a[0] == 0)
            return true;

        // Store the first element in a variable
        // and delete it from the list
        int v = a[0];
        a.erase(a.begin() + 0);

        // Check if enough elements
        // are present in the list
        if (v > a.size())
            return false;

        // Subtract first element from next v elements
        for (int i = 0; i < v; i++)
        {
            a[i]--;

            // Check if negative element is
            // encountered after subtraction
            if (a[i] < 0)
                return false;
        }
    }
}

// Driver Code
int main()
{
    vector<int> a = {3, 3, 3, 3};
    int n = a.size();

    graphExists(a, n) ? cout << "Yes" :
                        cout << "NO" << endl;

    return 0;
}

// This code is contributed by
// sanjeev2552
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the approach
import java.util.*;

@SuppressWarnings("unchecked")

class GFG{

// Function that returns true if
// a simple graph exists
static boolean graphExists(ArrayList a, int n)
{

    // Keep performing the operations until one
    // of the stopping condition is met
    while (true)
    {

        // Sort the list in non-decreasing order
        Collections.sort(a, Collections.reverseOrder());

        // Check if all the elements are equal to 0
        if ((int)a.get(0) == 0)
            return true;

        // Store the first element in a variable
        // and delete it from the list
        int v = (int)a.get(0);
        a.remove(a.get(0));

        // Check if enough elements
        // are present in the list
        if (v > a.size())
            return false;

        // Subtract first element from
        // next v elements
        for(int i = 0; i < v; i++)
        {
            a.set(i, (int)a.get(i) - 1);

            // Check if negative element is
            // encountered after subtraction
            if ((int)a.get(i) < 0)
                return false;
        }
    }
}

// Driver Code
public static void main(String[] args)
{
    ArrayList a = new ArrayList();
    a.add(3);
    a.add(3);
    a.add(3);
    a.add(3);

    int n = a.size();

    if (graphExists(a, n))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("NO");
    }
}
}

// This code is contributed by pratham76
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function that returns true if
# a simple graph exists
def graphExists(a):

    # Keep performing the operations until one
    # of the stopping condition is met
    while True:

        # Sort the list in non-decreasing order
        a = sorted(a, reverse = True)

        # Check if all the elements are equal to 0
        if a[0]== 0 and a[len(a)-1]== 0:
            return True

        # Store the first element in a variable
        # and delete it from the list
        v = a[0]
        a = a[1:]

        # Check if enough elements
        # are present in the list
        if v>len(a):
            return False

        # Subtract first element from next v elements
        for i in range(v):
            a[i]-= 1

            # Check if negative element is
            # encountered after subtraction
            if a[i]<0:
                return False

# Driver code
a = [3, 3, 3, 3]
if(graphExists(a)):
    print("Yes")
else:
    print("No")
```

## C#

```
// C# implementation of the approach
using System;
using System.Collections;

class GFG{

// Function that returns true if
// a simple graph exists
static bool graphExists(ArrayList a, int n)
{

    // Keep performing the operations until one
    // of the stopping condition is met
    while (true)
    {

        // Sort the list in non-decreasing order
        a.Sort();
        a.Reverse();

        // Check if all the elements are equal to 0
        if ((int)a[0] == 0)
            return true;

        // Store the first element in a variable
        // and delete it from the list
        int v = (int)a[0];
        a.Remove(a[0]);

        // Check if enough elements
        // are present in the list
        if (v > a.Count)
            return false;

        // Subtract first element from
        // next v elements
        for(int i = 0; i < v; i++)
        {
            a[i] = (int)a[i] - 1;

            // Check if negative element is
            // encountered after subtraction
            if ((int)a[i] < 0)
                return false;
        }
    }
}

// Driver Code
public static void Main(string[] args)
{
    ArrayList a = new ArrayList(){ 3, 3, 3, 3 };
    int n = a.Count;

    if (graphExists(a, n))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("NO");
    }
}
}

// This code is contributed by rutvik_56
```

## java 描述语言

```
<script>

// Javascript implementation of the approach

// Function that returns true if
// a simple graph exists
function graphExists(a, n)
{

    // Keep performing the operations until one
    // of the stopping condition is met
    while (1)
    {

        // Sort the list in non-decreasing order
        a.sort((a, b) => b - a)

        // Check if all the elements are equal to 0
        if (a[0] == 0)
            return true;

        // Store the first element in a variable
        // and delete it from the list
        var v = a[0];
        a.shift();

        // Check if enough elements
        // are present in the list
        if (v > a.length)
            return false;

        // Subtract first element from next v elements
        for(var i = 0; i < v; i++)
        {
            a[i]--;

            // Check if negative element is
            // encountered after subtraction
            if (a[i] < 0)
                return false;
        }
    }
}

// Driver Code
var a = [ 3, 3, 3, 3 ];
var n = a.length;
graphExists(a, n) ? document.write("Yes"):
                    document.write("NO");

// This code is contributed by rrrtnx

</script>
```

**Output:** 

```
Yes
```

**时间复杂度:** O( ![N^2*logN](img/0f98f143f1321dd37e5cb774ee3ffa63.png "Rendered by QuickLaTeX.com") )
**辅助空间:** O(1)