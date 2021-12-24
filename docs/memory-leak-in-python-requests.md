# Python 请求中的内存泄漏

> 原文:[https://www . geesforgeks . org/memory-in-python-leak-requests/](https://www.geeksforgeeks.org/memory-leak-in-python-requests/)

当程序员忘记清除堆内存中分配的内存时，就会发生内存泄漏。这是一种资源泄漏或浪费。当应用程序内存泄漏时，机器的内存会被填满，从而降低机器的性能。在构建大型可扩展应用程序时，这是一个严重的问题。

**请求:**请求库是 Python 的一个组成部分，用于向指定的 URL 发出 HTTP 请求。无论是 REST APIs 还是 Web 报废，都必须了解请求，以便进一步使用这些技术。当一个人向 URI 提出请求时，它会返回一个响应。Python 请求提供了管理请求和响应的内置功能。

**Gc 模块:**Gc 模块是一个 python 内置模块，它为 python 垃圾收集器提供了一个接口。它提供了启用收集器、禁用收集器、调整收集频率、调试选项等功能。

在像 C 和 C++这样的低级语言中，程序员应该手动释放未使用的资源，即编写代码来管理资源。但是像 python、java 这样的高级语言有一个被称为垃圾收集器的自动内存管理器的概念。垃圾收集器管理应用程序内存的分配和释放。

**下面列出了我们将使用的一些 gc 方法。**

*   **get_objects():** 此方法返回垃圾收集器跟踪的所有对象的列表，不包括正在返回的列表。
*   **collect():** 该方法释放由收集器维护的列表中未被引用的对象。由于它们的实现，一些非引用对象不会立即自动释放。

我们将在请求中使用 get()方法，该方法返回一个响应对象。当响应对象未被引用(即被删除)时，它的内存应该立即释放，但是由于它的实现，资源不会自动释放。这是泄露内存的统计数据。

### **识别内存泄漏:**

**进场:**

*   获取并存储收集器跟踪(创建和活动)的对象数量。您可以使用 gc.get_objects()获取跟踪对象的列表，然后使用 len 函数计算对象的数量。
*   调用调用 request.get()方法的函数。
*   打印响应状态代码，以便我们可以确认对象已创建。
*   然后返回函数。当函数返回时，应该删除在函数中创建的所有。
*   获取当前跟踪的对象数量，并将阀门与泄漏对象的先前值进行比较。
*   如果当前返回的对象数大于，则存在内存泄漏。

**下面是实现:**

## 蟒蛇 3

```py
import requests
import gc

def call():

    # call the get with a url,here I used google.com
    # get method returns a response object
    response = requests.get('https://google.com')

    # print the status code of response
    print("Status code", response.status_code)

    # After the function is been returned,
    # the response object becomes non-referenced
    return

def main():
    print("No.of tracked objects before calling get method")

    # gc.get_objects() returns list objects been tracked
    # by the collector.
    # print the length of object list with len function.
    print(len( gc.get_objects() ) )

    # make a call to the function, that calls get method.
    call()

    print("No.of tracked objects after calling get method")

    # print the length of object list with len function.
    print(len( gc.get_objects() ) )

if __name__ == "__main__":
    main()
```

**输出:**

```py
No.of tracked objects before calling get method
16071
Status code 200
No.of tracked objects after calling get method
16158
```

### **修复内存泄漏:**

一个简单的解决方案是手动调用 gc.collect()方法，该方法将立即释放资源。

**进场:**

*   获取并存储收集器跟踪(创建和活动)的对象数量。您可以使用 gc.get_objects()获取跟踪对象的列表，然后使用 len 函数计算对象的数量。
*   调用调用 request.get()方法的函数。
*   打印响应状态代码，以便我们可以确认对象已创建。
*   然后返回函数。当函数返回时，应该删除在函数中创建的所有。
*   调用垃圾收集器来释放未使用的资源，即调用 gc.collect()方法。
*   获取当前跟踪的对象数量，现在您可以注意到由于清理未使用的资源而导致的对象数量减少。

**下面是实现:**

## 蟒蛇 3

```py
import requests
import gc

def call():

    # call the get with a url,here I used google.com
    # get method returns a response object
    response = requests.get('https://google.com')

    # print the status code of response
    print("Status code",response.status_code)

    # After the function is been returned,
    # the response object becomes non-referenced
    return

def main():
    print("No.of tracked objects before calling get method")

    # gc.get_objects() returns list objects been tracked
    # by the collector.
    # print the length of object list with len function.
    print(len( gc.get_objects() ) )

    # make a call to the function, that calls get method.
    call()

    # collect method immediately free the resource of
    # non-referenced object.
    gc.collect()

    # print the length of object list with len
    # function after removing non-referenced object.
    print("No.of tracked objects after removing non-referenced objects")
    print(len( gc.get_objects() ) )

if __name__ == "__main__":
    main()
```

**输出:**

```py
No.of tracked objects before calling get method
16071
Status code 200
No.of tracked objects after removing non-referenced objects
15954
```