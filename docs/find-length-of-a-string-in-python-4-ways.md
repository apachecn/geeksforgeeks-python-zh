# 用 python 查找字符串长度(4 种方式)

> 原文:[https://www . geesforgeks . org/find-python 中的字符串长度-4 路/](https://www.geeksforgeeks.org/find-length-of-a-string-in-python-4-ways/)

[Python 中的字符串](https://www.geeksforgeeks.org/python-strings/)是**不可变的**Unicode 代码点序列。给定一个字符串，我们需要找到它的长度。

示例:

```
Input : 'abc'
Output : 3

Input : 'hello world !'
Output : 13

Input : ' h e l   l  o '
Output :14

```

方法:

*   使用内置功能镜头。内置函数 len 返回容器中的项目数。

    ```
    # Python code to demonstrate string length 
    # using len

    str = "geeks"
    print(len(str))
    ```

    **输出:**

    ```
    5

    ```

*   用于循环和 in 运算符。字符串可以直接在 for 循环中迭代。保持迭代次数的计数将导致字符串的长度。

    ```
    # Python code to demonstrate string length 
    # using for loop

    # Returns length of string
    def findLen(str):
        counter = 0    
        for i in str:
            counter += 1
        return counter

    str = "geeks"
    print(findLen(str))
    ```

    **输出:**

    ```
    5

    ```

*   使用 while 循环和切片。我们在每次迭代中将一个字符串剪短 1，最终会得到一个空字符串。这是 while 循环停止的时候。保持迭代次数的计数将导致字符串的长度。

    ```
    # Python code to demonstrate string length 
    # using while loop.

    # Returns length of string
    def findLen(str):
        counter = 0
        while str[counter:]:
            counter += 1
        return counter

    str = "geeks"
    print(findLen(str))
    ```

    **输出:**

    ```
    5

    ```

*   使用字符串方法连接和计数。strings 的 join 方法接受一个 iterable 并返回一个字符串，该字符串是 iterable 中字符串的串联。元素之间的分隔符是调用方法的原始字符串。使用联接并计算原始字符串中的联接字符串也会导致字符串的长度。

    ```
    # Python code to demonstrate string length 
    # using join and count

    # Returns length of string
    def findLen(str):
        if not str:
            return 0
        else:
            some_random_str = 'py'
            return ((some_random_str).join(str)).count(some_random_str) + 1

    str = "geeks"
    print(findLen(str))
    ```

    **输出:**

    ```
    5

    ```