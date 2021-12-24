# Python 中清除列表的不同方式

> 原文:[https://www . geesforgeks . org/不同方式清除 python 列表/](https://www.geeksforgeeks.org/different-ways-to-clear-a-list-in-python/)

有许多方法可以通过 Python 语言提供的不同构造的方法来清除列表。让我们试着逐一理解每种方法。

*   **Method #1 :** Using `clear()` method

    ```
    # Python program to clear a list
    # using clear() method 

    # Creating list
    GEEK = [6, 0, 4, 1]
    print('GEEK before clear:', GEEK) 

    # Clearing list 
    GEEK.clear() 
    print('GEEK after clear:', GEEK) 
    ```

    **输出:**

    ```
    GEEK before clear: [6, 0, 4, 1]
    GEEK after clear: []

    ```

*   **Method #2 :** Reinitializing the list : The initialization of the list in that scope, initializes the list with no value. i.e list of size 0\. Let’s see the example demonstrating Method 1 and 2 to clear list

    ```
    # Python3 code to demonstrate 
    # clearing a list using
    # clear and Reinitializing 

    # Initializing lists
    list1 = [1, 2, 3]
    list2 = [5, 6, 7]

    # Printing list1 before deleting 
    print ("List1 before deleting is : " 
    +  str(list1))

    # deleting list using clear()
    list1.clear()

    # Printing list1 after clearing
    print ("List1 after clearing using clear() : " 
    + str(list1))

    # Printing list2 before deleting 
    print ("List2 before deleting is : "
     +  str(list2))

    # deleting list using reinitialization
    list2 = []

    # Printing list2 after reinitialization
    print ("List2 after clearing using reinitialization : " 
    + str(list2))
    ```

    **输出:**

    ```
    List1 before deleting is : [1, 2, 3]
    List1 after clearing using clear() : []
    List2 before deleting is : [5, 6, 7]
    List2 after clearing using reinitialization : []

    ```

*   **Method #3 :** Using **“*= 0”** : This is a lesser known method, but this method removes all elements of the list and makes it empty.

    ```
    # Python3 code to demonstrate 
    # clearing a list using
    # *= 0 method

    # Initializing lists
    list1 = [1, 2, 3]

    # Printing list1 before deleting 
    print ("List1 before deleting is : " + str(list1))

    # deleting list using *= 0
    list1 *= 0

    # Printing list1 after *= 0
    print ("List1 after clearing using *= 0: " + str(list1))
    ```

    **输出:**

    ```
    List1 before deleting is : [1, 2, 3]
    List1 after clearing using *= 0: []
    ```

*   **Method #4 :** Using **[del](https://www.geeksforgeeks.org/list-methods-in-python-set-2-del-remove-sort-insert-pop-extend/)** : **del** can be used to clear the list elements in a range, if we don’t give a range, all the elements are deleted.

    ```
    # Python3 code to demonstrate 
    # clearing a list using
    # del method

    # Initializing lists
    list1 = [1, 2, 3]
    list2 = [5, 6, 7]

    # Printing list1 before deleting 
    print ("List1 before deleting is : " + str(list1))

    # deleting list1 using del
    del list1[:]
    print ("List1 after clearing using del : " + str(list1))

    # Printing list2 before deleting 
    print ("List2 before deleting is : " + str(list2))

    # deleting list using del
    del list2[:]
    print ("List2 after clearing using del : " + str(list2))
    ```

    **输出:**

    ```
    List1 before deleting is : [1, 2, 3]
    List1 after clearing using del : []
    List2 before deleting is : [5, 6, 7]
    List2 after clearing using del : []

    ```