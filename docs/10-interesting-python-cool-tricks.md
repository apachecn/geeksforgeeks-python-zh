# 10 个有趣的蟒蛇酷招

> 原文:[https://www . geesforgeks . org/10-有趣-python-酷-技巧/](https://www.geeksforgeeks.org/10-interesting-python-cool-tricks/)

在 python 中，我们可以返回多个值-

1.  A very unique feature of Python is that it returns multiple values at a time.

    ```py
    def GFG():
        g = 1 
        f = 2
        return g, f 

    x, y = GFG()
    print(x, y)
    ```

    **Output:**

    ```py
    (1, 2)

    ```

2.  Allow negative indexing: Python allows negative indexing of its sequence. Index -1 refers to the last element, -2 seconds refers to the last element and so on.

    ```py
    my_list = ['geeks', 'practice', 'contribute']
    print(my_list[-1])
    ```

    **Output:**

```py
contribute

```