# Python 词典理解

> 原文:[https://www . geesforgeks . org/python-dictionary-understance/](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

像[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)一样，Python 允许字典理解。我们可以使用简单的表达式来创建字典。
字典理解的形式是***{ key:iterable 中(key，value)的值}***

让我们看一个例子，假设我们现在有两个名为 key 和值的列表，

```
# Python code to demonstrate dictionary 
# comprehension

# Lists to represent keys and values
keys = ['a','b','c','d','e']
values = [1,2,3,4,5]  

# but this line shows dict comprehension here  
myDict = { k:v for (k,v) in zip(keys, values)}  

# We can use below too
# myDict = dict(zip(keys, values))  

print (myDict)
```

输出:

```
{'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}
```

我们也可以利用理解从一个列表中制作字典

```
# Python code to demonstrate dictionary 
# creation using list comprehension
myDict = {x: x**2 for x in [1,2,3,4,5]}
print (myDict)
```

输出:

```
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

类似的，

```
sDict = {x.upper(): x*3 for x in 'coding '}
print (sDict)
```

输出:

```
{'O': 'ooo', 'N': 'nnn', 'I': 'iii', 'C': 'ccc', 'D': 'ddd', 'G': 'ggg'}
```

我们可以在 if 和 else 语句以及其他表达式中使用字典理解。下面的示例将数字映射到不能被 4 整除的立方体:

```
# Python code to demonstrate dictionary 
# comprehension using if.
newdict = {x: x**3 for x in range(10) if x**3 % 4 == 0}
print(newdict)
```

输出:

```
{0: 0, 8: 512, 2: 8, 4: 64, 6: 216}
```

本文由 [**山塔奴夏尔马供稿。**](https://auth.geeksforgeeks.org/profile.php?user=Shantanu Sharma 2&list=practice) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。