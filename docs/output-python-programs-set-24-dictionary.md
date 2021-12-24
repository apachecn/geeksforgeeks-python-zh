# Python 程序输出|第 24 集(字典)

> 原文:[https://www . geesforgeks . org/output-python-programs-set-24-dictionary/](https://www.geeksforgeeks.org/output-python-programs-set-24-dictionary/)

先决条件:[Python-字典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)

**1。会有什么产出？**

```py
dictionary = {"geek":10, "for":45, "geeks": 90}
print("geek" in dictionary)
```

选项:

1.  Ten
2.  错误的
3.  真实的
4.  错误

```py
Output:
3\. True
```

**说明: 中的** ***是用来检查字典中是否存在关键字。***

**2。会有什么产出？**

```py
dictionary ={1:"geek", 2:"for", 3:"geeks"}
del dictionary
```

选项:

1.  Del delete the entire dictionary
2.  Del does not exist for the dictionary.
3.  Del delete the key in the dictionary
4.  Del delete the value in the dictionary

```py
Output:
1\. del deletes the entire dictionary
```

**解释:** ***del*** 删除整个字典，任何进一步访问它的尝试都会抛出一个错误。

**3。会有什么产出？**

```py
a = {}
a[1] = 1
a['1'] = 2
a[1]= a[1]+1
count = 0
for i in a:
    count += a[i]
print(count)
```

选项:

1.  four
2.  Two
3.  one
4.  mistake

```py
Output:
1\. 4
```

**说明:**上面这段代码基本找到了键值的总和。

**4。会有什么产出？**

```py
test = {1:'A', 2:'B', 3:'C'}
del test[1]
test[1] = 'D'
del test[2]
print(len(test))
```

选项:

1.  Two
2.  one
3.  Zero
4.  mistake

```py
Output:
1\. 2
```

**说明:**删除 1 的键值对:“A”后，增加 1 的键值对:“D”。

**5。会有什么产出？**

```py
a ={}
a['a']= 1
a['b']=[2, 3, 4]
print(a)
```

选项:

1.  {'b': [2]，' a': 1}
2.  {“a”:1，“b”:[2，3，4]}
3.  {'b': [2]，' a': [3]}
4.  mistake

```py
Output:
2\. {'a': 1, 'b': [2, 3, 4]}
```

**说明:**可变成员可以作为字典的值，但不能作为字典的键。