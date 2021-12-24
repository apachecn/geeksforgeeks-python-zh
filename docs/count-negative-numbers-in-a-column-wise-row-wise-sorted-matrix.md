# 在按列和按行排序的矩阵中计算负数

> 原文:[https://www . geesforgeks . org/count-负数-按列-按行-按排序-矩阵/](https://www.geeksforgeeks.org/count-negative-numbers-in-a-column-wise-row-wise-sorted-matrix/)

在按列/行排序的矩阵 M[][]中找出负数的个数。假设 M 有 n 行 M 列。
例:

```py
Input:  M =  [-3, -2, -1,  1]
             [-2,  2,  3,  4]
             [4,   5,  7,  8]
Output : 4
We have 4 negative numbers in this matrix
```

**我们强烈建议你尽量减少浏览器，先自己试试这个。**
**天真的解决方案**
这里有一个天真的、非最优的解决方案。
我们从左上角开始，一个一个的数负数，从左到右，从上到下。
用给定的例子:

```py
[-3, -2, -1,  1]
[-2,  2,  3,  4]
[4,   5,  7,  8]

Evaluation process

[?,  ?,  ?,  1]
[?,  2,  3,  4]
[4,  5,  7,  8]
```

以下是上述想法的实现:

## C++

```py
// CPP implementation of Naive method
// to count of negative numbers in
// M[n][m]
#include <bits/stdc++.h>
using namespace std;

int countNegative(int M[][4], int n, int m)
{
    int count = 0;

    // Follow the path shown using
    // arrows above
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            if (M[i][j] < 0)
                count += 1;

            // no more negative numbers
            // in this row
            else
                break;
        }
    }
    return count;
}

// Driver program to test above functions
int main()
{
    int M[3][4] = { { -3, -2, -1, 1 },
                    { -2, 2, 3, 4 },
                    { 4, 5, 7, 8 } };

    cout << countNegative(M, 3, 4);
    return 0;
}
// This code is contributed by Niteesh Kumar
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation of Naive method
// to count of negative numbers in
// M[n][m]
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
    static int countNegative(int M[][], int n,
                             int m)
    {
        int count = 0;

        // Follow the path shown using
        // arrows above
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (M[i][j] < 0)
                    count += 1;

                // no more negative numbers
                // in this row
                else
                    break;
            }
        }
        return count;
    }

    // Driver program to test above functions
    public static void main(String[] args)
    {
        int M[][] = { { -3, -2, -1, 1 },
                      { -2, 2, 3, 4 },
                      { 4, 5, 7, 8 } };

        System.out.println(countNegative(M, 3, 4));
    }
}
// This code is contributed by Chhavi
```

## 计算机编程语言

```py
# Python implementation of Naive method to count of
# negative numbers in M[n][m]

def countNegative(M, n, m):
    count = 0

    # Follow the path shown using arrows above
    for i in range(n):
        for j in range(m):

            if M[i][j] < 0:
                count += 1

            else:
                # no more negative numbers in this row
                break
    return count

# Driver code
M = [
      [-3, -2, -1,  1],
      [-2,  2,  3,  4],
      [ 4,  5,  7,  8]
    ]
print(countNegative(M, 3, 4))
```

## C#

```py
// C# implementation of Naive method
// to count of negative numbers in
// M[n][m]
using System;

class GFG {

    // Function to count
    // negative number
    static int countNegative(int[, ] M, int n,
                             int m)
    {
        int count = 0;

        // Follow the path shown
        // using arrows above
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (M[i, j] < 0)
                    count += 1;

                // no more negative numbers
                // in this row
                else
                    break;
            }
        }
        return count;
    }

    // Driver Code
    public static void Main()
    {
        int[, ] M = { { -3, -2, -1, 1 },
                      { -2, 2, 3, 4 },
                      { 4, 5, 7, 8 } };

        Console.WriteLine(countNegative(M, 3, 4));
    }
}

// This code is contributed by Sam007
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP implementation of Naive method
// to count of negative numbers in
// M[n][m]

function countNegative($M, $n, $m)
{
    $count = 0;

    // Follow the path shown using
    // arrows above
    for( $i = 0; $i < $n; $i++)
    {
        for( $j = 0; $j < $m; $j++)
        {
            if( $M[$i][$j] < 0 )
                $count += 1;

            // no more negative numbers
            // in this row
            else
                break;
        }
    }
    return $count;
}

    // Driver Code
    $M = array(array(-3, -2, -1, 1),
               array(-2, 2, 3, 4),
               array(4, 5, 7, 8));

    echo countNegative($M, 3, 4);

// This code is contributed by anuj_67.
?>
```

## java 描述语言

```py
<script>

// JavaScript implementation of Naive method
// to count of negative numbers in
// M[n][m]
function  countNegative(M,n,m)
    {
        let count = 0;

        // Follow the path shown using
        // arrows above
        for (let i = 0; i < n; i++) {
            for (let j = 0; j < m; j++) {
                if (M[i][j] < 0)
                    count += 1;

                // no more negative numbers
                // in this row
                else
                    break;
            }
        }
        return count;
    }

    // Driver program to test above functions

        let M = [[ -3, -2, -1, 1 ],
                    [ -2, 2, 3, 4 ],
                    [ 4, 5, 7, 8 ]];

        document.write(countNegative(M, 3, 4));

// This code is contributed by sravan kumar

</script>
```

**输出:**

```py
4
```

在这种方法中，我们遍历所有元素，因此，在最坏的情况下(当矩阵中所有数字都是负数时)，这需要 O(n * m)时间。
**最优解**
这里有一个更高效的解决方案:

1.  我们从右上角开始，找到第一行最后一个负数的位置。
2.  利用这个信息，我们找到第二行最后一个负数的位置。
3.  我们不断重复这个过程，直到我们用完负数或者到达最后一行。

```py
With the given example:
[-3, -2, -1,  1]
[-2,  2,  3,  4]
[4,   5,  7,  8]

Here's the idea:
[-3, -2,  ?,  ?] -> Found 3 negative numbers in this row
[ ?,  ?,  ?,  4] -> Found 1 negative number in this row
[ ?,  5,  7,  8] -> No negative numbers in this row 
```

## C++

```py
// CPP implementation of Efficient
// method to count of negative numbers
// in M[n][m]
#include <bits/stdc++.h>
using namespace std;

int countNegative(int M[][4], int n, int m)
{
    // initialize result
    int count = 0;

    // Start with top right corner
    int i = 0;
    int j = m - 1;

    // Follow the path shown using
    // arrows above
    while (j >= 0 && i < n) {
        if (M[i][j] < 0) {
            // j is the index of the
            // last negative number
            // in this row. So there
            // must be ( j+1 )
            count += j + 1;

            // negative numbers in
            // this row.
            i += 1;
        }

        // move to the left and see
        // if we can find a negative
        // number there
        else
            j -= 1;
    }

    return count;
}

// Driver program to test above functions
int main()
{
    int M[3][4] = { { -3, -2, -1, 1 },
                    { -2, 2, 3, 4 },
                    { 4, 5, 7, 8 } };

    cout << countNegative(M, 3, 4);

    return 0;
}
// This code is contributed by Niteesh Kumar
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation of Efficient
// method to count of negative numbers
// in M[n][m]
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {
    static int countNegative(int M[][], int n,
                             int m)
    {
        // initialize result
        int count = 0;

        // Start with top right corner
        int i = 0;
        int j = m - 1;

        // Follow the path shown using
        // arrows above
        while (j >= 0 && i < n) {
            if (M[i][j] < 0) {
                // j is the index of the
                // last negative number
                // in this row. So there
                // must be ( j+1 )
                count += j + 1;

                // negative numbers in
                // this row.
                i += 1;
            }

            // move to the left and see
            // if we can find a negative
            // number there
            else
                j -= 1;
        }
        return count;
    }

    // Driver program to test above functions
    public static void main(String[] args)
    {
        int M[][] = { { -3, -2, -1, 1 },
                      { -2, 2, 3, 4 },
                      { 4, 5, 7, 8 } };

        System.out.println(countNegative(M, 3, 4));
    }
}
// This code is contributed by Chhavi
```

## 计算机编程语言

```py
# Python implementation of Efficient method to count of
# negative numbers in M[n][m]

def countNegative(M, n, m):

    count = 0 # initialize result

    # Start with top right corner
    i = 0
    j = m - 1 

    # Follow the path shown using arrows above
    while j >= 0 and i < n:

        if M[i][j] < 0:

            # j is the index of the last negative number
            # in this row.  So there must be ( j + 1 )
            count += (j + 1)

            # negative numbers in this row.
            i += 1

        else:
            # move to the left and see if we can
            # find a negative number there
             j -= 1
    return count

# Driver code
M = [
      [-3, -2, -1,  1],
      [-2,  2,  3,  4],
      [4,   5,  7,  8]
    ]
print(countNegative(M, 3, 4))
```

## C#

```py
// C# implementation of Efficient
// method to count of negative
// numbers in M[n][m]
using System;

class GFG {

    // Function to count
    // negative number
    static int countNegative(int[, ] M, int n,
                             int m)
    {

        // initialize result
        int count = 0;

        // Start with top right corner
        int i = 0;
        int j = m - 1;

        // Follow the path shown
        // using arrows above
        while (j >= 0 && i < n) {
            if (M[i, j] < 0) {
                // j is the index of the
                // last negative number
                // in this row. So there
                // must be ( j + 1 )
                count += j + 1;

                // negative numbers in
                // this row.
                i += 1;
            }

            // move to the left and see
            // if we can find a negative
            // number there
            else
                j -= 1;
        }
        return count;
    }

    // Driver Code
    public static void Main()
    {
        int[, ] M = { { -3, -2, -1, 1 },
                      { -2, 2, 3, 4 },
                      { 4, 5, 7, 8 } };

        Console.WriteLine(countNegative(M, 3, 4));
    }
}

// This code is contributed by Sam007
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```py
<?php
// PHP implementation of Efficient
// method to count of negative numbers
// in M[n][m]

function countNegative( $M, $n, $m)
{

    // initialize result
    $count = 0;

    // Start with top right corner
    $i = 0;
    $j = $m - 1;

    // Follow the path shown using
    // arrows above
    while( $j >= 0 and $i < $n )
    {
        if( $M[$i][$j] < 0 )
        {
            // j is the index of the
            // last negative number
            // in this row. So there
            // must be ( j+1 )
            $count += $j + 1;

            // negative numbers in
            // this row.
            $i += 1;
        }

        // move to the left and see
        // if we can find a negative
        // number there
        else
        $j -= 1;
    }

    return $count;
}

    // Driver Code
    $M = array(array(-3, -2, -1, 1),
               array(-2, 2, 3, 4),
               array(4, 5, 7, 8));

    echo countNegative($M, 3, 4);

    return 0;

// This code is contributed by anuj_67.
?>
```

## java 描述语言

```py
<script>
    // Javascript implementation of Efficient
    // method to count of negative numbers
    // in M[n][m]q   
    function countNegative(M, n, m)
    {

        // initialize result
        let count = 0;

        // Start with top right corner
        let i = 0;
        let j = m - 1;

        // Follow the path shown using
        // arrows above
        while (j >= 0 && i < n)
        {
            if (M[i][j] < 0)
            {

                // j is the index of the
                // last negative number
                // in this row. So there
                // must be ( j+1 )
                count += j + 1;

                // negative numbers in
                // this row.
                i += 1;
            }

            // move to the left and see
            // if we can find a negative
            // number there
            else
                j -= 1;
        }
        return count;
    }

    let M = [ [ -3, -2, -1, 1 ],
               [ -2, 2, 3, 4 ],
               [ 4, 5, 7, 8 ] ];

      document.write(countNegative(M, 3, 4));
 `
 // This code is contributed by decode2207.
</script>
```

**输出:**

```py
4
```

有了这个解决方案，我们现在可以在 O(n + m)时间内解决这个问题。
**【更多最优解】**
这里有一个使用二分搜索法代替线性搜索的更有效的解决方案:

1.  我们从第一行开始，用二分搜索法找到第一行最后一个负数的位置。
2.  利用这些信息，我们通过只运行二分搜索法直到上一行中最后一个负数的位置来找到第二行中最后一个负数的位置。
3.  我们不断重复这个过程，直到我们用完负数或者到达最后一行。

```py
With the given example:
[-3, -2, -1,  1]
[-2,  2,  3,  4]
[4,   5,  7,  8]

Here's the idea:
1\. Count is initialized to 0
2\. Binary search on full 1st row returns 2 as the index 
   of last negative integer, and we increase count to 0+(2+1) = 3.
3\. For 2nd row, we run binary search from index 0 to index 2 
   and it returns 0 as the index of last negative integer. 
   We increase the count to 3+(0+1) = 4;
4\. For 3rd row, first element is > 0, so we end the loop here.
```

## C++

```py
// C++ implementation of More efficient
// method to count number of negative numbers
// in row-column sorted matrix M[n][m]
#include<bits/stdc++.h>
using namespace std;

// Recursive binary search to get last negative
// value in a row between a start and an end
int getLastNegativeIndex(int array[], int start,
                       int end,int n)
{
    // Base case
    if (start == end)
    {
        return start;
    }

    // Get the mid for binary search
    int mid = start + (end - start) / 2;

    // If current element is negative
    if (array[mid] < 0)
    {

        // If it is the rightmost negative
        // element in the current row
        if (mid + 1 < n && array[mid + 1] >= 0)
        {
            return mid;
        }

        // Check in the right half of the array
        return getLastNegativeIndex(array,
                                mid + 1, end, n);
    }
    else
    {

        // Check in the left half of the array
        return getLastNegativeIndex(array,
                                start, mid - 1, n);
    }
}

// Function to return the count of
// negative numbers in the given matrix
int countNegative(int M[][4], int n, int m)
{

    // Initialize result
    int count = 0;

    // To store the index of the rightmost negative
    // element in the row under consideration
    int nextEnd = m - 1;

    // Iterate over all rows of the matrix
    for (int i = 0; i < n; i++)
    {

        // If the first element of the current row
        // is positive then there will be no negatives
        // in the matrix below or after it
        if (M[i][0] >= 0)
        {
            break;
        }

        // Run binary search only until the index of last
        // negative Integer in the above row
        nextEnd = getLastNegativeIndex(M[i], 0, nextEnd, 4);
        count += nextEnd + 1;
    }
    return count;
}

// Driver code
int main()
{
    int M[][4] = { { -3, -2, -1, 1 },
                    { -2, 2, 3, 4 },
                    { 4, 5, 7, 8 } };
    int r = 3;
    int c = 4;
    cout << (countNegative(M, r, c));
    return 0;
}

// This code is contributed by Arnab Kundu
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation of More efficient
// method to count number of negative numbers
// in row-column sorted matrix M[n][m]
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG {

    // Recursive binary search to get last negative
    // value in a row between a start and an end
    static int getLastNegativeIndex(int array[], int start, int end)
    {
        // Base case
        if (start == end) {
            return start;
        }

        // Get the mid for binary search
        int mid = start + (end - start) / 2;

        // If current element is negative
        if (array[mid] < 0) {

            // If it is the rightmost negative
            // element in the current row
            if (mid + 1 < array.length && array[mid + 1] >= 0) {
                return mid;
            }

            // Check in the right half of the array
            return getLastNegativeIndex(array, mid + 1, end);
        }
        else {

            // Check in the left half of the array
            return getLastNegativeIndex(array, start, mid - 1);
        }
    }

    // Function to return the count of
    // negative numbers in the given matrix
    static int countNegative(int M[][], int n, int m)
    {

        // Initialize result
        int count = 0;

        // To store the index of the rightmost negative
        // element in the row under consideration
        int nextEnd = m - 1;

        // Iterate over all rows of the matrix
        for (int i = 0; i < n; i++) {

            // If the first element of the current row
            // is positive then there will be no negatives
            // in the matrix below or after it
            if (M[i][0] >= 0) {
                break;
            }

            // Run binary search only until the index of last
            // negative Integer in the above row
            nextEnd = getLastNegativeIndex(M[i], 0, nextEnd);
            count += nextEnd + 1;
        }
        return count;
    }

    // Driver code
    public static void main(String[] args)
    {
        int M[][] = { { -3, -2, -1, 1 },
                      { -2, 2, 3, 4 },
                      { 4, 5, 7, 8 } };
        int r = M.length;
        int c = M[0].length;
        System.out.println(countNegative(M, r, c));
    }
}
// This code is contributed by Rahul Jain
```

## 蟒蛇 3

```py
# Python3 implementation of More efficient
# method to count number of negative numbers
# in row-column sorted matrix M[n][m]

# Recursive binary search to get last negative
# value in a row between a start and an end
def getLastNegativeIndex(array, start, end, n):

    # Base case
    if (start == end):
        return start

    # Get the mid for binary search
    mid = start + (end - start) // 2

    # If current element is negative
    if (array[mid] < 0):

        # If it is the rightmost negative
        # element in the current row
        if (mid + 1 < n and array[mid + 1] >= 0):

            return mid

        # Check in the right half of the array
        return getLastNegativeIndex(array, mid + 1, end, n)

    else:

        # Check in the left half of the array
        return getLastNegativeIndex(array, start, mid - 1, n)

# Function to return the count of
# negative numbers in the given matrix
def countNegative(M, n, m):

    # Initialize result
    count = 0

    # To store the index of the rightmost negative
    # element in the row under consideration
    nextEnd = m - 1

    # Iterate over all rows of the matrix
    for i in range(n):

        # If the first element of the current row
        # is positive then there will be no negatives
        # in the matrix below or after it
        if (M[i][0] >= 0):
            break

        # Run binary search only until the index of last
        # negative Integer in the above row
        nextEnd = getLastNegativeIndex(M[i], 0, nextEnd, 4)
        count += nextEnd + 1
    return count

# Driver code

M = [[-3, -2, -1, 1],[-2, 2, 3, 4],[ 4, 5, 7, 8]]
r = 3
c = 4
print(countNegative(M, r, c))

# This code is contributed by shubhamsingh10
```

## C#

```py
// C# implementation of More efficient
// method to count number of negative numbers
// in row-column sorted matrix M[n,m]
using System;
using System.Collections.Generic;

class GFG
{

    // Recursive binary search to get last negative
    // value in a row between a start and an end
    static int getLastNegativeIndex(int []array, int start, int end)
    {
        // Base case
        if (start == end)
        {
            return start;
        }

        // Get the mid for binary search
        int mid = start + (end - start) / 2;

        // If current element is negative
        if (array[mid] < 0)
        {

            // If it is the rightmost negative
            // element in the current row
            if (mid + 1 < array.GetLength(0) && array[mid + 1] >= 0)
            {
                return mid;
            }

            // Check in the right half of the array
            return getLastNegativeIndex(array, mid + 1, end);
        }
        else
        {

            // Check in the left half of the array
            return getLastNegativeIndex(array, start, mid - 1);
        }
    }

    // Function to return the count of
    // negative numbers in the given matrix
    static int countNegative(int [,]M, int n, int m)
    {

        // Initialize result
        int count = 0;

        // To store the index of the rightmost negative
        // element in the row under consideration
        int nextEnd = m - 1;

        // Iterate over all rows of the matrix
        for (int i = 0; i < n; i++)
        {

            // If the first element of the current row
            // is positive then there will be no negatives
            // in the matrix below or after it
            if (M[i, 0] >= 0)
            {
                break;
            }

            // Run binary search only until the index of last
            // negative int in the above row
            nextEnd = getLastNegativeIndex(GetRow(M, i), 0, nextEnd);
            count += nextEnd + 1;
        }
        return count;
    }
    public static int[] GetRow(int[,] matrix, int row)
    {
        var rowLength = matrix.GetLength(1);
        var rowVector = new int[rowLength];

        for (var i = 0; i < rowLength; i++)
            rowVector[i] = matrix[row, i];

        return rowVector;
    }

    // Driver code
    public static void Main(String[] args)
    {
        int [,]M = { { -3, -2, -1, 1 },
                    { -2, 2, 3, 4 },
                    { 4, 5, 7, 8 } };
        int r = M.GetLength(0);
        int c = M.GetLength(1);
        Console.WriteLine(countNegative(M, r, c));
    }
}

// This code is contributed by PrinciRaj1992
```

## java 描述语言

```py
<script>

// JavaScript implementation of More efficient
// method to count number of negative numbers
// in row-column sorted matrix M[n,m]
// Recursive binary search to get last negative
// value in a row between a start and an end
function getLastNegativeIndex(array, start, end)
{
    // Base case
    if (start == end)
    {
        return start;
    }
    // Get the mid for binary search
    var mid = start + parseInt((end - start) / 2);
    // If current element is negative
    if (array[mid] < 0)
    {
        // If it is the rightmost negative
        // element in the current row
        if (mid + 1 < array.length && array[mid + 1] >= 0)
        {
            return mid;
        }
        // Check in the right half of the array
        return getLastNegativeIndex(array, mid + 1, end);
    }
    else
    {
        // Check in the left half of the array
        return getLastNegativeIndex(array, start, mid - 1);
    }
}
// Function to return the count of
// negative numbers in the given matrix
function countNegative(M, n, m)
{
    // Initialize result
    var count = 0;
    // To store the index of the rightmost negative
    // element in the row under consideration
    var nextEnd = m - 1;
    // Iterate over all rows of the matrix
    for (var i = 0; i < n; i++)
    {
        // If the first element of the current row
        // is positive then there will be no negatives
        // in the matrix below or after it
        if (M[i][0] >= 0)
        {
            break;
        }
        // Run binary search only until the index of last
        // negative int in the above row
        nextEnd = getLastNegativeIndex(GetRow(M, i), 0, nextEnd);
        count += nextEnd + 1;
    }
    return count;
}

function GetRow(matrix, row)
{
    var rowLength = matrix[0].length;
    var rowVector = Array(rowLength).fill(0);
    for (var i = 0; i < rowLength; i++)
        rowVector[i] = matrix[row][i];
    return rowVector;
}

// Driver code
var M = [ [ -3, -2, -1, 1 ],
            [ -2, 2, 3, 4 ],
            [ 4, 5, 7, 8 ] ];
var r = M.length;
var c = M[0].length;
document.write(countNegative(M, r, c));

</script>
```

**输出:**

```py
4
```

这里我们用二分搜索法代替了对最后一个负数的线性搜索。这将改善最差情况，保持最差情况为 0(nlog(m))。
本文由**YK·杉田****拉胡尔·贾恩**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。