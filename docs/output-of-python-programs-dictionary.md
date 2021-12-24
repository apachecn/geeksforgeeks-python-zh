# Python 程序输出|(字典)

> 原文:[https://www . geesforgeks . org/python 程序输出-字典/](https://www.geeksforgeeks.org/output-of-python-programs-dictionary/)

**先决条件:** [字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)
T5】注:所有这些程序的输出都在 Python3
**1 上测试。以下代码的输出是什么？**

```
a = {i: i * i for i in range(6)}
print (a)
```

选项:
a)字典理解不存在
b) {0: 0，1: 1，2: 4，3: 9，4: 16，5: 25，6:36}
c) {0: 0，1: 1，4: 4，9: 9，16: 16，25: 25}
d) {0: 0，1: 1，2: 4，3: 9，4: 16，5: 25}

```
Ans. (d)
```

**解释:**上面这段用花括号写的代码生成了整个字典。
T3】2。以下代码的输出是什么？

```
a ={}
a.fromkeys(['a', 'b', 'c', 'd'], 98)
print (a)
```

选项:
a)语法错误
b) {'a':98、' b':98、' c':98、' d':98}
c) {}
d) {'a ':无、' b ':无、' c ':无。' d ':无}

```
Ans. (c)

```

**解释:** **fromkeys()** 用列表中给它的键作为参数创建一个新字典，并设置该键的值，其中给定的默认值作为参数。
输入:

```
a ={}
dict = a.fromkeys(['a', 'b', 'c', 'd'], 98)
print (a)
print (dict)
```

输出:

```
{}
{'d': 98, 'b': 98, 'a': 98, 'c': 98}

```

**3。以下代码的输出是什么？**

```
dict ={}
print (all(dict))
```

选项:
a) { }
b)假
c)真
d)抛出异常

```
Ans.(c)

```

**解释:**all()方法返回:

*   True–如果可迭代表中的所有元素都为 true，则可迭代表为空。*   False – If any element in an iterable is false.

    输入:

    ```
    a = {}
    b = a.fromkeys([1, False, 3], 'True')
    print (all(a))
    print (all(b))
    ```

    输出:

    ```
    True
    False

    ```

    **4。以下代码的输出是什么？**

    ```
    a = {'geeks' : 1, 'gfg' : 2}
    b = {'geeks' : 2, 'gfg' : 1}
    print (a == b) 
    ```

    a)真
    b)假
    c)错误
    d)无

    ```
    Ans. (b)

    ```

    **说明:**如果两个字典相同则返回真，否则返回假。

    **5。关于字典，以下哪一项是错误的？**
    a)可以使用键
    访问字典的值 b)可以使用值
    访问字典的键 c)字典可以排序也可以不排序
    d)以上都不是

    ```
    Ans.(b)

    ```

    **说明:**字典的值可以用键访问，但字典的键不能用值访问。