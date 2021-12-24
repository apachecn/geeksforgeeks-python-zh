# 在没有库的 Python 中查找平均值、中值、模式

> 原文:[https://www . geesforgeks . org/find-mean-middle-mode-in-python-不带库/](https://www.geeksforgeeks.org/finding-mean-median-mode-in-python-without-libraries/)

在本文中，我们将学习如何在不使用外部库的情况下，使用 Python 计算**平均值、中值和模式。**

1.  **Mean :** The mean is the average of all numbers and is sometimes called the [arithmetic mean](https://www.geeksforgeeks.org/find-n-arithmetic-means-b/). This code calculates Mean or Average of a list containing numbers:

    ```
    # Python program to print
    # mean of elements

    # list of elements to calculate mean
    n_num = [1, 2, 3, 4, 5]
    n = len(n_num)

    get_sum = sum(n_num)
    mean = get_sum / n

    print("Mean / Average is: " + str(mean))
    ```

    **Output:**

    ```
    Mean / Average is: 3.0

    ```

    我们定义一个数字列表，并计算列表的长度。然后，我们使用 sum()函数获取列表中所有元素的总和。我们最终将总和除以列表中的元素数量，并打印结果以获得列表的平均值。

2.  **中位数:**中位数是一组数字中的中间数。此代码计算包含数字的列表的中位数:

    ```
    # Python program to print
    # median of elements

    # list of elements to calculate median
    n_num = [1, 2, 3, 4, 5]
    n = len(n_num)
    n_num.sort()

    if n % 2 == 0:
        median1 = n_num[n//2]
        median2 = n_num[n//2 - 1]
        median = (median1 + median2)/2
    else:
        median = n_num[n//2]
    print("Median is: " + str(median))
    ```

    **输出:**

```
Median is: 3

```