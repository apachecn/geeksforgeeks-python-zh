# Python 计数器和字典交集示例(使用删除和重排制作字符串)

> 原文:[https://www . geesforgeks . org/python-counter-dictionary-交集-example-make-string-use-delete-重排/](https://www.geeksforgeeks.org/python-counter-dictionary-intersection-example-make-string-using-deletion-rearrangement/)

给定两个字符串，通过从第二个字符串中删除一些字符并重新排列剩余的字符，找出我们是否可以从第二个字符串中创建第一个字符串。

示例:

```py
Input : s1 = ABHISHEKsinGH
      : s2 = gfhfBHkooIHnfndSHEKsiAnG
Output : Possible

Input : s1 = Hello
      : s2 = dnaKfhelddf
Output : Not Possible

Input : s1 = GeeksforGeeks
      : s2 = rteksfoGrdsskGeggehes
Output : Possible

```

对于这个问题我们已经有了解决方案，请参考[通过删除和重新排列字符](https://www.geeksforgeeks.org/make-string-another-deletion-rearrangement-characters/)链接从另一个字符串中创建一个字符串。我们将在 python 中快速解决这个问题。方法很简单，

1.  使用[计数器(可迭代)](https://www.geeksforgeeks.org/counters-in-python-set-1/)方法将两个字符串转换为字典，每个字典包含字符串中的字符作为键，它们的频率作为值。
2.  现在取两个字典的交集，将结果输出与第一个字符串的字典进行比较，如果两者相等，则意味着有可能**转换字符串，否则没有可能。**

```py
# Python code to find if we can make first string
# from second by deleting some characters from 
# second and rearranging remaining characters.
from collections import Counter

def makeString(str1,str2):

    # convert both strings into dictionaries
    # output will be like str1="aabbcc", 
    # dict1={'a':2,'b':2,'c':2}
    # str2 = 'abbbcc', dict2={'a':1,'b':3,'c':2}
    dict1 = Counter(str1)
    dict2 = Counter(str2)

    # take intersection of two dictionries
    # output will be result = {'a':1,'b':2,'c':2}
    result = dict1 & dict2

    # compare resultant dictionary with first
    # dictionary comparison first compares keys
    # and then compares their corresponding values 
    return result == dict1

# Driver program
if __name__ == "__main__":
    str1 = 'ABHISHEKsinGH'
    str2 = 'gfhfBHkooIHnfndSHEKsiAnG'
    if (makeString(str1,str2)==True):
        print("Possible")
    else:
        print("Not Possible")
```

输出:

```py
Possible

```