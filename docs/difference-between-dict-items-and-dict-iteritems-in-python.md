# Python 中 dict.items()和 dict . items()的区别

> 原文:[https://www . geeksforgeeks . org/python 中 dict-items 和-dict-items 的区别/](https://www.geeksforgeeks.org/difference-between-dict-items-and-dict-iteritems-in-python/)

`dict.items()`和`dict.iteriteams()` almots 做的是同样的事情，但它们之间略有不同–

*   **dict.items():** 以(key，value)元组对的形式返回字典列表的副本，它是(Python v3.x)版本，存在于(Python v2.x)版本中。
*   **dict.iteritems():** 以(键、值)元组对的形式返回字典列表的迭代器。这是一个(Python v2.x)版本，在(Python v3.x)版本中被省略了。

**对于蟒蛇 2.x:**

**示例-1**

```
# Python2 code to demonstrate
# d.iteritems()

d ={
  "fantasy": "harrypotter",
  "romance": "me before you",
  "fiction": "divergent"
  }

# every time you run the object address keeps changes
print d.iteritems()
```

**输出:**

```
<dictionary-itemiterator object at 0x7f04628d5890>

```

要打印字典项目，使用`for()`循环分割对象并打印它们
**示例-2**

```
# Python2 code to demonstrate
# d.iteritems()

d ={
"fantasy": "harrypotter",
"romance": "me before you",
"fiction": "divergent"
}

for i in d.iteritems():

    # prints the items
    print(i)
```

**输出:**

```
('romance', 'me before you')
('fantasy', 'harrypotter')
('fiction', 'divergent')

```

如果我们试图在 Python v2.x 中运行 **dict.items()** ，它会像存在于 v2.x 中的 **dict.items()** 一样运行

**示例-3**

```
# Python2 code to demonstrate
# d.items()

d ={
  "fantasy": "harrypotter",
  "romance": "me before you",
  "fiction": "divergent"
  }

# places the tuples in a list.
print(d.items())

# returns iterators and never builds a list fully.
print(d.iteritems())
```

**输出:**

> [(‘浪漫’，‘你之前的我’)，(‘幻想’，‘哈利波特’，(‘虚构’，‘发散’)]
> <字典-itemiterator 对象在 0x7f1d78214890 >

**对于蟒蛇 3:**

**示例-1**

```
# Python3 code to demonstrate
# d.items()

d ={
  "fantasy": "harrypotter",
  "romance": "me before you",
  "fiction": "divergent"
  }

# saves as a copy
print(d.items())

```

**输出:**

> dict_items([('幻想'，'哈利波特')，('虚构'，'发散'，('浪漫'，'你之前的我'))])

如果我们试图在 Python v3.x 中运行`dict.iteritems()`，我们将返回一个错误。

**示例-2**

```
# Python3 code to demonstrate
# d.iteritems()

d ={
  "fantasy": "harrypotter",
  "romance": "me before you",
  "fiction": "divergent"
  }

print("d.items() in (v3.6.2) = ")
for i in d.items():

    # prints the items
    print(i)

print("\nd.iteritems() in (v3.6.2)=")

for i in d.iteritems():

    # prints the items
    print(i)
```

**输出:**

```
d.items() in (v3.6.2) = 
('fiction', 'divergent')
('fantasy', 'harrypotter')
('romance', 'me before you')

d.iteritems() in (v3.6.2)=

```

```
Traceback (most recent call last):
  File "/home/33cecec06331126ebf113f154753a9a0.py", line 19, in 
    for i in d.iteritems():
AttributeError: 'dict' object has no attribute 'iteritems'

```