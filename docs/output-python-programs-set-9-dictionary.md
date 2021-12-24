# Python 程序输出|集合 9(字典)

> 原文:[https://www . geesforgeks . org/output-python-programs-set-9-dictionary/](https://www.geeksforgeeks.org/output-python-programs-set-9-dictionary/)

**先决条件:** [**字典**](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)
**1)以下程序的输出是什么？**

## 计算机编程语言

```py
dictionary = {'GFG' : 'geeksforgeeks.org',
              'google' : 'google.com',
              'facebook' : 'facebook.com'
              }
del dictionary['google'];
for key, values in dictionary.items():
    print(key)
dictionary.clear();
for key, values in dictionary.items():
    print(key)
del dictionary;
for key, values in dictionary.items():
    print(key)
```

a)b 和 d 两者
b)运行时错误
c) GFG
脸书
d)脸书
GFG
T6】Ans。(一)
输出:

```py
facebook
GFG
```

**解释:**陈述:**德尔词典；**删除整个字典，因此迭代删除的字典会引发如下运行时错误:

```py
Traceback (most recent call last):
  File "cbeac2f0e35485f19ae7c07f6b416e84.py", line 12, in 
    for key, values in dictionary.items():
NameError: name 'dictionary' is not defined
```

**2)以下程序的输出是什么？**

## 计算机编程语言

```py
dictionary1 = {'Google' : 1,
               'Facebook' : 2,
               'Microsoft' : 3
               }
dictionary2 = {'GFG' : 1,
               'Microsoft' : 2,
               'Youtube' : 3
               }
dictionary1.update(dictionary2);
for key, values in dictionary1.items():
    print(key, values)
```

a)编译错误
b)运行时错误
c)(‘谷歌’，1)
(‘脸书’，2)
(‘Youtube’，3)
(‘微软’，2)
(‘GFG’，1)
d)这些
**都不是 Ans。(c)**
**说明:**dictionary1 . update(dictionary2)用于用 dictionary 2 的条目更新 dictionary 1 的条目。如果两个字典中有相同的键，则使用第二个字典中的值。

**3)以下程序的输出是什么？**

## 计算机编程语言

```py
dictionary1 = {'GFG' : 1,
               'Google' : 2,
               'GFG' : 3
               }
print(dictionary1['GFG']);
```

a)由于重复键
导致的编译错误 b)由于重复键
导致的运行时间错误 c)3
d)1
T4】Ans。(c)
**说明:**这里，GFG 是复制键。python 中不允许重复键。如果字典中有相同的键，则最近分配的**值**被分配给该键。

**4)以下程序的输出是什么？**

## 计算机编程语言

```py
temp = dict()
temp['key1'] = {'key1' : 44, 'key2' : 566}
temp['key2'] = [1, 2, 3, 4]
for (key, values) in temp.items():
    print(values, end = "")
```

a)编译错误
b) {'key1': 44，' key2': 566}[1，2，3，4]
c)运行时错误
d)以上
**Ans 均无。** (b)
**说明:**字典可以保存任何值，如整数、字符串、列表，甚至可以保存另一个保存键值对的字典。

**5)下面 Python 程序的输出是什么？**

## 计算机编程语言

```py
temp = {'GFG' : 1,
        'Facebook' : 2,
        'Google' : 3
        }
for (key, values) in temp.items():
    print(key, values, end = " ")
```

a)谷歌 3 GFG 1 脸书 2
b)脸书 2 GFG 1 谷歌 3
c)脸书 2 谷歌 3 GFG 1
d)以上任何一项

e)以上
**无一为 Ans。**(英)

**对(e)的解释:**由于 python 3.7 字典是按照插入顺序排序的。

本文由 [**Mayank Kumar**](https://www.linkedin.com/in/mayank-kumar-a9058b137/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。