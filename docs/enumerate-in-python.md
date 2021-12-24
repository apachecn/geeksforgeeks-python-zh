# Python 中枚举()

> 原文:[https://www.geeksforgeeks.org/enumerate-in-python/](https://www.geeksforgeeks.org/enumerate-in-python/)

通常，在处理迭代器时，我们也需要记录迭代次数。Python 通过为这个任务提供一个内置函数 enumerate()来简化程序员的任务。
Enumerate()方法向 iterable 添加一个计数器，并以枚举对象的形式返回。然后，这个枚举对象可以直接用于循环，或者使用 list()方法转换成元组列表。

**语法:**

```
enumerate(iterable, start=0)

Parameters:
Iterable: any object that supports iteration
Start: the index value from which the counter is 
              to be started, by default it is 0
```

## 蟒蛇 3

```
#python
# Python program to illustrate
# enumerate function
l1 = ["eat","sleep","repeat"]
s1 = "geek"

# creating enumerate objects
obj1 = enumerate(l1)
obj2 = enumerate(s1)

print ("Return type:",type(obj1))
print (list(enumerate(l1)))

# changing start index to 2 from 0
print (list(enumerate(s1,2)))
```

**输出:**

```
Return type: < type 'enumerate' >
[(0, 'eat'), (1, 'sleep'), (2, 'repeat')]
[(2, 'g'), (3, 'e'), (4, 'e'), (5, 'k')]
```

**在循环中使用枚举对象:**

## 蟒蛇 3

```
# Python program to illustrate
# enumerate function in loops
l1 = ["eat","sleep","repeat"]

# printing the tuples in object directly
for ele in enumerate(l1):
    print (ele)
print
# changing index and printing separately
for count,ele in enumerate(l1,100):
    print (count,ele)

#getting desired output from tuple
for count,ele in enumerate(l1):
  print(count)
  print(ele)
```

**输出:**

```
(0, 'eat')
(1, 'sleep')
(2, 'repeat')

100 eat
101 sleep
102 repeat

0
eat
1
sleep
2
repeat
```

本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果您发现任何不正确的地方，或者对上面讨论的主题有更多的信息，请写评论。