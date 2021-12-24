# Python 程序输出|第 5 集

> 原文:[https://www.geeksforgeeks.org/output-python-program-set-5/](https://www.geeksforgeeks.org/output-python-program-set-5/)

预测以下程序的输出:

**程序 1:**

```
def gfgFunction():
    "Geeksforgeeks is cool website for boosting up technical skills"
    return 1

print (gfgFunction.__doc__[17:21])
```

**输出:**

```
cool

```

**解释:**
这个方法定义了一个 [docstring](https://www.python.org/dev/peps/pep-0257/) ，在函数定义开始后的第一行放一个字符串。可以使用函数的 __doc__ 属性来引用文档字符串。
因此它打印索引字符串。

**程序 2:**

```
class A(object):
    val = 1

class B(A):
    pass

class C(A):
    pass

print (A.val, B.val, C.val)
B.val = 2
print (A.val, B.val, C.val)
A.val = 3
print (A.val, B.val, C.val)
```

**输出:**

```
1 1 1
1 2 1
3 2 3

```

**解释:**
在 Python 中，类变量在内部作为字典处理。如果在当前类的字典中找不到变量名，将搜索类层次结构(即其父类)，直到找到引用的变量名，如果找不到变量，将引发错误。
因此，在上面的程序中，对 print()的第一次调用打印初始化值，即 1。
在 B. val 设置为 2 后的第二次调用中，输出为 1 2 1。
最后的输出 3 2 3 可能会让人惊讶。这里 B.val 反映的是 2 而不是 3，而不是 3，因为它之前被覆盖了。

**程序 3:**

```
check1 = ['Learn', 'Quiz', 'Practice', 'Contribute']
check2 = check1
check3 = check1[:]

check2[0] = 'Code'
check3[1] = 'Mcq'

count = 0
for c in (check1, check2, check3):
    if c[0] == 'Code':
        count += 1
    if c[1] == 'Mcq':
        count += 10

print (count)
```

**输出:**

```
12

```

**解释:**
将 check1 分配给 check2 时，我们创建了对同一列表的第二个引用。对 check2 的更改会影响 check1。当将 check1 中所有元素的切片分配给 check3 时，我们正在创建 check1 的完整副本，该副本可以独立修改(即 check3 中的任何更改都不会影响 check1)。
因此，在检查 check1 时，“代码”得到匹配，计数增加到 1，但 Mcq 没有得到匹配，因为它只在 check3 中可用。
现在检查这里的 check2 也是“代码”匹配，导致计数值为 2。
最后，在检查与 check1 和 check2 分开的 check3 时，这里只有 Mcq 匹配，计数变为 12。

**程序 4:**

```
def gfg(x,l=[]):
    for i in range(x):
        l.append(i*i)
    print(l) 

gfg(2)
gfg(3,[3,2,1])
gfg(3)
```

**输出:**

```
[0, 1]
[3, 2, 1, 0, 1, 4]
[0, 1, 0, 1, 4]

```

**解释:**
第一个函数调用应该相当明显，循环向空列表追加 0，然后追加 1，l. l 是指向存储在内存中的列表的变量的名称。第二次调用从在新的内存块中创建新的列表开始。然后我参考这个新列表。然后，它将 0、1 和 4 追加到这个新列表中。太好了。第三个函数调用很奇怪。它使用存储在原始存储块中的原始列表。这就是为什么它从 0 和 1 开始。

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。