# Python 计数器查找字谜单词最大子集的大小

> 原文:[https://www . geesforgeks . org/python-counter-find-size-maximum-subset-anagram-words/](https://www.geeksforgeeks.org/python-counter-find-size-largest-subset-anagram-words/)

给定包含小写字母的 n 个字符串的数组。找出最大字符串子集的大小，这些字符串是彼此的字谜。字符串的字谜是另一个包含相同字符的字符串，只有字符的顺序可以不同。例如，“abcd”和“dabc”是彼此的字谜。

示例:

```py
Input: 
ant magenta magnate tan gnamate
Output: 3
Explanation
Anagram strings(1) - ant, tan
Anagram strings(2) - magenta, magnate,
                     gnamate
Thus, only second subset have largest
size i.e., 3

Input: 
cars bikes arcs steer 
Output: 2

```

对于这个问题我们已经有了解决方案，请参考[找到字谜单词最大子集的大小](https://www.geeksforgeeks.org/find-size-largest-subset-anagram-words/)链接。我们可以使用 [Counter()](https://www.geeksforgeeks.org/counters-in-python-set-1/) 方法在 python 中快速解决这个问题。方法很简单，

1.  Separate the input string into words with spaces.
2.  As we all know, if two strings contain the same character set, they are each other's puzzles. Therefore, in order to put all these strings together, we will first sort each string in the given string list.
3.  Now use the **counter** method to create a dictionary with strings as keys and their frequencies as values.
4.  Check the maximum frequency, which will be the largest subset of crossword strings.

```py
# Function to find the size of largest subset 
# of anagram words
from collections import Counter

def maxAnagramSize(input):

    # split input string separated by space
    input = input.split(" ")

    # sort each string in given list of strings
    for i in range(0,len(input)):
         input[i]=''.join(sorted(input[i]))

    # now create dictionary using counter method
    # which will have strings as key and their 
    # frequencies as value
    freqDict = Counter(input)

    # get maximum value of frequency
    print (max(freqDict.values()))

# Driver program
if __name__ == "__main__":
    input = 'ant magenta magnate tan gnamate'
    maxAnagramSize(input)
```

输出:

```py
3

```