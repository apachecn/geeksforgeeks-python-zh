# Python 中的多线程爬虫

> 原文:[https://www . geesforgeks . org/多线程-python 中的爬虫/](https://www.geeksforgeeks.org/multithreaded-crawler-in-python/)

在本文中，我们将描述如何使用 Python 构建一个简单的基于多线程的爬虫。

## **所需模块**

[**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)T5:美人汤(bs4)是一个从 HTML 和 XML 文件中提取数据的 Python 库。要安装此库，请在 IDE/终端中键入以下命令。

```
pip install bs4
```

[**请求:**](https://www.geeksforgeeks.org/python-requests-tutorial/) 这个库可以让你非常轻松的发送 HTTP/1.1 请求。要安装此库，请在 IDE/终端中键入以下命令。

```
pip install requests
```

## **分步实施**

**第一步:**我们首先导入所有需要抓取的库。如果你正在使用 Python3，你应该已经拥有了除了美丽的请求之外的所有库。因此，如果您还没有安装这两个库，您将需要使用上面指定的命令来安装它们。

## 蟒 3

```
import multiprocessing
from bs4 import BeautifulSoup
from queue import Queue, Empty
from concurrent.futures import ThreadPoolExecutor
from urllib.parse import urljoin, urlparse
import requests
```

**第二步:**创建一个主程序，然后创建一个 MultiThreadedCrawler 类的对象，并将种子 URL 传递给它的参数化构造函数，并调用 run _ web _ flutter()方法。

## 蟒 3

```
if __name__ == '__main__':
    cc = MultiThreadedCrawler("https://www.geeksforgeeks.org/")
    cc.run_web_crawler()
    cc.info()
```

**第三步:**创建一个名为 MultiThreadedCrawler 的类。并初始化构造函数中的所有变量，将基本 URL 分配给名为 seed_url 的实例变量。然后使用 HTTPS 和网络位置等方案将基本网址格式化为绝对网址。

要同时执行爬网前沿任务，请在 python 中使用多线程。创建一个线程池执行器类的对象，并将最大工作线程数设置为 5，即一次执行 5 个线程。并且为了避免重复访问网页，为了维护历史创建一个集合数据结构。

创建一个队列来存储爬网边界的所有网址，并将第一项作为种子网址。

## 蟒 3

```
class MultiThreadedCrawler:

    def __init__(self, seed_url):
        self.seed_url = seed_url
        self.root_url = '{}://{}'.format(urlparse(self.seed_url).scheme,
                                         urlparse(self.seed_url).netloc)
        self.pool = ThreadPoolExecutor(max_workers=5)
        self.scraped_pages = set([])
        self.crawl_queue = Queue()
        self.crawl_queue.put(self.seed_url)
```