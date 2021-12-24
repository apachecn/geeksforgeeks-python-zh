# 使用 Python 获取当前日期

> 原文:[https://www . geesforgeks . org/get-current-date-use-python/](https://www.geeksforgeeks.org/get-current-date-using-python/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

在 Python 中，日期和时间本身不是一种数据类型，但是可以导入一个名为`datetime`的模块来处理日期和时间。Datetime 模块内置于 Python 中，无需外部安装。

`datetime`模块提供了一些获取当前日期和时间的功能。让我们看看他们。

*   **date.today():** `today()` method of `date` class under `datetime` module returns a date object which contains the value of Today’s date.

    > **语法:** date.today()
    > 
    > **返回:**返回当前本地日期。

    **示例:**

    ```py
    # Python program to get
    # current date

    # Import date class from datetime module
    from datetime import date

    # Returns the current local date
    today = date.today()
    print("Today date is: ", today)
    ```

    **输出:**

    ```py
    Today date is:  2019-12-11

    ```

*   **[datetime.now():](https://www.geeksforgeeks.org/python-now-function/)** Python library defines a function that can be primarily used to get current time and date. `now()` function Return the current local date and time, which is defined under `datetime` module.

    > **语法:** datetime.now(tz)
    > 
    > **参数:**
    > **tz :** 需要当前时间和日期的指定时区。(默认使用格林威治子午线时间。)
    > 
    > **返回:**以时间格式返回当前日期和时间。

    **示例:**

    ```py
    # Python program to get
    # current date

    # Import datetime class from datetime module
    from datetime import datetime

    # returns current date and time
    now = datetime.now()
    print("now = ", now)
    ```

    **输出:**

    ```py
    now =  2019-12-11 10:58:37.039404

    ```

    **now()的属性:**
    now()有不同的属性，与年、月、日、时、分、秒等时间属性相同。

    **例 3:** 演示 now()的属性。

    ```py
    # Python3 code to demonstrate 
    # attributes of now() 

    # importing datetime module for now() 
    import datetime 

    # using now() to get current time 
    current_time = datetime.datetime.now() 

    # Printing attributes of now(). 
    print ("The attributes of now() are : ") 

    print ("Year : ", end = "") 
    print (current_time.year) 

    print ("Month : ", end = "") 
    print (current_time.month) 

    print ("Day : ", end = "") 
    print (current_time.day) 
    ```

    **输出:**

    ```py
    The attributes of now() are : 
    Year : 2019
    Month : 12
    Day : 11

    ```