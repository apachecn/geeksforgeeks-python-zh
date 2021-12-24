# Python–检查列表是否为空

> 原文:[https://www . geesforgeks . org/python-check-if-list-空-not/](https://www.geeksforgeeks.org/python-check-if-list-empty-not/)

在本文中，我们将学习如何检查给定的列表是否为空。在 Python 中有各种方法可以检查列表，但是所有这些方法都不合适，或者用 Python 的术语“Python 化”来实现。

1.  Let’s see how we can check a list is empty or not, in a less pythonic way. We should avoid this way of **explicitly checking for a sequence or list**

    ```py
    # Python code to check for empty list
    # Explicit way
    def Enquiry(lis1):
        if len(lis1) == 0:
            return 0
        else:
            return 1

    # Driver Code
    lis1 = []
    if Enquiry(lis1):
        print ("The list is not empty")
    else:
        print("Empty List")
    ```

    **输出:**

    ```py
    Empty List

    ```

2.  Now let’s see a more pythonic way to check for an empty list. This method of check is an **implicit way of checking and more preferable than the previous one.**

    ```py
    # Python code to check for empty list
    # IMPLICIT way or Pythonic way
    def Enquiry(lis1):
        if not lis1:
            return 1
        else:
            return 0

    # Driver Code
    lis1 = []
    if Enquiry(lis1):
        print ("The list is Empty")
    else:
        print ("The list is not empty")
    ```

    **输出:**

    ```py
    The list is Empty
    ```

**音程**

1.  The previous methods that we used in normal **Python don’t work for the Numpythonic way**. Other methods that work fine for lists or other standard containers **fail for numpy arrays**. This way fails with numpy arrays because numpy tries to cast the array to an array of bools and if this tries to evaluate all of those bools at once for some kind of aggregate truth value, it fails so we get a ValueError.

    ```py
    # Numpythonic way with the previous method
    # Returns ValueError
    import numpy
    def Enquiry(lis1):
        return(numpy.array(lis1))

    # Driver Code
    lis1 = [0, 1]
    if Enquiry(lis1):
        print("Not Empty")
    else:
        print("Empty")
    ```

    **输出:**

    ```py
    None
    ```

    错误:

    ```py
    Traceback (most recent call last):
      File "/home/2d237324bb5211d7216c521441a750e9.py", line 7, in 
        if Enquiry(lis1):
    ValueError: The truth value of an array with more than 
    one element is ambiguous. Use a.any() or a.all()
    ```

2.  In the next example, we will see that even if the list is Not Empty, the output will show Empty. If the list contains one 0, then the if statement will incorrectly result.

    ```py
    # Numpythonic way with the previous method
    # Returns wrong result
    import numpy
    def Enquiry(lis1):
        return(numpy.array(lis1))

    # Driver Code
    lis1 = [0, ]
    if Enquiry(lis1):
        print("Not Empty")
    else:
        print("Empty")
    ```

    **输出:**

    ```py
    Empty
    ```

    **让节奏运转起来**

    1.  If we have a numpy array then correct method in all cases, is to use if *.size*. This size checks the size of the arrays and return True or False accordingly.
        Example:

        ```py
        # Numpythonic way to check emptiness
        # Use of size
        import numpy
        def Enquiry(lis1):
            return(numpy.array(lis1))

        # Driver Code
        lis1 = []
        if Enquiry(lis1).size:
            print("Not Empty")
        else:
            print("Empty")
        ```

        **输出:**

        ```py
        Empty
        ```

    2.  This example shows the other case with a single 0 element, which failed in the previous cases.

        ```py
        # Numpythonic way to check emptiness
        # Use of size
        import numpy
        def Enquiry(lis1):
            return(numpy.array(lis1))

        # Driver Code
        lis1 = [0, ]
        if Enquiry(lis1).size:
            print("Not Empty")
        else:
            print("Empty")
        ```

        **输出:**

        ```py
        Not Empty
        ```

更多参考请访问 [PEP8 风格指南](https://www.python.org/dev/peps/pep-0008/)。