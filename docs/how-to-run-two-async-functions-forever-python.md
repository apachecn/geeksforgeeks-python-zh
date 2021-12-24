# 如何永远运行两个异步函数——Python

> 原文:[https://www . geesforgeks . org/how-run-two-async-functions-forever-python/](https://www.geeksforgeeks.org/how-to-run-two-async-functions-forever-python/)

异步编程是一种我们可以执行多个任务而不阻塞 Main 任务(函数)的编程类型。在 Python 中，并发执行多个函数的方法有很多，其中一种方法就是使用 **asyncio** 。异步编程允许您编写在单个线程中运行的并发代码。

**注意:** Asyncio 不使用线程或多处理来使程序异步。

[**【科罗廷】**](https://www.geeksforgeeks.org/coroutine-in-python/) **:** 科罗廷是一种通用的控制结构，流量控制在两个不同的例程之间协作传递，而不返回。在 asyncio 中，可以通过在 def 之前使用 async 关键字来创建 Coroutine。

```py
async def speak_async():
   for i in range(100):
       print("Hello I'm Abhishek, writer on GFG")
```

如果您尝试直接运行异步函数，您将收到运行时警告:

> RuntimeWarning:从未等待过 coroutine“speak _ async”
> 
> speak_async()

要运行异步函数，你必须使用事件循环来调用它。

**事件循环:**您可以将事件循环看作运行异步任务和回调、执行网络 IO 操作以及运行子流程的函数。

**示例 1:** 运行异步函数运行单个异步函数的事件循环示例:

## 蟒蛇 3

```py
import asyncio

async def function_asyc():
    for i in range(5):
        print("Hello, I'm Abhishek")
        print("GFG is Great")
    return 0

# to run the above function we'll 
# use Event Loops these are low 
# level functions to run async functions
loop = asyncio.get_event_loop()
loop.run_until_complete(function_asyc())
loop.close()
print("HELLO WORLD")
print("HELLO WORLD")

# You can also use High Level functions Like:
# asyncio.run(function_asyc())
```

**Output**

```py
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
HELLO WORLD
HELLO WORLD
```

**例 2:** 一次执行多个功能。为此，我们必须创建一个新的异步函数(main)，并调用该新函数(main)中的所有异步函数(我们希望同时运行)。然后使用事件循环调用新的(主)函数…

**代码:**

## 蟒蛇 3

```py
import asyncio

async def function_asyc():
    for i in range(100000):
        if i % 50000 == 0:
            print("Hello, I'm Abhishek")
            print("GFG is Great")
    return 0

async def function_2():
    print("\n HELLO WORLD \n")
    return 0

async def main():
    f1 = loop.create_task(function_asyc())
    f2 = loop.create_task(function_2())
    await asyncio.wait([f1, f2])

# to run the above function we'll 
# use Event Loops these are low 
# level functions to run async functions
loop = asyncio.get_event_loop()
loop.run_until_complete(main())
loop.close()

# You can also use High Level functions Like:
# asyncio.run(function_asyc())
```

**Output**

```py
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great

 HELLO WORLD 
```

**注:**。create_task()用于一次运行多个异步函数。

**例 3:** 这里可以看到 function_async()和 function_2()没有并发运行，先显示 function_async()的输出，再显示 function_2()的输出，也就是说 function_async()执行完之后，function_2()正在执行。

但我们不想那样！我们希望这两个函数同时进步，所以为了实现这一点，在 python 中，我们必须明确告诉计算机何时从一个函数转换到另一个函数。

**代码:**

## 蟒蛇 3

```py
import asyncio

async def function_asyc():

    for i in range(100000):
        if i % 50000 == 0:
            print("Hello, I'm Abhishek")
            print("GFG is Great")

            # New Line Added
            await asyncio.sleep(0.01)
    return 0

async def function_2():
    print("\n HELLO WORLD \n")
    return 0

async def main():
    f1 = loop.create_task(function_asyc())
    f2 = loop.create_task(function_2())
    await asyncio.wait([f1, f2])

# to run the above function we'll 
# use Event Loops these are low level
# functions to run async functions
loop = asyncio.get_event_loop()
loop.run_until_complete(main())
loop.close()

# You can also use High Level functions Like:
# asyncio.run(function_asyc())
```

**Output**

```py
Hello, I'm Abhishek
GFG is Great

 HELLO WORLD 

Hello, I'm Abhishek
GFG is Great
```

现在可以看到，第二个函数是在运行函数(function_async())的执行过程中执行的。这些是基础，现在让我们看看如何永远运行两个异步函数。

### 永远运行两个异步函数:

**方法 1:** 只需使用主函数中的 while True 循环:

## 蟒蛇 3

```py
import asyncio

async def function_asyc():
    i = 0
    while i < 1000000:
        i += 1
        if i % 50000 == 0:
            print("Hello, I'm Abhishek")
            print("GFG is Great")
            await asyncio.sleep(0.01)

async def function_2():
    print("\n HELLO WORLD \n")

async def main():

    # New Line Added
    while True:
        f1 = loop.create_task(function_asyc())
        f2 = loop.create_task(function_2())
        await asyncio.wait([f1, f2])

# to run the above function we'll 
# use Event Loops these are low
# level functions to run async functions
loop = asyncio.get_event_loop()
loop.run_until_complete(main())
loop.close()
```

**输出:**

```py
Hello, I'm Abhishek
GFG is Great

 HELLO WORLD 

Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great
.
.
.
.
```

**方法 2:** 对两个函数使用 while True 循环，并使用 asyncio . confirm _ future()和 loop.run_forever()调用它们

**注意:**insure _ future 让我们在后台执行一个 coroutine，不需要显式等待它完成。

## 蟒蛇 3

```py
import asyncio

async def function_asyc():
    i = 0

    while True:
        i += 1
        if i % 50000 == 0:
            print("Hello, I'm Abhishek")
            print("GFG is Great")
            await asyncio.sleep(0.01)

async def function_2():
    while True:
        await asyncio.sleep(0.01)
        print("\n HELLO WORLD \n")

loop = asyncio.get_event_loop()
asyncio.ensure_future(function_asyc())
asyncio.ensure_future(function_2())
loop.run_forever()
```

**输出:**

```py
Hello, I'm Abhishek
GFG is Great
Hello, I'm Abhishek
GFG is Great

 HELLO WORLD 

Hello, I'm Abhishek
GFG is Great
.
.
.
```