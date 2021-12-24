# 如何在 Python3 中使用 ThreadPoolExecutor？

> 原文:[https://www . geesforgeks . org/how-用法-threadpoolexecutor-in-pyt 3/](https://www.geeksforgeeks.org/how-to-use-threadpoolexecutor-in-python3/)

**先决条件:** [**多线程**](https://www.geeksforgeeks.org/multithreading-python-set-1/)

**线程化**允许代码的并行性，Python 语言有两种方式实现其 1 <sup>st</sup> 是通过多处理模块，2 <sup>nd</sup> 是通过多线程模块。多线程非常适合于加速 I/O 绑定任务，如发出 web 请求、数据库操作或读取/写入文件。与此相反，像数学计算任务这样的 CPU 密集型任务在使用多处理时受益最大。这是由于 GIL(全球翻译锁)。

从 Python 3.2 开始，在 Python 中的 **concurrent.futures** 模块中引入了一个名为 **ThreadPoolExecutor** 的新类，以高效地管理和创建线程。但是等一下，如果 python 已经内置了线程模块，那么为什么要引入一个新模块。我先回答这个问题。

*   当线程数量较少时，动态生成新线程不是问题，但是如果我们处理许多线程，管理线程就会变得非常麻烦。除此之外，创建如此多的线程会导致吞吐量下降，这在计算上是低效的。保持吞吐量的一种方法是预先创建并实例化一个空闲线程池，并重用该池中的线程，直到所有线程都耗尽。这样就减少了创建新线程的开销。
*   此外，该池跟踪和管理线程生命周期，并代表程序员对它们进行调度，从而使代码更加简单，错误更少。

> **语法:**concurrent . futures . threadpoolexecutor(max _ workers =None，thread_name_prefix= "，初始值设定项= None，initargs=()
> 
> **参数:**
> 
> *   **max_workers** :这是一个线程数，也就是池的大小。从 3.8 开始，默认值为 min(32，os.cpu_count() + 4)。在这 5 个线程中，有 4 个是为输入/输出绑定任务保留的。
> *   **thread _ name _ prefix**:thread _ name _ prefix 是从 python 3.6 开始添加的，为线程赋予名称，以便于调试。
> *   **初始化器:**初始化器接受一个在每个工作线程开始时调用的可调用。
> *   **initargs:** 它是传递给初始值设定项的一组参数。

### 线程池执行器方法:

ThreadPoolExecutor 类公开了三种异步执行线程的方法。下面给出详细的解释。

1.  **submit(fn，*args，**kwargs):** 它运行一个可调用的或方法，并返回一个 Future 对象，表示该方法的执行状态。
2.  **地图(fn、*迭代、超时=无、chunksize = 1) :**
    *   它立即将方法和 iterables 映射在一起，并将同时引发异常。未来。如果未能在超时限制内完成，则超时错误。
    *   如果 iterables 非常大，那么块大小大于 1 可以提高使用 ProcessPoolExecutor 时的性能，但是对于 ThreadPoolExecutor，它没有这样的优势，即它可以保留默认值。
3.  **关机(等待=真、*取消 _ 期货=假):**
    *   它向执行器发出信号，要求在执行完期货时释放所有资源。
    *   它必须在 executor.submit()和 executor.map()方法之前调用，否则会引发 RuntimeError。
    *   wait=True 使方法在所有线程执行完毕并释放资源之前不返回。
    *   cancel_futures=True，那么执行器将取消所有尚未启动的未来线程。

**例 1:**

下面的代码演示了 ThreadPoolExecutor 的使用，请注意，与线程模块不同，我们不必使用循环显式调用、使用列表跟踪线程或使用 join 等待线程进行同步，或者在线程完成后释放资源，所有的事情都由构造函数本身负责，使代码紧凑且没有错误。

## 蟒蛇 3

```
from concurrent.futures import ThreadPoolExecutor
from time import sleep

values = [3,4,5,6]

def cube(x):
    print(f'Cube of {x}:{x*x*x}')

if __name__ == '__main__':
    result =[]
    with ThreadPoolExecutor(max_workers=5) as exe:
        exe.submit(cube,2)

        # Maps the method 'cube' with a list of values.
        result = exe.map(cube,values)

    for r in result:
      print(r)
```

**输出:**

```
Output: 
Cube of 2:8
Cube of 3:27
Cube of 4:64
Cube of 5:125
Cube of 6:216
```

**例 2:**

下面的代码是通过发出一个 HTTP 请求在互联网上获取图像，我使用的是请求库。代码的第一部分对应用编程接口进行一对一的调用，即下载速度很慢，而代码的第二部分使用线程进行并行请求以获取应用编程接口。

您可以尝试上面讨论的各种参数，看看它是如何调整加速的，例如，如果我将线程池设置为 6，而不是 3，加速会更显著。

## 蟒蛇 3

```
import requests
import time
import concurrent.futures

img_urls = [
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623210949/download21.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211125/d11.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211655/d31.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212213/d4.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212607/d5.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623235904/d6.jpg',
]

t1 = time.perf_counter()
def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print("Downloading..")

# Download images 1 by 1 => slow
for img in img_urls:
  download_image(img)
t2 = time.perf_counter()
print(f'Single Threaded Code Took :{t2 - t1} seconds')

print('*'*50)

t1 = time.perf_counter()
def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print("Downloading..")

# Fetching images concurrently thus speeds up the download.
with concurrent.futures.ThreadPoolExecutor(3) as executor:
    executor.map(download_image, img_urls)

t2 = time.perf_counter()
print(f'MultiThreaded Code Took:{t2 - t1} seconds')
```

**输出:**

```
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Single Threaded Code Took :2.5529379630024778 seconds
**************************************************
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
MultiThreaded Code Took:0.5221083430078579 seconds
```