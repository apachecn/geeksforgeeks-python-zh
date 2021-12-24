# Python 中的堆队列(或 heapq)

> 原文:[https://www . geesforgeks . org/heap-queue-or-heap q-in-python/](https://www.geeksforgeeks.org/heap-queue-or-heapq-in-python/)

[堆数据结构主要用来表示一个优先级队列](https://www.geeksforgeeks.org/applications-of-heap-data-structure/)。在 Python 中，它可以使用“ **heapq** ”模块获得。Python 中这种数据结构的属性是每次弹出**最小的堆元素(最小堆)**。每当元素被推送或弹出时，**堆结构保持在**中。堆[0]元素每次也返回最小的元素。

**我们来看看堆上的各种操作:**

*   **heapify(iterable) :- This function is used to **convert the iterable into a heap** data structure. i.e. in heap order.***   ****heappush(heap, ele) :- This function is used to **insert the element** mentioned in its arguments into heap. The **order is adjusted**, so as **heap structure is maintained**.*****   ******heappop(heap) :- This function is used to **remove and return the smallest element** from heap. The **order is adjusted**, so as **heap structure is maintained**.

    ```py
    # Python code to demonstrate working of 
    # heapify(), heappush() and heappop()

    # importing "heapq" to implement heap queue
    import heapq

    # initializing list
    li = [5, 7, 9, 1, 3]

    # using heapify to convert list into heap
    heapq.heapify(li)

    # printing created heap
    print ("The created heap is : ",end="")
    print (list(li))

    # using heappush() to push elements into heap
    # pushes 4
    heapq.heappush(li,4)

    # printing modified heap
    print ("The modified heap after push is : ",end="")
    print (list(li))

    # using heappop() to pop smallest element
    print ("The popped and smallest element is : ",end="")
    print (heapq.heappop(li))
    ```

    **输出:**

    ```py
    The created heap is : [1, 3, 9, 7, 5]
    The modified heap after push is : [1, 3, 4, 7, 5, 9]
    The popped and smallest element is : 1

    ```****** *   ******heappushpop(heap, ele) :- This function **combines the functioning of both push and pop operations** in one statement, increasing efficiency. Heap order is maintained after this operation.*******   ******heapreplace(heap, ele) :- This function also inserts and pops element in one statement, but it is different from above function. In this, **element is first popped, then the element is pushed.i.e, the value larger than the pushed value can be returned.** `heapreplace()` returns the smallest value originally in heap regardless of the pushed element as opposed to `heappushpop()`.

    ```py
    # Python code to demonstrate working of 
    # heappushpop() and heapreplce()

    # importing "heapq" to implement heap queue
    import heapq

    # initializing list 1
    li1 = [5, 7, 9, 4, 3]

    # initializing list 2
    li2 = [5, 7, 9, 4, 3]

    # using heapify() to convert list into heap
    heapq.heapify(li1)
    heapq.heapify(li2)

    # using heappushpop() to push and pop items simultaneously
    # pops 2
    print ("The popped item using heappushpop() is : ",end="")
    print (heapq.heappushpop(li1, 2))

    # using heapreplace() to push and pop items simultaneously
    # pops 3
    print ("The popped item using heapreplace() is : ",end="")
    print (heapq.heapreplace(li2, 2))
    ```

    **输出:**

    ```py
    The popped item using heappushpop() is : 2
    The popped item using heapreplace() is : 3

    ```****** *   ******nlargest(k, iterable, key = fun) :- This function is used to **return the k largest elements from the iterable specified and satisfying the key if mentioned.*********   ******nsmallest(k, iterable, key = fun) :- This function is used to **return the k smallest elements from the iterable specified and satisfying the key if mentioned.**

    ```py
    # Python code to demonstrate working of 
    # nlargest() and nsmallest()

    # importing "heapq" to implement heap queue
    import heapq

    # initializing list 
    li1 = [6, 7, 9, 4, 3, 5, 8, 10, 1]

    # using heapify() to convert list into heap
    heapq.heapify(li1)

    # using nlargest to print 3 largest numbers
    # prints 10, 9 and 8
    print("The 3 largest numbers in list are : ",end="")
    print(heapq.nlargest(3, li1))

    # using nsmallest to print 3 smallest numbers
    # prints 1, 3 and 4
    print("The 3 smallest numbers in list are : ",end="")
    print(heapq.nsmallest(3, li1))
    ```

    **输出:**

    ```py
    The 3 largest numbers in list are : [10, 9, 8]
    The 3 smallest numbers in list are : [1, 3, 4]

    ```

    本文由供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。******