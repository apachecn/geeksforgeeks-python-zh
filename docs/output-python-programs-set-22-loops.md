# Python 程序的输出|第 22 集(循环)

> 原文:[https://www . geesforgeks . org/output-python-programs-set-22-loops/](https://www.geeksforgeeks.org/output-python-programs-set-22-loops/)

**先决条件:** [循环](https://www.geeksforgeeks.org/loops-in-python/)
T5】注:所有这些程序的输出都在 Python3 上测试

##### 1.下面的输出是什么？

```py
mylist = ['geeks', 'forgeeks']
for i in mylist:
    i.upper()
print(mylist)
```

1.  ['GEEKS '，' FORGEKS ']。
2.  ['极客'，'伪装者']。
3.  [无，无]。
4.  意外的

输出:

```py
2\. [‘geeks’, ‘forgeeks’]

```

**解释:**函数 ***upper()*** 不会就地修改字符串，而是返回一个没有存储在任何地方的新字符串。

##### 2.下面的输出是什么？

```py
mylist = ['geeks', 'forgeeks']
for i in mylist:
    mylist.append(i.upper())
print(mylist)
```

1.  ['GEEKS '，' FORGEKS ']。
2.  ['geeks '，' forgeeks '，' geeks '，' FORGEEKS']。
3.  [无，无]。
4.  这些都不是

输出:

```py
4\. None of these

```

**解释:**循环不会终止，因为在每次迭代中都有新元素被添加到列表中。

##### 3.下面的输出是什么？

```py
i = 1
while True:
    if i % 0O7 == 0:
        break
    print(i)
    i += 1
```

1.  1 2 3 4 5 6.
2.  1 2 3 4 5 6 7.
3.  错误。
4.  这些都不是

输出:

```py
1\. 1 2 3 4 5 6

```

**说明:**当 ***i*** 等于 7 时，循环终止。

##### 4.下面的输出是什么？

```py
True = False
while True:
    print(True)
    break
```

1.  假的。
2.  没错。
3.  错误。
4.  这些都不是

输出:

```py
3\. Error

```

**说明:**语法错误，**T3】真 T5】是关键字，其值不可更改。**

##### 5.下面的输出是什么？

```py
i = 1
while True:
    if i % 3 == 0:
        break
    print(i)
    i + = 1
```

1.  1 2 3.
2.  1 2.
3.  语法错误。
4.  这些都不是

输出:

```py
3\. Syntax Error

```

**说明:**语法错误，**中+和=之间不应该有空格*+=*T5】。**