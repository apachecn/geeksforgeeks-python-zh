# 巨蟒惊人的黑客攻击

> 原文:[https://www.geeksforgeeks.org/amazing-hacks-python/](https://www.geeksforgeeks.org/amazing-hacks-python/)

Python 确实是最聪明、最流行的语言之一。这里有一些很酷的黑客攻击，使得 python 在所有其他语言中非常优秀。

1.  **列表理解:**列表理解是摆脱编写不必要的代码行的最好和有效的技术。[阅读文章](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)了解更多。
2.  **Printing a list:** List are not printed according the user requirement. They are always printed in unwanted square brackets and single quotes. But there is trivial solution to print the list efficiently by using the string’s join method.
    *The join method turns the list into a string by casting each item into a string and connecting them with the string that join was called on*.

    ```
    # Declaring the list geek
    geek = ['Geeks', 'Programming', 'Algorithm', 'Article']

    # Directly printing the list
    print ("Simple List:", geek)

    # Printing the list by join method
    print ('List by using join method: %s' % ', ' .join(geek))

    # Direct use of join method
    print ('Direct apply the join method:',(", " .join(geek)))
    ```

    ```
    Output: 
    Simple List: ['Geeks', 'Programming', 'Algorithm', 'Article']
    List by using join method: Geeks, Programming, Algorithm, Article
    Direct apply the join method: Geeks, Programming, Algorithm, Article

    ```

    **炫酷的拉链招数**

3.  **转置一个矩阵:**你可以[读到这里](https://www.geeksforgeeks.org/transpose-matrix-single-line-python/)关于这个。
4.  **Partition a list into N groups:** We used iter() as an iterator over a sequence.

    ```

    # Declaring the list geek
    geek = ['Sun', 'Flowers', 'Peoples', 'Animals', 'Day', 'Night']

    partition = list(zip (*[iter(geek)] * 2))
    print (partition)
    ```

    ```
    Output: 
    [('Sun', 'Flowers'), ('Peoples', 'Animals'), ('Day', 'Night')]

    ```

    **解释** : [iter(geek)] * 2 产生一个包含 geek[]列表 2 项的列表，即长度为 2 的列表。*arg 将序列解包为函数调用的参数。因此，我们将同一个迭代器传递给 zip()两次。

5.  **同时打印多个列表的项目**

    ```
    list1 = [1, 3, 5, 7]
    list2 = [2, 4, 6, 8]

    # Here zip() function takes two equal length list and merges them
    # together in pairs
    for a, b in zip(list1,list2):
        print (a, b)
    ```

    ```
    Output: 
    1 2
    3 4
    5 6
    7 8

    ```

6.  **以字符串为输入，转换为列表:**

    ```
    # Reads a string from input and type case them to int 
    # after splitting to white-spaces

    formatted_list = list(map(int, input().split()))
    print(formatted_list)
    ```

    ```
    Input:
    2 4 5 6
    Output:
    [2, 4, 5, 6] 

    ```

7.  **将列表列表转换为单个列表**

    ```
    # import the itertools 
    import itertools 

    # Declaring the list geek 
    geek = [[1, 2], [3, 4], [5, 6]] 

    # chain.from_iterable() function returns the
    # elements of nested list 
    # and iterate from first list 
    # of iterable till the last 
    # end of the list 

    lst = list(itertools.chain.from_iterable(geek)) 
    print(lst)
    ```

    ```
    Output: 
    [1, 2, 3, 4, 5, 6]

    ```

8.  **打印重复字符:**任务是打印这样的图案 Geeeeekkkkss。因此，我们可以轻松打印此图案，而无需使用 for loop。

    ```
    # + used for string concatenation
    # To repeat the character n times, just multiply n 
    # with that character  
    print ("G" + "e"*5 + "k"*4 + "s"*2)
    ```

    ```
    Output:
    Geeeeekkkkss

    ```

**阅读更多:** [关于蟒蛇的 10 个有趣事实](https://www.geeksforgeeks.org/py-facts-10-interesting-facts-about-python/)
T5【参考:[https://www.quora.com/What-are-some-cool-Python-tricks](https://www.quora.com/What-are-some-cool-Python-tricks)

本文由 [Shubham Bansal](https://www.facebook.com/banalshubham) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。