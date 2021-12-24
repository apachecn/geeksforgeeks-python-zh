# Python 中的人性化包

> 原文:[https://www.geeksforgeeks.org/humanize-package-in-python/](https://www.geeksforgeeks.org/humanize-package-in-python/)

**人性化**是 python 中的一个包，里面包含了各种人性化的实用程序，比如把一个数字变成人类可读的大小或者吞吐量或者数字。在本文中，我们将讨论如何安装这个包，以及这个包中有哪些不同的实用程序。

**安装:**要安装这个包，我们将使用 pip a 命令。 [Python pip](https://www.geeksforgeeks.org/python-pip/) 是 Python 包的包管理器。pip 预装在 3.4 或更旧版本的 Python 上，命令提示符中使用 pip 命令。以下命令用于安装软件包:

> pip 安装人性化

**用法:**该软件包提供了各种实用程序，可用于数字上，使数字易于人类阅读。该软件包的实用程序包括:

1.  **File Size Utility:** This utility can convert large integers of file sizes to human-readable form. The default unit of the size it accepts is **bytes**. For example:

    ```
    # Program to demonstrate the
    # File Size Utility
    import humanize

    size = humanize.naturalsize(1024000)
    ```

    **输出:**

    ```
    1.0 MB

    ```

2.  **Scientific Notation:** This utility is used to add scientific notation to the program. This utility also gives an option to add precision to the number. Precision here means the number of digits needed in the number. For example:

    ```
    # Program to demonstrate the
    # scientific notation utility
    import humanize

    # Scientific notation using 
    # integer without precision
    gfg = humanize.scientific(2000)
    print('Without Precision: '+gfg)

    # Scientific notation using 
    # integer with precision
    gfg = humanize.scientific(2**10, precision = 5)
    print('With Precision: '+gfg)
    ```

    **输出:**

    ```
    Without Precision: 2.00 x 10³
    With Precision: 1.02400 x 10³

    ```

3.  **Floating Point to Fractions:** This utility is used to convert a floating-point to fractions. For example:

    ```
    # Program to demonstrate the
    # floating point to fraction 
    # utility
    import humanize

    gfg = humanize.fractional(0.5269)
    print(gfg)
    ```

    **输出:**

    ```
    333/632

    ```

4.  **Date & Time Utility:** Many a times, we encounter few scenarios where the date or time is returned in the form of numbers. This utility is used to convert the date into a human understandable format. For example:

    ```
    # Program to demonstrate the
    # date time utility
    import humanize
    import datetime as dt

    # Converting the date represented
    # as a number
    gfg = humanize.naturaldate(dt.date(2020, 5, 3))
    print(gfg)

    # Converting seconds to a 
    # better representation
    gfg = humanize.naturaldelta(dt.timedelta(seconds = 900))
    print(gfg)
    ```

    **输出:**

    ```
    May 03 2020
    15 minutes

    ```

5.  **整数实用程序:**该实用程序用于使整数值更具代表性。例如:

    ```
    # Python program to demonstrate 
    # the integer utility
    import humanize

    # Adding commas to integer values
    gfg = humanize.intcomma(14523689)
    print(gfg)

    # Converts the integer to 
    # long and short scales
    gfg = humanize.intword(1562345640)
    print(gfg)

    # Converts numbers (0-9) to their 
    # english format
    gfg = humanize.apnumber(5)
    print(gfg)
    ```

    **输出:**

    ```
    14, 523, 689
    1.6 billion
    five

    ```

**参考文献:**T2】https://pypi.org/project/humanize/