# 在 Python 中更改类成员

> 原文:[https://www . geesforgeks . org/g-fact-42-changing-class-members-python/](https://www.geeksforgeeks.org/g-fact-42-changing-class-members-python/)

在[之前的事实](https://www.geeksforgeeks.org/g-fact-34-class-or-static-variables-in-python/)中，我们已经看到 Python 没有静态关键字。在类声明中被赋值的所有变量都是类变量。

***我们在改变一个类变量的值时要小心*** 。如果我们试图用一个对象来改变一个类变量，那么这个特定对象的一个新的实例(或者非静态)变量就会被创建，这个变量会隐藏类变量。下面是一个 Python 程序来演示这一点。

## 蟒蛇 3

```py
# Class for Computer Science Student
class CSStudent:
    stream = 'cse'     # Class Variable
    def __init__(self, name, roll):
        self.name = name
        self.roll = roll

# Driver program to test the functionality
# Creating objects of CSStudent class
a = CSStudent("Geek", 1)
b = CSStudent("Nerd", 2)

print ("Initially")
print ("a.stream =", a.stream )
print ("b.stream =", b.stream )

# This thing doesn't change class(static) variable
# Instead creates instance variable for the object
# 'a' that shadows class member.
a.stream = "ece"

print ("\nAfter changing a.stream")
print ("a.stream =", a.stream )
print ("b.stream =", b.stream )
```

**输出:**

```py
Initially
a.stream = cse
b.stream = cse

After changing a.stream
a.stream = ece
b.stream = cse
```

***我们应该只使用类名来更改类变量。**T3】*

## 蟒蛇 3

```py
# Program to show how to make changes to the
# class variable in Python

# Class for Computer Science Student
class CSStudent:
    stream = 'cse'     # Class Variable
    def __init__(self, name, roll):
        self.name = name
        self.roll = roll

# New object for further implementation
a = CSStudent("check", 3)
print "a.stream =", a.stream

# Correct way to change the value of class variable
CSStudent.stream = "mec"
print "\nClass variable changes to mec"

# New object for further implementation
b = CSStudent("carter", 4)

print "\nValue of variable steam for each object"
print "a.stream =", a.stream
print "b.stream =", b.stream
```

**输出:**

```py
a.stream = cse

Class variable changes to mec

Value of variable steam for each object
a.stream = mec
b.stream = mec
```

本文由**尼基尔·库马尔·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息