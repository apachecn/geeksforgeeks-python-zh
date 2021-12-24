# Python |获取包含给定模式所有字符的字符串中最小的窗口

> 原文:[https://www . geesforgeks . org/python-获取包含给定模式所有字符的最小字符串窗口/](https://www.geeksforgeeks.org/python-get-the-smallest-window-in-a-string-containing-all-characters-of-given-pattern/)

给定两个字符串 *str* 和*模式*，在包含模式所有字符的 *str* 中找到最小的子字符串。

**示例:**

```
Input : str = 'geeksforgeeks' pattern = 'gks' 
Output : geeks

Input : str = 'new string' pattern = 'rg' 
Output : ring

```

**方法#1 :** 使用 Python *枚举()*T5】此方法使用 Python `enumerate()`。*需要【k】*存储我们需要多少次字符 *k* 而缺失则告诉我们还有多少字符缺失。在循环中，首先将新字符添加到窗口中。然后，如果没有遗漏任何内容，尽可能从窗口开始处删除，然后更新结果。

```
string = 'new string'
pattern = 'rg'

# let's find the index of r and g in String and the
# stor them in index list (index[]) 
index=[]
for x in range(len(pattern)):
    if pattern[x] in string:
        index.append(string.index(pattern[x]))

# sorting the r and g index's
index.sort()

# save first index in l
l = len(index)
low = int(index[0])

# save  last index in h
high = int(index[l-1])
h = high +1
for i in range(low,h):
    print(string[i],end=" ")
```

**Output:**

```
ksf

```

**方法 2 :** 使用`collections.defaultdict()`
这种方法使用两个缺省值“src”和“dest”。A *defaultdict* 的工作方式与普通 dict 完全一样，但它是用一个不接受参数的函数(“默认工厂”)初始化的。*源*为空，而*目标*由模式元素作为键，出现次数作为值组成。在每次迭代“I”中，我们检查*目标*字典中是否存在*字符串*的 *i <sup>th</sup>* 元素，并相应更新*源*字典。

```
# Python3 code to Find the smallest 
# window in a string containing all 
# characters of another string
from collections import defaultdict
import sys
def min_window(str, pattern):

        # Function to check validity of source and 
        # destination
        def isValid(i, j):
            for item in j:
                if item not in i or i[item] < j[item]:
                    return False
            return True

        source = defaultdict(int)
        target = defaultdict(int)

        # Target consist pattern elements and 1 
        # as key:value pair
        for e in pattern:
            target[e] += 1

        # Minimum length for window    
        minLen = sys.maxsize
        n = len(str)
        ans, j = '', 0 
        for i in range(n):

            # Update source for valid source - target pair
            while j < n and (isValid(source, target) == False):
                source[str[j]] += 1
                j += 1

            # Checking validity of source-target pair
            if isValid(source, target):
                if minLen > j-i + 1:
                    minLen = j-i + 1
                    ans = str[i:j]
            source[str[i]] -= 1
        return ans

# Driver Code
string = "geekforgeeks"
pattern = "gks"
print(min_window(string, pattern))
```

**Output:**

```
geeks

```

**方法#3 :** 动态方法
在这个方法中，我们使用一个 for 循环，在每次迭代中，比如说 I，我们找到以 I 结束并包含模式中所有字母的最短间隔。这可以通过考虑两种数据结构来实现，即“RPO”和“rdict”。rpos 是一个排序的位置列表，其中保存了字符串中模式字符的最右边位置，rdict 是一个从字符到位置的字典映射。rdict 的值与 RPO 相同。

```
# Python3 code to Find the smallest 
# window in a string containing all 
# characters of another string
from collections import Counter, defaultdict

def min_window(str, pattern):

    rdict, count = defaultdict(list), Counter(pattern)
    rpos, res = [], "" 

    # Loop only over c exist in pattern
    for i, c in filter(lambda x: x[1] in pattern, enumerate(str)): 
        if len(rdict) == count: 

            # If reached limit, remove
            rpos.remove(rdict.pop(0))

        # Add to dict
        rdict[i].append(i)

        # Add to list
        rpos.append(i) 

        if (len(rpos) == len(pattern) and
           (res =="" or rpos[-1]-rpos[0]<len(res))):
            res = str[rpos[0]:rpos[-1]+1] 

    return res

# Driver Code
string = "geeksforgeeks"
pattern = "gks"
print(min_window(string, pattern))
```

**Output:**

```
geeks

```