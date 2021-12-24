# 计算往返时间(RTT)的程序

> 原文:[https://www . geesforgeks . org/program-calculate-往返-time-rtt/](https://www.geeksforgeeks.org/program-calculate-round-trip-time-rtt/)

**往返时间(RTT)** 是发送一个信号所花费的时间加上接收该信号的确认所花费的时间。因此，这个时间包括信号两点之间的传播时间。

在互联网上，终端用户可以通过查验 IP(互联网协议)地址来确定往返于该地址的 RTT。结果取决于各种因素

*   源互联网连接的数据传输速率。
*   传播媒介的本质。
*   源和目的地之间的物理距离。
*   源和目标之间的节点数。
*   终端用户所连接的局域网上的流量。
*   中间节点和远程服务器正在处理的其他请求的数量。
*   中间节点和远程服务器运行的速度。
*   电路中存在干扰。

示例:

```
Input : www.geeksforgeeks.org
Output : Time in seconds : 0.212174892426

Input : www.cricbuzz.com
Output : Time in seconds : 0.55425786972
```

## 计算机编程语言

```
# Python program to calculate RTT

import time
import requests

# Function to calculate the RTT
def RTT(url):

    # time when the signal is sent
    t1 = time.time()

    r = requests.get(url)

    # time when acknowledgement of signal
    # is received
    t2 = time.time()

    # total time taken
    tim = str(t2-t1)

    print("Time in seconds :" + tim)

# driver program
# url address
url = "http://www.google.com"
RTT(url)
```

**输出:**

```
  Time in seconds :0.0579478740692
```

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。