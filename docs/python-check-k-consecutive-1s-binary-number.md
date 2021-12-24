# Python |检查二进制数中是否有 K 个连续的 1

> 原文:[https://www . geesforgeks . org/python-check-k-continuous-1s-binary-number/](https://www.geeksforgeeks.org/python-check-k-consecutive-1s-binary-number/)

给定 K 和一个二进制数，检查二进制数中是否存在 K 个连续的 1。

示例:

```
Input : binary number = 101010101111
            k = 4 
Output : yes
Explanation: at the last 4 index there exists
4 consecutive 1's

Input : binary number = 11100000 k=5 
Output : no
Explanation: There is a maximum of 3 consecutive 
1's in the given binary.

```

**方法:**用 k 1 的创建一个**新字符串。使用 if 条件检查 s 中是否有新的。在 python 中**如果 s 中有新的:**检查 s 中是否有新的存在，因此如果有，则返回 true，否则返回 false。**

*下面是上面方法的 Python 实现:*

```
# Python program to check if there 
# is k consecutive 1's in a binary number 

# function to check if there are k 
# consecutive 1's 
def check(s,k):

    # form a new string of k 1's 
    new = "1"*k 

    # if there is k 1's at any position 
    if new in s:
        print "yes" 
    else:
        print "no" 

# driver code
s = "10101001111"
k = 4 
check(s, k)
```

输出:

```
yes

```