# Python 中的类和实例属性

> 原文:[https://www . geesforgeks . org/class-instance-attributes-python/](https://www.geeksforgeeks.org/class-instance-attributes-python/)

**类属性**

[类属性](https://www.geeksforgeeks.org/g-fact-34-class-or-static-variables-in-python/)属于类本身，它们将被所有实例共享。这样的属性通常在类主体部分的顶部定义，以便于阅读。

```py
# Write Python code here
class sampleclass:
    count = 0     # class attribute

    def increase(self):
        sampleclass.count += 1

# Calling increase() on an object
s1 = sampleclass()
s1.increase()        
print(s1.count)

# Calling increase on one more
# object
s2 = sampleclass()
s2.increase()
print(s2.count)

print(sampleclass.count)
```

输出:

```py
1              
2                           
2
```

**实例属性**

与类属性不同，实例属性不被对象共享。每个对象都有自己的实例属性副本(在类属性的情况下，所有对象都引用单个副本)。

要列出实例/对象的属性，我们有两个函数:-
1。**vars()**–该函数以字典的形式显示实例的属性。
2。**dir()**–该函数比 vars 函数显示更多的属性，因为它不限于实例。它还显示类属性。它还显示其祖先类的属性。

```py
# Python program to demonstrate
# instance attributes.
class emp:
    def __init__(self):
        self.name = 'xyz'
        self.salary = 4000

    def show(self):
        print(self.name)
        print(self.salary)

e1 = emp()
print("Dictionary form :", vars(e1))
print(dir(e1))
```

输出:

```py
Dictionary form :{'salary': 4000, 'name': 'xyz'}
['__doc__', '__init__', '__module__', 'name', 'salary', 'show']
```

本文由 [**【严酷的瓦雷查】**](https://auth.geeksforgeeks.org/profile.php?user=Harsh Valecha) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。