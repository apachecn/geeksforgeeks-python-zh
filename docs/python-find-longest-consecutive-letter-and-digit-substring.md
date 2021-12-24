# Python |查找最长的连续字母和数字子串

> 原文:[https://www . geesforgeks . org/python-find-最长连续字母数字子串/](https://www.geeksforgeeks.org/python-find-longest-consecutive-letter-and-digit-substring/)

给定一个字符串(可能包含字母和数字)，编写一个 Python 程序来查找最长的连续字母和数字子字符串。

**示例:**

```
Input : geeks123available
Output : ('available', 123)

Input : 98apple658pine
Output : ('apple', 658)

```

**方法#1 :** 蛮力
这是寻找最长的连续字母和数字子串的幼稚或蛮力方法。我们取两个字符串型变量*最长字母*和*最长数字*。我们开始一个循环，检查字母和数字的连续子串。在每次迭代中，我们分别检查当前字母子串是否长于最长的字母或数字子串。如果是，我们将字母和数字的当前子串分别分配给最长的字母和数字子串。否则，什么都不做。

```
# Python3 program to find the longest 
# consecutive substring of a certain type
import re

def longestSubstring(s):

    longest_letterSeq = ''
    longest_digitSeq = ''
    i = 0
    while(i<len(s)):

        curr_letterSeq = ''
        curr_digitSeq = ''

        # For letter substring 
        while(i<len(s) and s[i].isalpha()):
            curr_letterSeq += s[i]
            i+= 1

        # For digit substring
        while(i<len(s) and s[i].isdigit()):
            curr_digitSeq += s[i]
            i+= 1

        # Case handling if the character 
        # is neither letter nor digit    
        if(i< len(s) and not(s[i].isdigit()) 
                     and not(s[i].isalpha())) :
            i+= 1

        if(len(curr_letterSeq) > len(longest_letterSeq) ):
            longest_letterSeq = curr_letterSeq

        if(len(curr_digitSeq) > len(longest_digitSeq) ):
            longest_digitSeq = curr_digitSeq

    return longest_letterSeq, longest_digitSeq

# Driver Code
str = '3Geeksfor123geeks3'
print(longestSubstring(str))
```

**Output:**

```
('Geeksfor', '123')

```

**方法 2 :** 使用 Python 正则表达式
[Python 正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)是解决给定问题的另一种方法。使用 Python 正则表达式找到数字和字母的子串序列，然后分别找到最长的子串长度。

```
# Python3 program to find the longest 
# consecutive substring of a certain type
import re

def longestSubstring(str):
    letter = max(re.findall(r'\D+', str), key = len)
    digit = max(re.findall(r'\d+', str), key = len)

    return letter, digit

# Driver Code
str = 'geeks123geeksforgeeks1'
print(longestSubstring(str))
```

**Output:**

```
('geeksforgeeks', '123')

```