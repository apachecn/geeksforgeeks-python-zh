# Python |检查给定字符串是否为二进制字符串

> 原文:[https://www . geesforgeks . org/python-检查给定字符串是否为二进制字符串/](https://www.geeksforgeeks.org/python-check-if-a-given-string-is-binary-string-or-not/)

给定一个字符串。任务是检查它是否是二进制字符串。
**例:**

```
Input: str = "01010101010"
Output: Yes

Input: str = "geeks101"
Output: No
```

**接近 1** :使用[设定](https://www.geeksforgeeks.org/sets-in-python/)T4】

1.  在集合中插入给定的字符串
2.  检查设定字符是否仅由 1 和/或 0 组成。

## 蟒蛇 3

```
# Python program to check
# if a string is binary or not

# function for checking the
# string is accepted or not
def check(string) :

    # set function convert string
    # into set of characters .
    p = set(string)

    # declare set of '0', '1' .
    s = {'0', '1'}

    # check set p is same as set s
    # or set p contains only '0'
    # or set p contains only '1'
    # or not, if any one condition
    # is true then string is accepted
    # otherwise not .
    if s == p or p == {'0'} or p == {'1'}:
        print("Yes")
    else :
        print("No")

# driver code
if __name__ == "__main__" :

    string = "101010000111"

    # function calling
    check(string)
```

**Output**

```
Yes
```

**方法 2:** 简单[迭代](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/)T4】

1.  对每个字符进行迭代，并检查字符是 0 还是 1。
2.  如果不是，则设置一个计数器并中断。
3.  迭代后检查计数器是否设置。

## 蟒蛇 3

```
# Python program to check
# if a string is binary or not

# function for checking the
# string is accepted or not
def check2(string) :

    # initialize the variable t
    # with '01' string
    t = '01'

    # initialize the variable count
    # with 0 value
    count = 0

    # looping through each character
    # of the string .
    for char in string :

        # check the character is present in
        # string t or not.
        # if this condition is true
        # assign 1 to the count variable
        # and break out of the for loop
        # otherwise pass
        if char not in t :
            count = 1
            break
        else :
            pass

    # after coming out of the loop
    # check value of count is non-zero or not
    # if the value is non-zero the en condition is true
    # and string is not accepted
    # otherwise string is accepted
    if count :
        print("No")
    else :
        print("Yes")

# driver code
if __name__ == "__main__" :

    string = "001021010001010"

    # function calling
    check2(string)
```

**Output**

```
No
```

**方法 3** : [正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

1.  使用 Compile()为“字符不是 0 或 1”编译正则表达式。
2.  使用 re.findall()获取满足上述正则表达式的字符串。
3.  根据结果打印输出。

## 蟒蛇 3

```
#import library
import re

sampleInput = "1001010"

# regular expression to find the strings
# which have characters other than 0 and 1
c = re.compile('[^01]')

# use findall() to get the list of strings
# that have characters other than 0 and 1.
if(len(c.findall(sampleInput))):
    print("No") # if length of list > 0 then it is not binary
else:
    print("Yes") # if length of list = 0 then it is binary
```

**Output**

```
Yes
```