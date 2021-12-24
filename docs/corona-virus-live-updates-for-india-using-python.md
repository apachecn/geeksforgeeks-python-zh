# 印度电晕病毒实时更新–使用 Python

> 原文:[https://www . geesforgeks . org/corona-virus-live-updates-for-India-use-python/](https://www.geeksforgeeks.org/corona-virus-live-updates-for-india-using-python/)

众所周知，整个世界都受到了新冠肺炎疫情的影响，几乎每个人都在家工作。我们都应该利用这段时间来提高我们的技术技能，或者写一些好的 Pythonic 脚本。
让我们看一个简单的 Python 脚本来演示印度各州的冠状病毒病例。这个 Python 脚本从卫生部官方网站获取实时数据。然后数据在水平条形图中表示。
要运行此脚本，请遵循以下安装–

```py
$ pip install bs4
$ pip install tabulate
$ pip install matplotlib
$ pip install numpy 
$ pip install requests

```

我们试着一步一步执行脚本。
**第一步:**

## 蟒蛇 3

```py
# importing libraries

import requests
from bs4 import BeautifulSoup
from tabulate import tabulate
import os
import numpy as np
import matplotlib.pyplot as plt
```