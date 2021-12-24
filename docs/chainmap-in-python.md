# Python 中的链图

> 原文:[https://www.geeksforgeeks.org/chainmap-in-python/](https://www.geeksforgeeks.org/chainmap-in-python/)

Python 包含一个名为“ **ChainMap** ”的容器，它将许多[词典](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)封装成一个单元。ChainMap 是模块“ **[”集合“](https://www.geeksforgeeks.org/python-collections-module/)** ”的成员。

**示例:**

```
# Python program to demonstrate  
# ChainMap  

from collections import ChainMap  

d1 = {'a': 1, 'b': 2} 
d2 = {'c': 3, 'd': 4} 
d3 = {'e': 5, 'f': 6} 

# Defining the chainmap  
c = ChainMap(d1, d2, d3)  

print(c)
```

**输出:**

```
ChainMap({'a': 1, 'b': 2}, {'c': 3, 'd': 4}, {'e': 5, 'f': 6})

```

**我们来看看链图上的各种操作**

## 访问操作

*   **keys() :- This function is used to display all the **keys** of all the dictionaries in ChainMap.***   ****values() :- This function is used to display **values** of all the dictionaries in ChainMap.*****   ******maps() :- This function is used to display **keys with corresponding values** of all the dictionaries in ChainMap.

    ```
    # Please select Python 3 for running this code in IDE
    # Python code to demonstrate ChainMap and
    # keys(), values() and maps

    # importing collections for ChainMap operations
    import collections

    # initializing dictionaries
    dic1 = { 'a' : 1, 'b' : 2 }
    dic2 = { 'b' : 3, 'c' : 4 }

    # initializing ChainMap
    chain = collections.ChainMap(dic1, dic2)

    # printing chainMap using maps
    print ("All the ChainMap contents are : ")
    print (chain.maps)

    # printing keys using keys()
    print ("All keys of ChainMap are : ")
    print (list(chain.keys()))

    # printing keys using keys()
    print ("All values of ChainMap are : ")
    print (list(chain.values()))
    ```

    **输出:**

    ```
    All the ChainMap contents are : 
    [{'b': 2, 'a': 1}, {'c': 4, 'b': 3}]
    All keys of ChainMap are : 
    ['a', 'c', 'b']
    All values of ChainMap are : 
    [1, 4, 2]

    ```

    **注意:**注意两个字典中都存在名为“b”的关键字，但只有第一个字典关键字作为“b”的键值。当字典按功能传递时，排序就完成了。

    ## 操作操作****** *   ******new_child() :- This function adds a new dictionary in the beginning of the ChainMap.*******   ******reversed() :- This function reverses the relative ordering of dictionaries in the ChainMap.

    ```
    # Please select Python 3 for running this code in IDE
    # Python code to demonstrate ChainMap and
    # reversed() and new_child()

    # importing collections for ChainMap operations
    import collections

    # initializing dictionaries
    dic1 = { 'a' : 1, 'b' : 2 }
    dic2 = { 'b' : 3, 'c' : 4 }
    dic3 = { 'f' : 5 }

    # initializing ChainMap
    chain = collections.ChainMap(dic1, dic2)

    # printing chainMap using map
    print ("All the ChainMap contents are : ")
    print (chain.maps)

    # using new_child() to add new dictionary
    chain1 = chain.new_child(dic3)

    # printing chainMap using map
    print ("Displaying new ChainMap : ")
    print (chain1.maps)

    # displaying value associated with b before reversing
    print ("Value associated with b before reversing is : ",end="")
    print (chain1['b'])

    # reversing the ChainMap
    chain1.maps = reversed(chain1.maps)

    # displaying value associated with b after reversing
    print ("Value associated with b after reversing is : ",end="")
    print (chain1['b'])
    ```

    **输出:**

    ```
    All the ChainMap contents are : 
    [{'b': 2, 'a': 1}, {'b': 3, 'c': 4}]
    Displaying new ChainMap : 
    [{'f': 5}, {'b': 2, 'a': 1}, {'b': 3, 'c': 4}]
    Value associated with b before reversing is : 2
    Value associated with b after reversing is : 3

    ```

    本文由 **[【曼吉特·辛格】](https://auth.geeksforgeeks.org/profile.php?user=manjeet_04&list=practice)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。******