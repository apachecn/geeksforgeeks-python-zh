# 精确地在一个位置上不同的线对的计数

> 原文:[https://www . geeksforgeeks . org/每对字符串中恰好有一个位置不同的计数/](https://www.geeksforgeeks.org/count-of-pairs-of-strings-which-differ-in-exactly-one-position/)

给定等长字符串的数组 **arr[]** 。任务是计算恰好在一个位置不同的字符串对的总数。

**示例:**

> **输入:**arr[]= {“ABC”、“abd”、“bbd”}
> **输出:** 2
> (abc、abd)和(abd、bbd)是唯一有效的对。
> 
> **输入:**arr[]= {“def”、“deg”、“dmf”、“xef”、“dxg”}
> **输出:** 4

**方法 1:** 对于每一个可能的对，通过对字符串的单次遍历，检查两个字符串是否恰好在单个索引位置不同。

**方法 2:** 可以通过以下方式比较两个字符串，以检查它们在单个索引位置是否不同:

> 让**str 1 =“ABC”**和**str 2 =“ADC”**
> 对于 **str1** ，添加**“# BC”**、**“a # c”**和**“ab #”**到一个[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)。
> 现在对于 **str2** ，以类似的方式生成字符串，如果任何生成的字符串
> 已经存在于集合中，则两个字符串在精确的 1 个索引位置上不同。
> 例如，**“a # c”**就是生成的字符串之一。
> **注意**使用“#”是因为它不会是任何原始字符串的一部分。

以下是上述方法的实现:

## C++

```
// CPP implementation of the approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the count of same pairs
int pairCount(map<string, int> &d)
{
    int sum = 0;
    for (auto i : d)
        sum += (i.second * (i.second - 1)) / 2;

    return sum;
}

// Function to return total number of strings
// which satisfy required condition
int difference(vector<string> &array, int m)
{
    // Dictionary changed will store strings
    // with wild cards
    // Dictionary same will store strings
    // that are equal
    map<string, int> changed, same;

    // Iterating for all strings in the given array
    for (auto s : array)
    {
        // If we found the string then increment by 1
        // Else it will get default value 0
        same[s]++;

        // Iterating on a single string
        for (int i = 0; i < m; i++)
        {
            // Adding special symbol to the string
            string t = s.substr(0, i) + "//" + s.substr(i + 1);

            // Incrementing the string if found
            // Else it will get default value 0
            changed[t]++;
        }
    }

    // Return counted pairs - equal pairs
    return pairCount(changed) - pairCount(same) * m;
}

// Driver Code
int main()
{
    int n = 3, m = 3;
    vector<string> array = {"abc", "abd", "bbd"};
    cout << difference(array, m) << endl;

    return 0;
}

// This code is contributed by
// sanjeev2552
```

## 蟒蛇 3

```
# Python3 implementation of the approach

# Function to return the count of same pairs
def pair_count(d):
    return sum((i*(i-1))//2 for i in d.values())

# Function to return total number of strings 
# which satisfy required condition
def Difference(array, m):

    # Dictionary changed will store strings 
    # with wild cards
    # Dictionary same will store strings 
    # that are equal
    changed, same = {}, {}

    # Iterating for all strings in the given array
    for s in array:

        # If we found the string then increment by 1 
        # Else it will get default value 0
        same[s]= same.get(s, 0)+1

        # Iterating on a single string
        for i in range(m):
            # Adding special symbol to the string
            t = s[:i]+'#'+s[i + 1:]

            # Incrementing the string if found 
            # Else it will get default value 0
            changed[t]= changed.get(t, 0)+1

    # Return counted pairs - equal pairs
    return pair_count(changed) - pair_count(same)*m

# Driver code
if __name__=="__main__":
    n, m = 3, 3
    array =["abc", "abd", "bbd"]
    print(Difference(array, m))
```

**Output:**

```
2

```