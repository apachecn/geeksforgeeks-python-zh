# 覆盖 N*M 网格中给定位置的最小成本

> 原文:[https://www . geesforgeks . org/覆盖纳米网格中给定位置的最小成本/](https://www.geeksforgeeks.org/minimum-cost-to-cover-the-given-positions-in-a-nm-grid/)

给定一个 **n*m** 的网格和网格中一些要绘制的杆的位置，任务是找到绘制所有杆的最小成本。从一行移动到另一行没有成本，而移动到相邻的一列有 1 卢比的相关成本。

**示例:**

```py
Input: n = 2, m = 2, noOfPos = 2
pos[0] = 0, 0
pos[1] = 0, 1

Output: 1
The grid is of 2*2 size and there are two poles at {0, 0} and {0, 1}. 
So we will start at {0, 0} and paint the pole and then go to
the next column to paint the pole at {0, 1} position which will
cost 1 rupee to move one column. 

Input: n = 2, m = 2, noOfPos = 2
pos[0] = {0, 0}
pos[1] = {1, 0}
Output: 0
Both poles are in the same column. So, no need to move to another column. 
```

**进场:**由于在柱子中移动是唯一的成本，如果我们走到任何一根柱子上，我们会画出那根柱子上的所有柱子，然后向前移动。所以，基本上，答案将是最远的两列之间的差异。
以下是所需的实施:

## C++

```py
// C++ implementation of the above approach

#include <iostream>
#include <list>

using namespace std;

    // Function to find the cost to paint all poles
    void find(int n,int m,int p,int q[2][2])
    {
        // To store all the columns,create list
        list <int> z ;
        int i ;

        for(i = 0;i < p;i++)
            z.push_back(q[i][1]);

        // sort in ascending order
        z.sort();

        // z.back() gives max value
        // z.front() gives min value
        cout << z.back() - z.front() <<endl ;
    }

    // Driver code
    int main()
    {
        int n = 2;
        int m = 2;
        int p = 2;

        int q[2][2] = {{0,0},{0,1}} ;

        find(n, m, p, q);

       return 0;

    // This code is contributed by ANKITRAI1
    }
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation of the above approach

import java.util.*;
class solution
{

    // Function to find the cost to paint all poles
    static void find(int n,int m,int p,int q[][])
    {
        // To store all the columns,create list
        Vector <Integer> z= new Vector<Integer>() ;
        int i ;

        for(i = 0;i < p;i++)
            z.add(q[i][1]);

        // sort in ascending order
        Collections.sort(z);

        // z.back() gives max value
        // z.front() gives min value
        System.out.print(z.get(z.size()-1) - z.get(0) ) ;
    }

    // Driver code
    public static void main(String args[])
    {
        int n = 2;
        int m = 2;
        int p = 2;

        int q[][] = {{0,0},{0,1}} ;

        find(n, m, p, q);

    }

}
//contributed by Arnab Kundu
```

## 蟒蛇 3

```py
# Function to find the cost to paint all poles
import math as ma

def find(n, m, p, q):

    # To store all the columns
    z =[]
    for i in range(p):
        z.append(q[i][1])

    print(max(z)-min(z))

n, m, p = 2, 2, 2
q =[(0, 0), (0, 1)]
find(n, m, p, q)
```

## C#

```py
// C# implementation of the above approach
using System;
using System.Collections.Generic;

class GFG
{

    // Function to find the cost to paint all poles
    static void find(int n, int m, int p, int [,]q)
    {
        // To store all the columns,create list
        List <int> z = new List<int>();
        int i;

        for(i = 0; i < p; i++)
            z.Add(q[i, 1]);

        // sort in ascending order
        z.Sort();

        // z.back() gives max value
        // z.front() gives min value
        Console.Write(z[z.Count-1] - z[0]);
    }

    // Driver code
    public static void Main(String []args)
    {
        int n = 2;
        int m = 2;
        int p = 2;

        int [,]q = {{0, 0}, {0, 1}};

        find(n, m, p, q);
    }
}

// This code is contributed by PrinciRaj1992
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP implementation of the above approach

// Function to find the cost to
// paint all poles
function find($n, $m, $p, $q)
{
    // To store all the columns,
    // create an array
    $z = array();

    for($i = 0; $i < $p; $i++)
        array_push($z, $q[$i][1]);

    // sort in ascending order
    sort($z);

    echo max($z) - min($z);
}

// Driver code
$n = 2;
$m = 2;
$p = 2;

$q = array(array(0, 0),
            array(0, 1));

find($n, $m, $p, $q);

// This code is contributed by ita_c
?>
```

## java 描述语言

```py
<script>

// Javascript implementation of the above approach
// Function to find the cost to paint all poles
function find(n,m,p,q)
{
    // To store all the columns,create list
    var z = [];
    var i ;

    for(i = 0;i < p;i++)
        z.push(q[i][1]);

    // sort in ascending order
    z.sort();

    // z.back() gives max value
    // z.front() gives min value
    document.write( z[z.length-1] - z[0]);
}

// Driver code
var n = 2;
var m = 2;
var p = 2;

var q = [[0,0],[0,1]];

find(n, m, p, q);

</script>
```

**Output:** 

```py
1
```