# Python 中的 ProcessPoolExecutor 类

> 原文:[https://www . geesforgeks . org/processpoolexecutor-python 中的类/](https://www.geeksforgeeks.org/processpoolexecutor-class-in-python/)

**先决条件–**[](https://www.geeksforgeeks.org/multiprocessing-python-set-1/)

**它允许代码的并行性，Python 语言有两种实现方式，第一种是通过多处理模块，第二种是通过多线程模块。从 Python 3.2 开始，一个名为 **ProcessPoolExecutor** 的新类在 Python 中以并发方式引入。高效管理和创建流程的期货模块。但是等等，如果 python 已经内置了一个多处理模块，那么为什么引入了一个新模块。我先回答这个问题。**

***   When the number of processes is small, it is not a problem to dynamically generate new processes, but if we deal with many processes, it will be very troublesome to manage the processes. In addition, creating so many processes will lead to a decrease in throughput, which is computationally inefficient. One way to maintain throughput is to create & instantiate an idle process pool in advance and reuse the processes in the pool until all the processes are exhausted. This reduces the overhead of creating new processes.*   In addition, the pool tracks and manages the process life cycle and arranges them on behalf of programmers, thus making the code simpler and making fewer mistakes.**

****语法:****

> **concurrent . futures . processpoolexecutor(max _ workers =None，mp_context=，初始值设定项= None，initargs=()**
> 
> ****参数:****
> 
> ***   **Max _ workers** : It is the number of processes, that is, the size of the pool. If the value is None, by default, 61 processes will be created on Windows even if the number of available cores exceeds this value.*   **MP _ context** : it is a multiprocessing context; if it is blank or blank, the default multiprocessing context will be used. It allows the user to control the startup method.*   **Initializer** : The initializer accepts a callable one that is called at the beginning of each work process.*   **initargs** : a set of parameters passed to the initializer.**

****ProcessPoolExecutor 方法:** ProcessPoolExecutor 类公开了以下异步执行 Process 的方法。下面给出详细的解释。**

***   **Submit (fn, *args, * * kwargs):** It runs a callable or a method and returns a Future object, which represents the execution status of the method.*   **Mapping (fn, *iterables, timeout=None, chunk size = 1):** It immediately maps the method and iterables together and will throw an exception at the same time. The future. If it fails to complete within the timeout limit, the timeout error occurs.
    *   If iterables is very large, then the block size greater than 1 can improve the performance when using ProcessPoolExecutor.*   **关闭（等待=真，*取消 _ 期货=假):**
    *   It signals the executor to release all resources when the execution of futures is finished.
    *   Must be called before the executor.submit () and executor.map () methods, otherwise a RuntimeError will be thrown.
    *   Wait=True makes this method not return until the execution of all threads is completed and resources are released.
    *   Cancel_futures=True Then the executor will cancel all future threads that have not been started yet.*   **Cancel ():** Try to cancel the call. If you can't cancel the call, return False; otherwise, return True.*   **Cancelled ():** Returns True if the call is cancelled.*   **Running ():** Returns True if the process is running and cannot be cancelled.*   **done ():** Returns True if the process has finished executing.*   **Result (timeout = none):** Returns the value returned by the process. If the process is still executing, wait for the specified timeout; otherwise, a TimeoutError will be raised. If no TimeoutError is specified, wait for the process to finish forever.*   [T0】 add _ done _ callback(fn): 【T1: Attach a callback function, which is called when the process finishes executing.**

#### **例 1**

**下面的代码演示了 ProcessPoolExecutor 的使用，请注意，与多处理模块不同，我们不必使用循环显式调用、使用列表跟踪进程或使用连接等待进程进行同步，或者在进程完成后释放资源。构造函数本身会将所有内容隐藏起来，使代码紧凑且无错误。**

 **## 蟒 3

```py
from concurrent.futures import ProcessPoolExecutor
from time import sleep

values = [3,4,5,6]
def cube(x):
    print(f'Cube of {x}:{x*x*x}')

if __name__ == '__main__':
    result =[]
    with ProcessPoolExecutor(max_workers=5) as exe:
        exe.submit(cube,2)

        # Maps the method 'cube' with a iterable
        result = exe.map(cube,values)

    for r in result:
      print(r)
```** 

****输出:****

```py
Cube of 2:8
Cube of 3:27
Cube of 6:216
Cube of 4:64
Cube of 5:125
```

#### **例 2**

**下面的代码是通过发出一个 HTTP 请求在互联网上获取图像，我使用的是请求库。代码的第一部分对应用编程接口进行一对一的调用，即下载速度很慢，而代码的第二部分使用多个进程进行并行请求以获取应用编程接口。**

**您可以尝试上面讨论的各种参数，看看它如何调整加速，例如，如果我将进程池设置为 6，而不是 3，加速会更显著。**

 **## 蟒 3

```py
import requests
import time
import os
import concurrent.futures

img_urls = [
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623210949/download21.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211125/d11.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211655/d31.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212213/d4.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212607/d5.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623235904/d6.jpg',
]

t1 = time.time()
print("Downloading images with single process")
def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print("Downloading..")

for img in img_urls:
    download_image(img)

t2 = time.time()
print(f'Single Process Code Took :{t2-t1} seconds')
print('*'*50)

t1 = time.time()
print("Downloading images with Multiprocess")

def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print(f"[Process ID]:{os.getpid()} Downloading..")

with concurrent.futures.ProcessPoolExecutor(3) as exe:
    exe.map(download_image, img_urls)

t2 = time.time()
print(f'Multiprocess Code Took:{t2-t1} seconds')
```** 

****输出:****

```py
Downloading images with single process
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Single Process Code Took :1.2382981777191162 seconds
**************************************************
Downloading images with Multiprocess
[Process ID]:118741 Downloading..
[Process ID]:118742 Downloading..
[Process ID]:118740 Downloading..
[Process ID]:118741 Downloading..
[Process ID]:118742 Downloading..
[Process ID]:118740 Downloading..
Multiprocess Code Took:0.8398590087890625 seconds
```