# Python 中的最大()和最小()

> 原文:[https://www.geeksforgeeks.org/max-min-python/](https://www.geeksforgeeks.org/max-min-python/)

这篇文章给大家带来了一个非常有趣的，不太为人所知的 Python 函数，即 [max()](https://www.geeksforgeeks.org/python-max-function/) 和 [min()](https://www.geeksforgeeks.org/python-min-function/) 。现在，与它们的 C++对应物相比，后者只允许两个参数，严格来说是 float、int 或 char，这些函数**不仅仅限于 2 个元素**，而且**可以容纳许多元素作为参数，并且还支持字符串**作为它们的参数，因此也允许显示字典上最小或最大的字符串。详细功能解释如下。

[**max()**](https://www.geeksforgeeks.org/python-max-function/)

此函数用于计算在其参数中传递的值的最大值，如果字符串作为参数传递，则计算字典中的最大值。

```py
Syntax : 
max(a,b,c,..,key,default)
Parameters : 
a,b,c,.. :  similar type of data.
key : key function where the iterables are passed and comparison is performed
default : default value is passed if the given iterable is empty
Return Value : 
Returns the maximum of all the arguments.
Exceptions : 
Returns TypeError when conflicting types are compared.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# max()

# printing the maximum of 4,12,43.3,19,100
print("Maximum of 4,12,43.3,19 and 100 is : ",end="")
print (max( 4,12,43.3,19,100 ) )
```

输出:

```py
Maximum of 4,12,43.3,19 and 100 is : 100
```

[**min()**](https://www.geeksforgeeks.org/python-min-function/)

此函数用于计算在其参数中传递的值的最小值，如果字符串作为参数传递，则计算字典中的最小值。

```py
Syntax : 
min(a,b,c,.., key,default)
Parameters : 
a,b,c,.. :  similar type of data.
key : key function where the iterables are passed and comparison is performed
default : default value is passed if the given iterable is empty
Return Value : 
Returns the minimum of all the arguments.
Exceptions : 
Returns TypeError when conflicting types are compared.
```

## 蟒蛇 3

```py
# Python code to demonstrate the working of
# min()

# printing the minimum of 4,12,43.3,19,100
print("Minimum of 4,12,43.3,19 and 100 is : ",end="")
print (min( 4,12,43.3,19,100 ) )
```

输出:

```py
Minimum of 4,12,43.3,19 and 100 is : 4
```

**Exception**

**1。类型错误:**这些函数在比较**冲突的数据类型时抛出类型错误**。

## 蟒蛇 3

```py
# Python code to demonstrate the Exception of
# min() and max()

# printing the minimum of 4,12,43.3,19, "GeeksforGeeks"
# Throws Exception
print("Minimum of 4,12,43.3,19 and GeeksforGeeks is : ",end="")
print (min( 4,12,43.3,19,"GeeksforGeeks" ) )
```

输出:

```py
Minimum of 4,12,43.3,19 and GeeksforGeeks is : 
```

运行时错误:

```py
Traceback (most recent call last):
  File "/home/b5da1d7f834a267f94fbbefe1b31a83c.py", line 7, in 
    print (min( 4,12,43.3,19,"GeeksforGeeks" ) )
TypeError: unorderable types: str() < int()
```

**Practical Application**

许多实际应用中的一个是找到按字典顺序排列的最大和最小的字符串，即在字典中最先出现或最后出现的字符串。

## 蟒蛇 3

```py
# Python code to demonstrate the Application of
# min() and max()

# printing the word occurring 1st among these in dict.
# "geeks", "manjeet", "algorithm", "programming"
print("The word occurring 1st in dict. among given is : ",end="")
print (min( "geeks", "manjeet", "algorithm", "programming" ) )

# printing the word occurring last among these in dict.
# "geeks", "manjeet", "algorithm", "programming"
print("The word occurring last in dict. among given is : ",end="")
print (max( "geeks", "manjeet", "algorithm", "programming" ) )
```

输出:

```py
The word occurring 1st in dict. among given is : algorithm
The word occurring last in dict. among given is : programming
```

本文由 [**【曼吉特·辛格】**](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。