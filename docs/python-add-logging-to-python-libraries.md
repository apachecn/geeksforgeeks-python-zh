# Python |将日志记录添加到 Python 库中

> 原文:[https://www . geesforgeks . org/python-add-logging-to-python-libraries/](https://www.geeksforgeeks.org/python-add-logging-to-python-libraries/)

在本文中，我们将学习如何向库中添加日志记录功能，但不希望它干扰不使用日志记录的程序。

对于想要执行日志记录的库，创建一个专用的日志记录对象，并按照下面的代码进行初始配置–

**代码#1 :**

```py
# abc.py
import logging

log = logging.getLogger(__name__)
log.addHandler(logging.NullHandler())

# Example function (for testing)
def func():
    log.critical('A Critical Error !')
    log.debug('A debug message')
```

使用此配置，默认情况下不会发生日志记录。

```py
import somelib
abc.func()
```

**输出:**

```py
NO OUTPUT
```

如果配置了日志系统，日志消息将开始出现。

**代码#2:**

```py
import logging

logging.basicConfig()
somelib.func()
```

**输出:**

```py
CRITICAL:somelib:A Critical Error!
```

**它是如何工作的？**

*   This brings a special problem to library logging, because the information about the environment in which they are used is unknown.
*   Generally speaking, don't write library code that attempts to configure the logging system by itself or assumes the existing logging configuration.
*   Therefore, one needs to be very careful to provide isolation.
*   The call to `getLogger(__name__)` creates a recorder module with the same name as the calling module.
*   Because all modules are unique, this creates a dedicated recorder, which is probably separate from other recorders.
*   `log.addHandler(logging.NullHandler())` The operation attaches an empty handler to the recorder object just created. By default, the null handler ignores all log messages.
*   Therefore, if the library is used and logging has never been configured, no messages or warnings will appear.

各个库的日志记录可以独立配置，而不考虑其他日志记录设置，如下面给出的代码所示–

**代码#3:**

```py
import logging

logging.basicConfig(level = logging.ERROR)

import abc
print (abc.func())

Change the logging level for 'abc' only
logging.getLogger('abc').level = logging.DEBUG
print (abc.func())
```

**输出:**

```py
CRITICAL:abc:A Critical Error!
DEBUG:abc:A debug message
```