# Python 中字符串上的逻辑运算符

> 原文:[https://www . geesforgeks . org/g-fact-43-逻辑运算符-python 中的字符串/](https://www.geeksforgeeks.org/g-fact-43-logical-operators-on-string-in-python/)

对于 python 中的字符串，布尔运算符(and，or，not)起作用。让我们考虑两个字符串，即 str1 和 str2，并对它们尝试布尔运算符:

## 蟒蛇 3

```py
str1 = ''
str2 = 'geeks'

# repr is used to print the string along with the quotes

# Returns str1
print(repr(str1 and str2)) 

# Returns str1  
print(repr(str2 and str1))

# Returns str2    
print(repr(str1 or str2))  

# Returns str2  
print(repr(str2 or str1))      

str1 = 'for'

# Returns str2
print(repr(str1 and str2)) 

# Returns str1  
print(repr(str2 and str1))

# Returns str1    
print(repr(str1 or str2)) 

# Returns str2    
print(repr(str2 or str1))      

str1='geeks'

# Returns False
print(repr(not str1))         

str1 = ''

# Returns True
print(repr(not str1))         

# Coded by Nikhil Kumar Singh(nickzuck_007)
```

**输出:**

```py
''
''
'geeks'
'geeks'
'geeks'
'for'
'for'
'geeks'
False
True
```

字符串之间布尔运算的输出取决于以下因素:

1.  Python 认为空字符串的布尔值为“假”，非空字符串的布尔值为“真”。
2.  对于“and”运算符，如果左值为真，则检查并返回右值。如果左值为假，则返回
3.  如果左值为真，则返回“或”运算符，否则，如果左值为假，则返回右值。

请注意，按位运算符(|、&)不适用于字符串。

本文由 [**尼基尔·库马尔·辛格**](https://www.facebook.com/nikhilkumar.singh.don) 供稿。
如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息