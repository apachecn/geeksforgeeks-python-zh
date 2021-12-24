# 用 Python 创建代理网络服务器|第 2 集

> 原文:[https://www . geesforgeks . org/creating-a-proxy-web server-in-python-set-2/](https://www.geeksforgeeks.org/creating-a-proxy-webserver-in-python-set-2/)

先决条件:[用 Python 创建代理网络服务器–设置 1](https://www.geeksforgeeks.org/creating-a-proxy-webserver-in-python-set-1/)

在本教程中，添加了一些有趣的特性，使其更加有用。

*   **添加域黑名单**。对于 Ex。facebook.com google.com。在我们的配置字典中创建一个黑名单域列表。目前，只需忽略/删除收到的黑名单域名请求。(理想情况下，我们必须用禁止的回应来回应。)

```

# Check if the host:port is blacklisted
for i in range(0, len(config['BLACKLIST_DOMAINS'])):
    if config['BLACKLIST_DOMAINS'][i] in url:
        conn.close()
return
```

*   **要添加主机阻止:**比方说，您可能需要允许来自特定子网的连接或特定人的连接。要添加此内容，请创建一个所有允许主机的列表。因为主机也可以是子网，所以添加正则表达式来匹配 IP 地址，特别是 IPV4 地址。*“IP v4 地址通常以点-十进制表示法表示，由四个十进制数字组成，每个数字的范围从 0 到 255，用点分隔，例如 172.16.254.1。每个部分代表一组 8 位(八位字节)的地址。”*
*   **使用正则表达式匹配正确的 IP 地址:**
    *   创建一个新的方法，在服务器类中使用 _ishostAllowed，并使用 fnmatch 模块来匹配正则表达式。遍历所有正则表达式，如果匹配，允许请求。如果没有发现客户端地址是任何正则表达式的一部分，那么发送一个禁止响应。现在，再次跳过这个响应创建部分。

*注意:在接下来的教程中，我们将创建一个完整的定制网络服务器，在那里将创建一个 createResponse 函数来处理一般的响应创建。*

```
def _ishostAllowed(self, host):

    """ Check if host is allowed to access
        the content """
    for wildcard in config['HOST_ALLOWED']:
        if fnmatch.fnmatch(host, wildcard):
            return True
    return False
```

默认主机匹配正则表达式是“*”来匹配所有主机。不过，表格 192.168 的正则表达式。*”也可以使用。服务器当前处理请求，但不显示任何消息，因此我们不知道服务器的状态。它的消息应该被记录到控制台上。为此，使用日志模块，因为它是线程安全的。(如果你记得的话，服务器是多线程的。)

**导入模块并设置其初始配置。**

```
logging.basicConfig(level = logging.DEBUG,
format = '[%(CurrentTime)-10s] (%(ThreadName)-10s) %(message)s',)
```

*   **创建一个单独的方法来记录每条消息**:将它作为一个参数传递，并添加线程名称和当前时间等附加数据来跟踪日志。此外，创建一个函数，为日志着色，使它们在 STDOUT 上看起来很漂亮。
    要实现这一点，在配置中添加一个布尔值，COLORED_LOGGING，并创建一个新的函数，根据 LOG_LEVEL 为传递给它的每个消息着色。

```
def log(self, log_level, client, msg):

    """ Log the messages to appropriate place """
    LoggerDict = {
       'CurrentTime' : strftime("%a, %d %b %Y %X", localtime()),
       'ThreadName' : threading.currentThread().getName()
    }
    if client == -1: # Main Thread
        formatedMSG = msg
    else: # Child threads or Request Threads
        formatedMSG = '{0}:{1} {2}'.format(client[0], client[1], msg)
    logging.debug('%s', utils.colorizeLog(config['COLORED_LOGGING'],
    log_level, formatedMSG), extra=LoggerDict)
```

*   **创建一个新的模块，coloraepython . py:**它包含一个维护颜色代码列表的 pycolors 类。将其分离到另一个模块中，以使代码模块化并遵循 PEP8 标准。

```
# ColorizePython.py
class pycolors:
HEADER = '\033[95m'
OKBLUE = '\033[94m'
OKGREEN = '\033[92m'
WARNING = '\033[93m'
FAIL = '\033[91m'
ENDC = '\033[0m' # End color
BOLD = '\033[1m'
UNDERLINE = '\033[4m'
```

**模块:**

```
import ColorizePython
```

**方法:**

```
def colorizeLog(shouldColorize, log_level, msg):
    ## Higher is the log_level in the log()
    ## argument, the lower is its priority.
    colorize_log = {
    "NORMAL": ColorizePython.pycolors.ENDC,
    "WARNING": ColorizePython.pycolors.WARNING,
    "SUCCESS": ColorizePython.pycolors.OKGREEN,
    "FAIL": ColorizePython.pycolors.FAIL,
    "RESET": ColorizePython.pycolors.ENDC
    }

    if shouldColorize.lower() == "true":
        if log_level in colorize_log:
            return colorize_log[str(log_level)] + msg + colorize_log['RESET']
        return colorize_log["NORMAL"] + msg + colorize_log["RESET"]
    return msg 
```

*   由于 colorizeLog 不是服务器类的函数，所以它被创建为一个名为 utils.py 的独立模块，该模块存储所有使代码更容易理解的实用程序，并将该方法放在那里。*在任何需要的地方添加适当的日志消息，尤其是每当*服务器的状态改变时。**
*   在退出应用程序之前，修改服务器中的关闭方法以退出所有正在运行的线程。 *threading.enumerate()* 遍历所有正在运行的线程，所以我们不需要维护它们的列表。当我们试图结束 main_thread 时，线程模块的行为是意外的。官方文件也指出:

*“join()如果试图加入当前线程，会引发运行时错误，因为这会导致死锁。在线程启动之前加入()也是一个错误，尝试这样做将引发相同的异常。*

所以，适当跳过它。这是相同的代码。

```
def shutdown(self, signum, frame):
    """ Handle the exiting server. Clean all traces """
    self.log("WARNING", -1, 'Shutting down gracefully...')
    main_thread = threading.currentThread() # Wait for all clients to exit
    for t in threading.enumerate():
        if t is main_thread:
            continue
            self.log("FAIL", -1, 'joining ' + t.getName())
        t.join()
        self.serverSocket.close()
    sys.exit(0)
```

如果您有任何意见/建议/疑问，请随时提出。🙂

关于作者:

平克什·巴杰蒂亚来自 IIIT 海得拉巴。 他本质上是一个极客，有大量值得寻找的项目。他的项目作品可以在这里看到 [。](https://github.com/pinkeshbadjatiya/)

如果你也想在这里展示你的博客，请查看 [GBlog](http://geeksquiz.com/gblog/) 在 GeeksforGeeks 上的客座博文。