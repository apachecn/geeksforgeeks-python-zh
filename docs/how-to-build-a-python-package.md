# 如何构建 Python 包？

> 原文:[https://www . geesforgeks . org/如何构建 python 包/](https://www.geeksforgeeks.org/how-to-build-a-python-package/)

在本文中，我们将学习如何用 Python 开发包。包只不过是为执行某一组任务而设计的程序的集合。包有两种类型，即

*   *Set, date and time, sqlite and other built-in packages.*
*   Outer packaging such as *flask, django, tensorflow, etc.*

### 创建包

首先，我们需要想办法构造我们的代码，这样其他人就可以访问我们的代码功能。在 Python 中，要制作一个包，我们需要添加一个 *__init__。py* 到目录。在这里，我们将制作一个名为*测试包*的包。

*   Let's write *_ _ init _ _. py*

## python 3

```py
from collections import Counter

def count_in_list(l, word):
  c = Counter(l)
  return c[word]
```

*   Now, create a directory named *test _ package* and keep *_ _ init _ _ in it. Py* file. In this way, our package is ready. All our packages count the number of times a word appears in the list. Now, to use our package, create a *run.py* file outside the *test _ package* directory. In *run.py* , just import the newly created package and use the *count _ in _ list* function. We can write the code shown below.

## 蟒 3

```py
from test_package import count_in_list

l = ["gfg", "dsa", "gfg"]
count = count_in_list(l, "gfg")
print(count)
```