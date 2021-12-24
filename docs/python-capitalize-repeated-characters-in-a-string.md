# Python–将字符串中重复的字符大写

> 原文:[https://www . geesforgeks . org/python-大写-字符串中重复字符/](https://www.geeksforgeeks.org/python-capitalize-repeated-characters-in-a-string/)

给定一个带有小写字母的输入字符串，任务是编写一个 python 程序来识别字符串中的重复字符并将其大写。

**示例:**

> **输入:**编程语言
> 
> **输出:**编程语言
> 
> **说明:** r、m、n、a、g 为重复元素
> 
> **输入:**极客为极客
> 
> **输出:**极客的极客
> 
> **说明:** g、e、k、s 为重复元素

**进场:**

*   我们必须将字符串的字符作为关键字，并将字符串中每个字符的频率作为字典中的值。
*   遍历字符串并使用字典检查每个字符的频率。如果字符的频率大于 1，则使用 [upper()](https://www.geeksforgeeks.org/isupper-islower-lower-upper-python-applications/) 函数将字符更改为大写。

**实施:**

## 蟒蛇 3

```
# function for changing the
# repeated characters to uppercase
def RepeatedUpper(s):

    # declaring dictionary
    dic = {}

    # Traversing the string
    for i in s:

        # If the character is already
        # present in dictionary then increment
        # the frequency of the character
        if i in dic:
            dic[i] = dic[i]+1

   # If the character is not present in
   # the dictionary then inserting
   # the character in the dictionary
        else:
            dic[i] = 1
    ans = ''

    # traversing the string
    for i in s:

        # if the frequency of the character is
        # greater than one
        if dic[i] > 1:

            # change into uppercase
            i = i.upper()

        # appending each character to the ans
        ans = ans+i
    return ans

# Driver code
s = 'geeks for geeks'
# fuction call
print(RepeatedUpper(s))
```

**输出:**

```
GEEKS for GEEKS
```

**时间复杂度:** O(n)

**空间复杂度:** O(n)