# Python |统计一对字符串中匹配字符的数量

> 原文:[https://www . geesforgeks . org/python-计算字符串对中匹配字符的数量/](https://www.geeksforgeeks.org/python-count-the-number-of-matching-characters-in-a-pair-of-string/)

给定一对非空字符串。计算这些字符串中匹配字符的数量(考虑字符串中重复字符的单一数量)。

**示例:**

```py
Input : str1 = 'abcdef'
        str2 = 'defghia'
Output : 4 
(i.e. matching characters :- a, d, e, f)

Input : str1 = 'aabcddekll12@'
        str2 = 'bb22ll@55k'
Output : 5 
(i.e. matching characters :- b, 1, 2, @, k)

```

**进场 1:**
1。用 0 初始化计数器变量。
2。从起始字符到结束字符迭代第一个字符串。
3。如果从第一个字符串中提取的字符出现在第二个字符串中，并且该提取的字符在第一个字符串中的第一个出现索引与当前提取的字符的索引相同，则将计数器的值增加 1。

> **注:**为此，在 python 中使用 **string.find(字符)**。
> 
> 这将返回字符串中第一个出现的字符索引(如果找到)，否则返回-1。
> 
> 例如:str = ' abcdde '
> str . find(' d ')–>3
> str . find(' e ')–>4
> str . find(' g ')–>-1

**4。**输出计数器的值。

下面是上述方法的实现。

```py
# Python code to count number of matching
# characters in a pair of strings

# count function
def count(str1, str2): 
    c, j = 0, 0

    # loop executes till length of str1 and 
    # stores value of str1 character by character 
    # and stores in i at each iteration.
    for i in str1:    

        # this will check if character extracted from
        # str1 is present in str2 or not(str2.find(i)
        # return -1 if not found otherwise return the 
        # starting occurrence index of that character
        # in str2) and j == str1.find(i) is used to 
        # avoid the counting of the duplicate characters
        # present in str1 found in str2
        if str2.find(i)>= 0 and j == str1.find(i): 
            c += 1
        j += 1
    print ('No. of matching characters are : ', c)

# Main function
def main(): 
    str1 ='aabcddekll12@' # first string
    str2 ='bb2211@55k' # second string
    count(str1, str2) # calling count function 

# Driver Code
if __name__=="__main__":
    main()
```

**输出:**

```py
No. of matching characters are : 5

```

**进场 2:**
1。在这种方法中，set()用于删除给定字符串上的重复项。
2。之后在给定的弦上使用[集合(交集)](https://www.geeksforgeeks.org/python-set-operations-union-intersection-difference-symmetric-difference/)的概念。
3。之后我们用 len()方法求出一个长度。

## 蟒蛇 3

```py
# Python code to count number of unique matching
# characters in a pair of strings

# count function count the common unique
# characters present in both strings .
def count(str1 ,str2) :
    # set of characters of string1
    set_string1 = set(str1)

    # set of characters of string2
    set_string2 = set(str2)

    # using (&) intersection mathematical operation on sets
    # the unique characters present in both the strings
    # are stored in matched_characters set variable
    matched_characters = set_string1 & set_string2

    # printing the length of matched_characters set
    # gives the no. of matched characters
    print("No. of matching characters are : " + str(len(matched_characters)) )

# Driver code
if __name__ == "__main__" :

    str1 = 'aabcddekll12@'  # first string
    str2 = 'bb2211@55k'     # second string

    # call count function 
    count( str1 , str2 )

```

**Output :**

```py
No. of matching characters are : 5

```

**进场 3:**

## 蟒蛇 3

```py
# Count the Number of matching characters in 
# a pair of string
import re
ip1 = "geeks"
ip2 = "geeksonly"

c = 0
for i in ip1:
    if re.search(i,ip2):
        c=c+1
print("No. of matching characters are ", c)
```

】

**Output :**

```py
No. of matching characters are : 5

```