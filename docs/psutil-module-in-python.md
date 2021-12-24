# Python 中的 Psutil 模块

> 原文:[https://www.geeksforgeeks.org/psutil-module-in-python/](https://www.geeksforgeeks.org/psutil-module-in-python/)

**Psutil** 是一个 Python 跨平台库，用于访问系统细节和流程实用程序。它用于跟踪系统中各种资源的利用情况。可以监控 CPU、内存、磁盘、网络、传感器等资源的使用情况。因此，该库用于系统监控、分析、限制进程资源和管理正在运行的进程。Python、2.7 和 3.4+版本支持它。

#### Linux Ubuntu/Debian 中的安装步骤

```
sudo pip install psutil
```

## 系统功能

#### 中央处理器

**1)PSU til . cpu _ times()–**该函数以命名元组的形式给出系统 CPU 时间。

**参数:**

*   用户–正常进程在用户模式下执行所花费的时间
*   系统–进程在内核模式下执行所花费的时间
*   空闲–系统空闲的时间
*   nice–优先进程在用户模式下执行所花费的时间
*   低等待时间–等待输入/输出完成的时间。这不计入空闲时间计数器。
*   IRQ–服务硬件中断所花费的时间
*   softirq–服务软件中断所花费的时间
*   窃取–在虚拟化环境中运行的其他操作系统花费的时间
*   来宾–在 Linux 内核的控制下运行来宾操作系统的虚拟 CPU 所花费的时间

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.cpu_times())
```

**输出**

> scput times(user = 5461.14，nice=2.44，system=1326.65，idle=45502.33，iowait=506.24，irq=0.0，softirq=5.46，steal = 0.0，guest=0.0，guest_nice=0.0)

**2)psutil . cpu _ percent(interval)–**此函数计算当前系统范围内的 CPU 利用率百分比。建议将时间间隔(秒)作为计算平均 CPU 使用率的函数的参数，忽略时间间隔参数可能会导致使用率值出现较大变化。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.cpu_percent(1))
```

**输出**

```
5.0
```

**3) psutil.cpu_count(逻辑=真)–**此功能显示系统中的逻辑 cpu 数量。逻辑内核的计算方法是物理内核的数量乘以每个内核上可以运行的线程数量。在没有逻辑内核的情况下，它只计算物理内核的数量。

**示例:**

## 计算机编程语言

```
import psutil

print("Number of cores in system", psutil.cpu_count())
print("\nNumber of physical cores in system",)
```

**输出:**

```
Number of cores in system 4
Number of physical cores in system 2
```

**4)PSU til . cpu _ stats()–**该函数将 CPU 统计数据作为命名元组给出。统计数据包括:

*   CTX _ switches–自引导以来上下文切换的次数。
*   中断——启动后的中断次数。
*   soft _ interrupts–自引导以来软件中断的次数。
*   syscalls–自引导以来的系统调用次数。在 Ubuntu 中总是设置为 0。

**示例:**

## 计算机编程语言

```
import psutil

print("CPU Statistics", psutil.cpu_stats())
```

> scpustats(CTX _ switches = 37382771，中断=13744347，soft_interrupts=6769413，syscalls=0)

**5)PSU til . cpu _ freq()–**该函数将 CPU 频率作为一个元组给出，该元组包括以 Mhz 表示的当前、最小和最大频率。Ubuntu 上的当前频率报告实时值。而在所有其他平台上，它代表名义上的“固定”值。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.cpu_freq())
```

**输出:**

> scpufreq(电流=931.42925，最小值=400.0，最大值=2000.0)

**6)PSU til . getloadavg()–**该函数以元组的形式给出最近 1 分钟、5 分钟和 15 分钟的平均系统负载。负载表示处于可运行状态的进程，使用中央处理器或等待使用中央处理器(例如，等待磁盘输入/输出)。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.getloadavg())
```

**输出:**

```
(0.22, 0.33, 0.35)
```

#### 记忆

**1)PSU til . virtual _ memory()–**该函数以字节为单位给出系统内存使用情况。已用和可用的总和可能等于也可能不等于总数。为了获得空闲物理内存的详细信息，使用了这个函数。

**参数:**

*   total–不包括交换的总物理内存。
*   可用内存——无需系统交换即可立即分配给进程的内存。
*   已用–已用内存。
*   空闲–内存未在使用，并且随时可用
*   活动–当前正在使用或最近使用的内存。
*   非活动–标记为未使用的内存。
*   缓冲区–缓存文件系统元数据等数据。
*   缓存–缓存的数据
*   共享—可由多个进程访问的内存。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.virtual_memory())
```

**输出:**

> svmem(total=4028772352，available=1061466112，percent=73.7，used=2401546240，free=412352512，active=2176798720，inactive=1196470272，buffers=70774784，cached = 1144098816，shared=313872384，slab = 31382384

**2)PSU til . swap _ memory()–**该函数以元组的形式提供交换内存统计的详细信息。

**参数:**

*   total–总交换内存(字节)
*   已用–已用交换内存(字节)
*   free–以字节为单位的空闲交换内存
*   百分比–使用百分比，计算方式为(总计–可用)/总计* 100
*   sin–系统从磁盘换入的字节数
*   sout–系统从磁盘换出的字节数

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.swap_memory())
```

**输出:**

> sswap(总计=2097147904L，已用=886620160L，免费=1210527744L，百分比=42.3，sin=1050411008，sout=1906720768)

