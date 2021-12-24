# Python 中字典的 Get()方法

> 原文:[https://www . geesforgeks . org/get-method-dictionary-python/](https://www.geeksforgeeks.org/get-method-dictionaries-python/)

**Python get()方法**返回给定键的值(如果字典中有)。如果不是，那么它将返回 None(如果 get()仅与一个参数一起使用)。

> **语法:** Dict.get(键，默认值=无)
> 
> **参数:**
> 
> *   **键:**要从中返回值的项目的键名
> *   **值:**(可选)如果找不到密钥，将返回的值。默认值为“无”。
> 
> **返回:**用指定的键返回项目的值。

## Python 字典 get()方法示例

### 示例 1: Python get()方法适用于字典

## 计算机编程语言

```
dic = {"A": 1, "B": 2}
print(dic.get("A"))
print(dic.get("C"))
print(dic.get("C", "Not Found ! "))
```

**输出:**

```
1
None
Not Found !
```

### 示例 2: Python 字典 get()方法嵌套

get()在没有值的情况下进行检查和赋值，以完成此特定任务。如果没有任何键，只返回无错误。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Safe access nested dictionary key
# Using nested get()

# initializing dictionary
test_dict = {'Gfg' : {'is' : 'best'}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using nested get()
# Safe access nested dictionary key
res = test_dict.get('Gfg', {}).get('is')

# printing result
print("The nested safely accessed value is :  " + str(res))
```

**输出:**

```
The original dictionary is : {'Gfg': {'is': 'best'}}
The nested safely accessed value is :  best
```

本文由 **Mayank Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。