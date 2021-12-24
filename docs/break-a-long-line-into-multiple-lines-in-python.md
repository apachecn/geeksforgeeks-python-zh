# 在 Python 中把一条长线打断成多条线

> 原文:[https://www . geesforgeks . org/break-a-long-line-in-multi-line-python/](https://www.geeksforgeeks.org/break-a-long-line-into-multiple-lines-in-python/)

打断一长串与输出无关，它只是试图修复我们的代码是如何出现的。在一行中写一行很长的代码会让代码看起来不那么干净，而且很有可能会把它弄得很复杂。分解同一行可以增加代码的可读性，排除任何混乱，并且显然使它看起来更像样。通常，一行在跨越一定数量的字符后会经历除法运算。本文讨论了实现这一目标的所有方法:

**方法 1:** 使用反斜杠

一个反斜杠(\)可以放在线之间，使它看起来像下面显示的那样分开。还要注意，所有三种情况都产生完全相同的输出，唯一的区别是它们在代码中的呈现方式:

**示例:**

## 蟒蛇 3

```py
print("BEFORE BREAKING:")
print("How many times were you frustrated while looking out for a good collection of programming/ algorithm/ interview questions? What did you expect and what did you get? Geeks for geeks is a portal that has been created to provide well written, well thought and well explained solutions for selected questions.")

print()
print("AFTER BREAKING:")
print("How many times were you frustrated while looking out "\
      "for a good collection of programming/ algorithm/ "\
      "interview questions? What did you expect and what "\
      "did you get? Geeks for geeks is a portal that"\
      " has been created to provide well written, we"\
      "ll thought and well explained solutions for se"\
      "lected questions.")

print()
line = "How many times were you frustrated while looking out "\
    "for a good collection of programming/ algorithm/ "\
    "interview questions? What did you expect and what "\
    "did you get? Geeks for geeks is a portal that"\
    " has been created to provide well written, we"\
    "ll thought and well explained solutions for se"\
    "lected questions."
print("AFTER BREAKING USING A VARIABLE:")
print(line)
```

**输出:**

> 断裂前:
> 
> 有多少次你在寻找一个好的编程/算法/面试问题集时感到沮丧？你期待什么，得到了什么？极客为极客是一个门户网站，为选定的问题提供写得好、想得好、解释得好的解决方案。
> 
> 破碎后:
> 
> 有多少次你在寻找一个好的编程/算法/面试问题集时感到沮丧？你期待什么，得到了什么？极客为极客是一个门户网站，为选定的问题提供写得好、想得好、解释得好的解决方案。
> 
> 使用变量断开后:
> 
> 有多少次你在寻找一个好的编程/算法/面试问题集时感到沮丧？你期待什么，得到了什么？极客为极客是一个门户网站，为选定的问题提供写得好、想得好、解释得好的解决方案。

**方法 2:** 使用字符串连接运算符

字符串连接运算符(+)，如此基本的东西可以很容易地替换上例中的反斜杠，以给出相同的输出。

**示例:**

## 蟒蛇 3

```py
print("How many times were you" +
      " frustrated while looking" +
      " out for a good collection" +
      " of programming/ algorithm/" +
      "interview questions? What" +
      " did you expect and what " +
      "did you get? Geeks for gee" +
      "ks is a portal that has bee" +
      "n created to provide well wr" +
      "itten, well thought and wel" +
      "l explained solutions for se" +
      "lected questions.")
```

**输出:**

> 有多少次你在寻找一个好的编程/算法/面试问题集时感到沮丧？你期待什么，得到了什么？极客为极客是一个门户网站，为选定的问题提供写得好、想得好、解释得好的解决方案。

**方法 3:** 使用括号

通过将每个片段放在括号中，并用逗号(，)分隔每个片段，可以获得相同的输出。

**示例:**

## 蟒蛇 3

```py
print(("How many times were you"),
      ("frustrated while looking"),
      ("out for a good collection"),
      ("of programming/ algorithm/"),
      ("interview questions? What"),
      ("did you expect and what"),
      ("did you get? Geeks for geeks"),
      ("is a portal that has been"),
      ("created to provide well"),
      ("written, well thought and well"),
      ("explained solutions for"),
      ("selected questions."))
```

**输出:**

> 有多少次你在寻找一个好的编程/算法/面试问题集时感到沮丧？你期待什么，得到了什么？极客为极客是一个门户网站，为选定的问题提供写得好、想得好、解释得好的解决方案。