#### 磁盘

**1)psutil . disk _ partitions()–**该功能以元组列表的形式提供所有已挂载磁盘分区的详细信息，包括设备、挂载点和文件系统类型。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.disk_partitions())
```

**输出:**

> [sdiskpart(device='/dev/sda1 '，mountpoint='/'，fstype='ext4 '，opts='rw，relatime，errors=remount-ro，data=ordered')]

**2) psutil.disk_usage(路径)-** 该函数给出给定路径的元组形式的磁盘使用统计信息。总空间、已用空间和可用空间以及使用百分比都以字节表示。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.disk_usage('/'))
```

**输出:**

> sdiskusage(total=787310764032，used=26450710528，free=720843354112，percent=3.5)

#### 网络

**1)psutil . net _ io _ counters()-**该函数以元组的形式给出网络输入输出统计的详细信息。

**参数:**

*   bytes _ send–发送的字节数
*   bytes _ recv–接收的字节数
*   packets _ send–发送的数据包数量
*   packets _ recv–收到的数据包数量
*   errin–接收时的错误总数
*   errout–发送时的错误总数
*   drop in–丢弃的传入数据包总数
*   丢弃–丢弃的传出数据包总数

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.net_io_counters())
```

**输出:**

> snetio(bytes _ send = 14508483，bytes_recv=62749361，packets _ sent = 84311，packets_recv=94888，errin=0，errout=0，dropin=0，drop in = 0)

**2)psutil . net _ connections()–**该函数将系统的套接字连接列表作为命名元组给出。

**参数:**

*   FD–套接字文件描述符。
*   系列–插座系列，可以是 AF_INET、AF_INET6 或 AF_UNIX。
*   type–套接字类型，可以是 SOCK_STREAM、SOCK_DGRAM 或 SOCK_SEQPACKET。
*   laddr–本地地址(ip，端口)命名元组
*   raddr–作为(ip，端口)命名元组的远程地址
*   状态–表示 TCP 连接的状态。
*   pid–打开套接字的进程的 PID，如果可检索，则为无。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.net_connections())
```

**输出:**

> [sconn(fd=118，family=2，type=1，laddr=addr(ip='192.168.12.184 '，port=59666)，raddr=addr(ip='172.217.166.42 '，port=443)，status = ' INSERTED '，pid=2428)，
> sconn(fd=-1，family=2，type=2，laddr=addr(ip='0。

**3)psutil . net _ if _ addrs()–**此功能用于获取系统上安装的每个网络接口卡的地址。它是一个字典，其关键字是网络接口卡名称，值是分配给它的每个地址的命名元组列表。每个元组包括:

*   系列–插座系列，AF_INET 或 AF_INET6
*   地址–主网卡地址
*   网络掩码–网络掩码地址
*   广播–广播地址。
*   PTP–“点对点”它是点对点接口上的目的地址。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.net_if_addrs())
```

**输出:**

> { ' wlo 1 ':[snicaddr(family = 2，address='192.168.12.184 '，netmask='255.255.255.0 '，broadcast='192.168.12.255 '，ptp=None)，snicaddr(family=10，address = ' fe80::664 f:767 c:91f 0:71 c0 % wlo 1 '，netmask='ffff:ffff:ffff

#### 传感器

**1)PSU til . sensors _ temperatures()-**此功能以摄氏度为单位返回系统的硬件温度。每个条目都是一个命名元组，代表某个硬件温度传感器。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.sensors_temperatures())
```

**输出:**

> {'acpitz': [shwtemp(label=，current=27.8，high=119.0，critical=119.0)]，shwtemp(label=，current=29.8，high=119.0，critical = 119.0)，shwtemp(label=，current=10.0，high=None，critical=None)]，' coretemp ':[shwtemp(label = ' Physical id 0 '，current=42.0，high=100.0，critical=100

**2)PSU til . sensors _ fans()–**此功能给出硬件风扇速度的详细信息，以 RPM(每分钟转数)表示。如果操作系统不支持传感器，将返回一个空字典。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.sensors_fans())
```

**输出:**

```
{'asus': [sfan(label='cpu_fan', current=3000)]}
```

**3)PSU til . sensors _ battery()–**此功能以命名元组的形式给出电池状态信息。

**参数:**

*   百分比–剩余的电池电量百分比。
*   秒秒–电池完全放电前的大约时间(秒)。
*   power _ plugged–如果连接了交流电源线，则为 True 如果没有连接，则为 False。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.sensors_battery())
```

**输出:**

> sbattery(百分比=98.98572501878287，secsleft = 22913，power _ plugged = False)

#### 其他系统信息

**1)PSU til . boot _ time()–**此函数返回系统启动时间，以自纪元以来的秒数表示。

**示例:**

## 计算机编程语言

```
import psutil, datetime

print(psutil.boot_time())
```

**输出:**

```
1582860765.0
```

**2)PSU til . users()–**该函数给出了以命名元组形式连接到系统的用户列表。

**参数:**

*   用户–这是用户的系统名称。
*   终端–用户的 tty。
*   主机–用户的主机名。
*   started–自纪元以来以秒为单位表示的浮点数的创建时间。
*   pid–登录过程的 PID。

**示例:**

## 计算机编程语言

```
import psutil

print(psutil.users())
```

**输出:**

> [suser(名称='admin1 '，终端='tty7 '，主机='localhost '，started=1582860800.0，pid=1747)]