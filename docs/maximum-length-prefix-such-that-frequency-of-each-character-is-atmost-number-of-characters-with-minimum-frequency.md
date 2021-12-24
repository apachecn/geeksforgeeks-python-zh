# 最大长度前缀，每个字符的频率是最小频率的字符数

> 原文:[https://www . geeksforgeeks . org/最大长度前缀-每个字符的频率是-大气-最小频率的字符数/](https://www.geeksforgeeks.org/maximum-length-prefix-such-that-frequency-of-each-character-is-atmost-number-of-characters-with-minimum-frequency/)

给定一个字符串 **S** ，任务是找到具有最大可能长度的字符串 **S** 的前缀，使得前缀中每个字符的频率最多是 S 中具有最小频率的字符数。

**示例:**

> **输入:** S = 'aabcdaab'
> **输出:** aabcd
> **说明:**
> 给定字符串中字符的出现频率–
> { a:4，b: 2，c: 1，d: 1}
> 最小出现频率在 1，最小出现频率的计数为 2，
> 所以前缀中每个字符的出现频率最多可以为 2。
> 
> **输入:** S = 'aaabc'
> **输出:** aa
> **解释:**
> 给定字符串中字符的出现频率–
> { a:3，b: 1，c: 1}
> 最小出现频率为 1，最小出现频率的计数为 2，
> 因此前缀中每个字符的出现频率最多为 2。

**进场:**

*   初始化一个[哈希映射](https://www.geeksforgeeks.org/hashing-data-structure/)来存储字符的频率。
*   迭代字符串并增加字符在哈希映射中的出现频率。
*   找出字符串中出现次数最少的字符，以及出现次数最少的字符数。
*   初始化另一个哈希映射来存储可能的前缀字符串的字符频率。
*   最后，从头开始迭代字符串，并增加字符的计数，直到任何字符的频率不大于最小频率的计数。

下面是上述方法的实现:

## C++

```py
// C++ implementation to find the prefix
// of the s such that occurrence of each
// character is atmost the count of minimum
// frequency in the s
#include <bits/stdc++.h>
using namespace std;

// Function to find the maximum
// possible prefix of the s
void MaxPrefix(string s)
{

    // Hash map to store the frequency
    // of the characters in the s
    map<char, int> Dict;

    // Iterate over the s to find
    // the occurence of each Character
    for(char i : s)
    {
        Dict[i]++;
    }

    int minfrequency = INT_MAX;

    // Minimum frequency of the Characters
    for(auto x : Dict)
    {
        minfrequency = min(minfrequency, x.second);
    }

    int countminFrequency = 0;

    // Loop to find the count of minimum
    // frequency in the hash-map
    for(auto x: Dict)
    {
        if (x.second == minfrequency)
            countminFrequency += 1;
    }
    map<char, int> mapper;

    int indi = 0;

    // Loop to find the maximum possible
    // length of the prefix in the s
    for(char i: s)
    {
        mapper[i] += 1;

        // Condition to check if the frequency
        // is greater than minimum possible freq
        if (mapper[i] > countminFrequency)
            break;

        indi += 1;
    }

    // maxprefix s and its length.
    cout << (s.substr(0, indi));
}

// Driver code
int main()
{

    // s is initialize.
    string str = "aabcdaab";

    // str is passed in
    // MaxPrefix function.
    MaxPrefix(str);
}

// This code is contributed by mohit kumar 29
```

## Java 语言(一种计算机语言，尤用于创建网站)

```py
// Java implementation to find the prefix
// of the s such that occurrence of each
// character is atmost the count of minimum
// frequency in the s
import java.util.*;
import java.lang.*;
import java.io.*;

class GFG{

// Function to find the maximum
// possible prefix of the s
static void MaxPrefix(String s)
{   

    // Hash map to store the frequency
    // of the characters in the s
    Map<Character,
        Integer> Dict = new HashMap<>();

    // Iterate over the s to find
    // the occurence of each Character
    for(char i : s.toCharArray())
    {
        Dict.put(i, Dict.getOrDefault(i, 0) + 1);
    }

    int minfrequency = Integer.MAX_VALUE;

    // Minimum frequency of the Characters
    for(Integer x: Dict.values())
    {
        minfrequency = Math.min(minfrequency, x);   
    }

    int countminFrequency = 0;

    // Loop to find the count of minimum
    // frequency in the hash-map
    for(Map.Entry<Character,
                  Integer> x: Dict.entrySet())
    {
        if (x.getValue() == minfrequency)
            countminFrequency += 1;
    }

   Map<Character,
       Integer> mapper = new HashMap<>();

    int indi = 0;

    // Loop to find the maximum possible
    // length of the prefix in the s
    for(char i: s.toCharArray())
    {
        mapper.put(i, mapper.getOrDefault(i, 0) + 1);

        // Condition to check if the frequency
        // is greater than minimum possible freq
        if (mapper.get(i) > countminFrequency)
            break;

        indi += 1;
    }

    // maxprefix s and its length.
    System.out.println(s.substring(0, indi));
}

// Driver code
public static void main(String[] args)
{

    // s is initialize.
    String str = "aabcdaab";

    // str is passed in
    // MaxPrefix function.
    MaxPrefix(str);
}
}

// This code is contributed by offbeat
```

## 蟒蛇 3

```py
# Python3 implementation to find the
# prefix of the string such that
# occurrence of each character is
# atmost the count of minimum
# frequency in the string

# Function to find the maximum
# possible prefix of the string
def MaxPrefix(string):

    # Hash map to store the frequency
    # of the characters in the string
    Dict = {}
    maxprefix = 0

    # Iterate over the string to find
    # the occurence of each Character
    for i in string:
        Dict[i] = Dict.get(i, 0) + 1

    # Minimum frequency of the Characters
    minfrequency = min(Dict.values())
    countminFrequency = 0

    # Loop to find the count of minimum
    # frequency in the hash-map
    for x in Dict:
        if (Dict[x] == minfrequency):
            countminFrequency += 1

    mapper = {}
    indi = 0

    # Loop to find the maximum possible
    # length of the prefix in the string   
    for i in string:
        mapper[i] = mapper.get(i, 0) + 1

        # Condition to check if the frequency
        # is greater than minimum possible freq
        if (mapper[i] > countminFrequency):
            break
        indi += 1

    # maxprefix string and its length.
    print(string[:indi])

# Driver code
if __name__ == '__main__':

    # String is initialize.
    str = 'aabcdaab'
    # str is passed in MaxPrefix function.
    MaxPrefix(str)
```

## C#

```py
// C# implementation to find the
// prefix of the s such that
// occurrence of each character is
// atmost the count of minimum
// frequency in the s
using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;

class GFG{

// Function to find the maximum
// possible prefix of the s
static void MaxPrefix(string s)
{   

    // Hash map to store the frequency
    // of the characters in the s
    Dictionary<char,
               int> Dict = new Dictionary<char,
                                          int>();

    // Iterate over the s to find
    // the occurence of each Character
    foreach(char i in s)
    {
        if (Dict.ContainsKey(i))
        {
            Dict[i]++;
        }
        else
        {
            Dict[i] = 1;
        }
    }

    int minfrequency = Int32.MaxValue;

    // Minimum frequency of the Characters
    foreach(int x in Dict.Values.ToList())
    {
        minfrequency = Math.Min(minfrequency, x);   
    }

    int countminFrequency = 0;

    // Loop to find the count of minimum
    // frequency in the hash-map
    foreach(char x in Dict.Keys.ToList())
    {
        if (Dict[x] == minfrequency)
            countminFrequency += 1;
    }

    Dictionary<char,
               int> mapper = new Dictionary<char,
                                            int>();
    int indi = 0;

    // Loop to find the maximum possible
    // length of the prefix in the s
    foreach(char i in s)
    {
        if (mapper.ContainsKey(i))
        {
            mapper[i]++;
        }
        else
        {
            mapper[i] = 1;
        }

        // Condition to check if the frequency
        // is greater than minimum possible freq
        if (mapper[i] > countminFrequency)
            break;

        indi += 1;
    }

    // maxprefix s and its length.
    Console.Write(s.Substring(0, indi));
}

// Driver Code
public static void Main(string[] args)
{

    // s is initialize.
    string str = "aabcdaab";

    // str is passed in
    // MaxPrefix function.
    MaxPrefix(str);
}
}

// This code is contributed by rutvik_56
```

## java 描述语言

```py
<script>

      // JavaScript implementation to find the
      // prefix of the s such that
      // occurrence of each character is
      // atmost the count of minimum
      // frequency in the s

      // Function to find the maximum
      // possible prefix of the s
      function MaxPrefix(s) {
        // Hash map to store the frequency
        // of the characters in the s
        var Dict = {};

        // Iterate over the s to find
        // the occurence of each Character
        for (const i of s) {
          if (Dict.hasOwnProperty(i)) {
            Dict[i]++;
          } else {
            Dict[i] = 1;
          }
        }

        var minfrequency = 2147483647;

        // Minimum frequency of the Characters
        for (const [key, value] of Object.entries(Dict)) {
          minfrequency = Math.min(minfrequency, value);
        }

        var countminFrequency = 0;

        // Loop to find the count of minimum
        // frequency in the hash-map
        for (const [key, value] of Object.entries(Dict)) {
          if (Dict[key] === minfrequency) countminFrequency += 1;
        }

        var mapper = {};
        var indi = 0;

        // Loop to find the maximum possible
        // length of the prefix in the s
        for (const i of s) {
          if (mapper.hasOwnProperty(i)) {
            mapper[i]++;
          } else {
            mapper[i] = 1;
          }

          // Condition to check if the frequency
          // is greater than minimum possible freq
          if (mapper[i] > countminFrequency) break;

          indi += 1;
        }

        // maxprefix s and its length.
        document.write(s.substring(0, indi));
      }

      // Driver Code
      // s is initialize.
      var str = "aabcdaab";

      // str is passed in
      // MaxPrefix function.
      MaxPrefix(str);

 </script>
```

**Output:** 

```py
aabcd
```

**性能分析:**

*   **时间复杂度:**在上面给出的方法中，有一个循环来寻找字符串中每个字符的频率，在最坏的情况下需要 O(N)个时间。因此，该方法的时间复杂度为 **O(N)** 。
*   **空间复杂度:**在上面给定的方法中，有额外的空间用于存储字符的频率。因此，上述方法的空间复杂度为 **O(N)**