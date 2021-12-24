# Python 中的递增和递减运算符

> 原文:[https://www . geesforgeks . org/g-fact-21-python 中的递增和递减运算符/](https://www.geeksforgeeks.org/g-fact-21-increment-and-decrement-operators-in-python/)

如果你熟悉 Python，你应该知道增量和减量操作符(前置和后置)是不允许的。

Python 旨在保持一致性和可读性。在使用++和——运算符的语言中，新手程序员的一个常见错误是混淆了前/后递增/递减运算符之间的差异(在优先级和返回值方面)。简单的递增和递减运算符不像其他语言那样需要。

你不会写这样的东西:

```
for (int i = 0; i < 5; ++i)
```

对于正常使用，如果您正在增加计数，您可以使用，而不是 i++

```
i+=1 or i=i+1
```

相反，在 Python 中，我们编写如下，语法如下:

```
for variable_name in range(start, stop, step)
```

*   开始:可选。一个整数，指定从哪个位置开始。默认值为 0
*   stop:指定结束位置的整数。
*   步骤:可选。指定增量的整数。默认值为 1

## 蟒蛇 3

```
# A sample use of increasing the variable value by one.
count=0
count+=1
count=count+1
print('The Value of Count is',count)

# A Sample Python program to show loop (unlike many
# other languages, it doesn't use ++)
# this is for increment operator here start = 1,
# stop = 5 and step = 1(by default)
print("INCREMENTED FOR LOOP")
for i in range(0, 5):
   print(i)

# this is for increment operator here start = 5,
# stop = -1 and step = -1
print("\n DECREMENTED FOR LOOP")
for i in range(4, -1, -1):
   print(i)
```

**Output**

```
INCREMENTED FOR LOOP
0
1
2
3
4

 DECREMENTED FOR LOOP
4
3
2
1
0
```

```
Output-1: INCREMENTED FOR LOOP
0
1
2
3
4
Output-2: DECREMENTED FOR LOOP
4
3
2
1
0
```

本文由 Basavaraja 供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。