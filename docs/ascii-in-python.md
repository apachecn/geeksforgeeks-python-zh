# Python 中的 ascii()

> 原文:[https://www.geeksforgeeks.org/ascii-in-python/](https://www.geeksforgeeks.org/ascii-in-python/)

**Python ascii()函数**返回包含对象的可打印表示的字符串，并使用 **\x，\u 或\U 转义**来转义字符串中的非 ascii 字符。

> **语法:** ascii(对象)

该方法只能接受一个参数，对象可以是列表、字符串等。如前所述，它返回一个对象的可打印表示。

### Python ascii()函数示例

```
Input : ascii("¥")
Output : '\xa5'

Input : ascii("µ")
Output : '\xb5'

Input : ascii("Ë")
Output : '\xcb'
```

我们看到，在这些例子中，所有的非 ascii 字符都被转义了，也就是说，它们的编码代码是通过使用 ASCII()方法显示的。

**例 1:**

在这个例子中，字符串包含非 ASCII 字符，我们的任务是显示给定字符串的 ASCII 值。

## 蟒蛇 3

```
# Python program to illustrate ascii()
str = "G ë ê k s f ? r G ? e k s"
print (ascii(str))
```

**输出:**

```
'G \xeb \xea k s f ? r G ? e k s'
```

**例 2:**

这里我们取一个带有多行字符串的变量，并将其传递到 ascii()中，它返回“\n”，新行的值是“\n”。

## 蟒蛇 3

```
str = '''Geeks
for
geeks'''
print(ascii(str))
```

**输出:**

```
'Geeks\nfor\ngeeks'
```

## ascii()与 print():

这里我们将看到 ascii()函数和 print()函数之间的区别。为此，我们采用了带有多行字符串的变量，并尝试用这两个函数来显示它们。代码执行后，您将获得不同的输出，因为 ascii()函数转义非 ASCII 字符，而 print 函数 print 不转义该值。

## 蟒蛇 3

```
str = '''Geeks
for
geeks'''
print("Display with ascii function : ",ascii(str))
print("Display with print function : ",str)
```

**输出:**

```
Display with ascii function :  'Geeks\nfor\ngeeks'
Display with print function :  Geeks
for
geeks
```

本文由 [**【钦莫伊蕾恩卡】**](https://www.linkedin.com/in/lenkachinmoy/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。