# Python 程序输出|第三集

> 原文:[https://www.geeksforgeeks.org/output-python-program-set-3/](https://www.geeksforgeeks.org/output-python-program-set-3/)

**难度等级:**中级

预测以下 Python 程序的输出。

**程序 1:**

```py
class Geeks:
    def __init__(self, id):
        self.id = id

manager = Geeks(100)

manager.__dict__['life'] = 49

print (manager.life + len(manager.__dict__))
```

输出:

```py
51

```

**解释:**在上面的程序中，我们通过将名为“life”的成员变量直接添加到类“Geeks”的对象“manager”的字典中来创建它。字典中的项目总数是 2，变量是“生活”和“id”。因此，字典的大小或长度是 2，变量“life”被赋予一个值“49”。所以变量‘life’和字典大小的和是 49 + 2 = 51。

**节目 2:**

```py
a = "GeeksforGeeks "

b = 13

print (a + b)
```

输出:

```py
An error is shown.

```

**说明:**如你所见，变量‘b’为整型，变量‘a’为字符串型。同样，由于 Python 是一种强类型语言，我们不能简单地将整数和字符串连接起来。我们必须首先将整数变量转换为类型字符串，以将其与字符串变量连接起来。因此，试图将一个整数变量连接到一个字符串变量时，出现了一个类型为“类型错误”的异常。

**程序 3:**

```py
dictionary = {}
dictionary[1] = 1
dictionary['1'] = 2
dictionary[1] += 1

sum = 0
for k in dictionary:
    sum += dictionary[k]

print (sum)
```

输出:

```py
4

```

**说明:**在上面的字典中，括在单引号和只有 1 之间的键 1 代表两个不同的键，因为其中一个是整数，另一个是字符串。所以，程序的输出是 4。

**节目 4:**

```py
dictionary = {1:'1', 2:'2', 3:'3'}
del dictionary[1]
dictionary[1] = '10'
del dictionary[2]
print (len(dictionary))
```

输出:

```py
2

```

**解释:**del 函数的任务是从字典中移除键值对。最初给定字典的大小是 3。然后，首先删除键 1 的键值对，然后用新值添加回来。然后删除键 2 的键值对。最后，字典的大小是 2。

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。