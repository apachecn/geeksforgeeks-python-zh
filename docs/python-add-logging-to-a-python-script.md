# Python |将日志记录添加到 Python 脚本中

> 原文:[https://www . geesforgeks . org/python-add-logging-to-a-python-script/](https://www.geeksforgeeks.org/python-add-logging-to-a-python-script/)

在本文中，我们将学习如何让脚本和简单程序将诊断信息写入日志文件。

**代码#1:使用日志模块将日志添加到一个简单的程序中**

```py
import logging

def main():
    # Configure the logging system
    logging.basicConfig(filename ='app.log',
                        level = logging.ERROR)

    # Variables (to make the calls that follow work)
    hostname = 'www.python.org'
    item = 'spam'
    filename = 'data.csv'
    mode = 'r'

    # Example logging calls (insert into your program)
    logging.critical('Host %s unknown', hostname)
    logging.error("Couldn't find %r", item)
    logging.warning('Feature is deprecated')
    logging.info('Opening file %r, mode = %r', filename, mode)
    logging.debug('Got here')

if __name__ == '__main__':
main()
```

*   五个日志记录调用( **critical()、error()、warning()、info()、debug()** )按降序表示不同的严重级别。
*   **basicConfig()** 的级别参数是一个过滤器。低于此设置的所有邮件都将被忽略。
*   每个日志记录操作的参数是一个消息字符串，后跟零个或多个参数。生成最终日志消息时，使用%运算符使用提供的参数格式化消息字符串。

如果运行上面的代码，文件 **app.log** 的内容如下–

```py
CRITICAL:root:Host www.python.org unknown
ERROR:root:Could not find 'spam'
```

要更改输出或输出水平，请更改参数至**基本配置()**调用，如下面给出的代码所示–

**代码#2 :**

```py
logging.basicConfig( 
        filename = 'app.log', 
        level = logging.WARNING, 
        format = '%(levelname)s:%(asctime)s:%(message)s')
```

**输出:**

```py
CRITICAL:2012-11-20 12:27:13, 595:Host www.python.org unknown
ERROR:2012-11-20 12:27:13, 595:Could not find 'spam'
WARNING:2012-11-20 12:27:13, 595:Feature is deprecated
```

日志配置直接硬编码到程序中。要从配置文件中进行配置，请将 **basicConfig()** 调用更改为以下内容。

**代码#3 :**

```py
import logging
import logging.config

def main():
    # Configure the logging system
    logging.config.fileConfig('logconfig.ini')
    ...
```

现在创建一个如下所示的配置文件–

```py
[loggers]
keys=root

[handlers]
keys=defaultHandler

[formatters]
keys=defaultFormatter

[logger_root]
level=INFO
handlers=defaultHandler
qualname=root

[handler_defaultHandler]
class=FileHandler
formatter=defaultFormatter
args=('app.log', 'a')

[formatter_defaultFormatter]
format=%(levelname)s:%(name)s:%(message)s

```

如果您想对配置进行更改，只需根据需要编辑文件即可。

暂且忽略日志模块有大约一百万个高级配置选项，这个解决方案对于简单的程序和脚本来说已经足够了。只需确保在进行任何日志记录调用之前执行`basicConfig()`调用，程序就会生成日志记录输出。

**参考:**[https://docs.python.org/3/howto/logging-cookbook.html](https://docs.python.org/3/howto/logging-cookbook.html)