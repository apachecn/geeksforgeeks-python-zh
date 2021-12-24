# 在 Python 中列出方法

> 原文:[https://www.geeksforgeeks.org/list-methods-python/](https://www.geeksforgeeks.org/list-methods-python/)

本文是以下文章的延伸:
[Python List](https://www.geeksforgeeks.org/python-list/)
[Python 中的 List Methods | Set 1(in，not in，len()，min()，max()…)](https://www.geeksforgeeks.org/list-methods-in-python-set-1-in-not-in-len-min-max/)
[Python 中的 List Methods | Set 2(del，remove()，sort()，insert()，pop()，extend()…)](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/)

**添加和追加**

*   **追加():**用于向列表追加和添加元素。用于将元素添加到列表的最后一个位置。
    **语法:**

```py
 list.append (element)
```

```py
# Adds List Element as value of List.
List = ['Mathematics', 'chemistry', 1997, 2000]
List.append(20544)
print(List)
```

输出:

```py
['Mathematics', 'chemistry', 1997, 2000, 20544]

```

*   **insert():** Inserts an elements at specified position.
    **Syntax:**

    ```py
     list.insert(<position, element)
    ```

    注意:所提到的位置应该在列表的范围内，因为在这种情况下在 0 和 4 之间，否则将抛出 IndexError。

    ```py
    List = ['Mathematics', 'chemistry', 1997, 2000]
    # Insert at index 2 value 10087
    List.insert(2,10087)     
    print(List)        
    ```

    输出:

    ```py
    ['Mathematics', 'chemistry', 10087, 1997, 2000, 20544]

    ```

    *   **extend():** Adds contents to List2 to the end of List1.
    **Syntax:**

    ```py
    List1.extend(List2)
    ```

    ```py
    List1 = [1, 2, 3]
    List2 = [2, 3, 4, 5]

    # Add List2 to List1
    List1.extend(List2)        
    print(List1)

    # Add List1 to List2 now
    List2.extend(List1) 
    print(List2)
    ```

    输出:

    ```py
    [1, 2, 3, 2, 3, 4, 5]
    [2, 3, 4, 5, 1, 2, 3, 2, 3, 4, 5]
    ```

    **列表**的 sum()、count()、index()、min()和 max()函数

    *   **sum() :** 计算列表所有元素的总和。
        **语法:**

    ```py
     sum(List)
    ```

    ```py
    List = [1, 2, 3, 4, 5]
    print(sum(List))
    ```

    输出:

    ```py
    15

    ```

    **如果数值不作为参数使用会发生什么？**
    总和只针对数值计算，否则将引发类型错误。
    见例:

    ```py
    List = ['gfg', 'abc', 3]
    print(sum(List))
    ```

    输出:

    ```py
    Traceback (most recent call last):
      File "", line 1, in 
        sum(List)
    TypeError: unsupported operand type(s) for +: 'int' and 'str'

    ```

    *   **count():**Calculates total occurrence of given element of List.
    **Syntax:**

    ```py
    List.count(element)
    ```

    ```py
    List = [1, 2, 3, 1, 2, 1, 2, 3, 2, 1]
    print(List.count(1))
    ```

    输出:

    ```py
    4

    ```

    *   **length:**Calculates total length of List.
    **Syntax:**

    ```py
    len(list_name)
    ```

    ```py
    List = [1, 2, 3, 1, 2, 1, 2, 3, 2, 1]
    print(len(List))
    ```

    输出:

    ```py
    10

    ```

    *   **index():** Returns the index of first occurrence. Start and End index are not necessary parameters.
    **Syntax:**

    ```py
    List.index(element[,start[,end]])
    ```

    ```py
    List = [1, 2, 3, 1, 2, 1, 2, 3, 2, 1]
    print(List.index(2))
    ```

    输出:

    ```py
    1

    ```

    另一个例子:

    ```py
    List = [1, 2, 3, 1, 2, 1, 2, 3, 2, 1]
    print(List.index(2,2))
    ```

    输出:

    ```py
    4

    ```

    ```py
    List = [1, 2, 3, 1, 2, 1, 2, 3, 2, 1]

    """index(element, start, end) : It will calculate till index end-1\. """

    # will check from index 2 to 4.
    print("After checking in index range 2 to 4")
    print(List.index(2,2,5))

    # will check from index 2 to 3.
    print("After checking in index range 2 to 3")
    print(List.index(2,2,4))

    ```

    输出:

    ```py
    After checking in index range 2 to 4
    4
    After checking in index range 2 to 3
    Traceback (most recent call last):
      File "", line 1, in 
        List.index(2,2,4)
    ValueError: tuple.index(x): x not in tuple

    ```

    *   **min() : **Calculates minimum of all the elements of List.
    **Syntax:**

    ```py
    min(List)
    ```

    ```py
    List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
    print(min(List))
    ```

    输出:

    ```py
    1.054

    ```

    *   **max():** Calculates maximum of all the elements of List.
    **Syntax:**

    ```py
    max(List)
    ```

    ```py
    List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
    print(max(List))
    ```

    输出:

    ```py
    5.33

    ```

    **排序()和反转()功能**

    *   **reverse(): **Sort the given data structure (both tuple and list) in ascending order. Key and reverse_flag are not necessary parameter and reverse_flag is set to False, if nothing is passed through sorted().
        **Syntax:**

        ```py
        sorted([list[,key[,Reverse_Flag]]])
         list.sort([key,[Reverse_flag]])
        ```

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]

        #Reverse flag is set True
        List.sort(reverse=True) 

        #List.sort().reverse(), reverses the sorted list  
        print(List)        
        ```

        输出:

        ```py
        [5.33, 4.445, 3, 2.5, 2.3, 1.054]

        ```

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
        sorted(List)
        print(List)
        ```

        输出:

        ```py
        [1.054, 2.3, 2.5, 3, 4.445, 5.33]

        ```

    **删除列表元素**

    要删除一个或多个元素，即删除一个元素，可以使用许多内置函数，如 pop() & remove()和 del 等关键字。

    *   **pop():** Index is not a necessary parameter, if not mentioned takes the last index.
        **Syntax:**

        ```py
         list.pop([index])
        ```

        注意:索引必须在列表的范围内，否则会出现索引错误。

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
        print(List.pop())
        ```

        输出:

        ```py
        2.5

        ```

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
        print(List.pop(0))
        ```

        输出:

        ```py
        2.3

        ```

    *   **del() : **Element to be deleted is mentioned using list name and index.
        **Syntax:**

        ```py
        del list.[index]
        ```

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
        del List[0]
        print(List)
        ```

        输出:

        ```py
        [4.445, 3, 5.33, 1.054, 2.5]
        ```

    *   **remove(): **Element to be deleted is mentioned using list name and element.
        **Syntax:**

        ```py
         list.remove(element)
        ```

        ```py
        List = [2.3, 4.445, 3, 5.33, 1.054, 2.5]
        List.remove(3)
        print(List)
        ```

        输出:

        ```py
        [2.3, 4.445, 5.33, 1.054, 2.5]

        ```

本文由 **Piyush Doorwar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。