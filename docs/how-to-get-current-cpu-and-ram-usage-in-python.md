# 如何在 Python 中获取当前的 CPU 和 RAM 使用情况？

> 原文:[https://www . geeksforgeeks . org/如何获取 python 中当前的 cpu 和 ram 使用情况/](https://www.geeksforgeeks.org/how-to-get-current-cpu-and-ram-usage-in-python/)

**先决条件:**

*   高效 PSU
*   操作系统（Operating System）

CPU 使用率或利用率是指计算机处理某些信息所花费的时间。另一方面，内存使用率指的是特定系统在特定时间使用内存的时间。这两者都可以使用 python 来检索。

### CPU 使用情况

**方法 1:使用 psutil**

函数 psutil.cpu_percent()以百分比的形式提供当前系统范围的 cpu 利用率。它采用的参数是时间间隔(秒)。由于 CPU 利用率是在一段时间内计算的，因此建议提供一个时间间隔。

**语法:**

```
cpu_percent(time_interval)
```

**例:**

## 蟒蛇

```
# Importing the library
import psutil

# Calling psutil.cpu_precent() for 4 seconds
print('The CPU usage is: ', psutil.cpu_percent(4))
```

**输出:**

```
The CPU usage is:  2.4
```

**方法二:使用 OS 模块**

**psutil.getloadavg()** 以元组的形式提供 CPU 的负载信息。 **psutil.getloadavg()** 在后台运行，结果每隔 *5 秒*更新一次。 **os.cpu_count()** 返回系统中的 cpu 数量。

**示例:**

## 蟒蛇 3

```
import os
import psutil

# Getting loadover15 minutes
load1, load5, load15 = psutil.getloadavg()

cpu_usage = (load15/os.cpu_count()) * 100

print("The CPU usage is : ", cpu_usage)
```

**输出:**

```
The CPU usage is: 13.4
```

### RAM 使用情况

**方法 1:使用 psutil**

函数 **psutil.virutal_memory()** 返回一个关于系统内存使用情况的命名元组。元组中的第三个字段*代表内存的使用百分比。按**(合计-可用)/合计* 100 计算。***

函数输出中的总计字段为:

*   **Total** : Total memory not including swap.
*   **: available memory of the process**
***   **percentage** : percentage of used memory.*   **: used memory*****   **Free memory** : unused memory available at any time.****

******例:******

 ****## 蟒蛇

```
# Importing the library
import psutil

# Getting % usage of virtual_memory ( 3rd field)
print('RAM memory % used:', psutil.virtual_memory()[2])
```**** 

******输出:******

```
**RAM memory % used: 76.9**
```

******方法二:使用 OS 模块******

****os 模块对于计算 CPU 中的 ram 使用量也很有用。以标志作为输入的 **os.popen()** 方法可以提供总的、可用的和已用的内存。这种方法打开一条通向或来自命令的管道。根据模式是“r”还是“w”，可以读取或写入返回值。****

******语法:******

```
**os.popen(command[, mode[, bufsize]])**
```

******例:******

 ****## 蟒 3

```
import os

# Getting all memory using os.popen()
total_memory, used_memory, free_memory = map(
    int, os.popen('free -t -m').readlines()[-1].split()[1:])

# Memory usage
print("RAM memory % used:", round((used_memory/total_memory) * 100, 2))
```**** 

******输出:******

```
**RAM memory % used: 17.55**
```

******注意:**由于为 linux 系统指定了 free flag 和 system 命令，因此 os 模块方法仅适用于 Linux 系统。****