# 在 Python 中处理调用线程中的线程异常

> 原文:[https://www . geesforgeks . org/handling-a-threads-异常在调用方-线程在 python 中/](https://www.geeksforgeeks.org/handling-a-threads-exception-in-the-caller-thread-in-python/)

Python 中的多线程可以通过使用线程库来实现。为了调用线程，调用线程创建一个线程对象，并在其上调用 start 方法。一旦联接方法被调用，它就开始执行并执行类对象的 run 方法。

对于异常处理，使用 try-except 块来捕获在 try 块中引发的异常，并在 except 块中进行相应的处理

**示例:**

## 蟒蛇 3

```py
# Importing the modules
import threading
import sys

# Custom Thread Class
class MyThread(threading.Thread):
    def someFunction(self):
        print("Hello World")
    def run(self):
          self.someFunction()
    def join(self):
        threading.Thread.join(self)

# Driver function
def main():
    t = MyThread()
    t.start()
    t.join()

# Driver code
if __name__ == '__main__':
    main()
```

**输出:**

```py
Hello World
```

为了在调用线程中捕获和处理线程的异常，我们使用了一个变量，该变量将引发的异常(如果有)存储在被调用线程中，当被调用线程被联接时，联接函数检查 exc 的值是否为 None，如果是，则不生成异常，否则，存储在 exc 中的生成的异常将再次被引发。这发生在调用者线程中，因此可以在调用者线程本身中处理。

**示例:**该示例创建一个类型为 MyThread 的线程 t，该线程的 run()方法调用 someFunction()方法，该方法会引发 MyException，因此每当线程运行时，都会引发异常。为了捕捉调用线程中的异常，我们维护一个单独的变量 exc，当被调用线程引发异常时，该变量被设置为引发的异常。这个 exc 最后会在 join()方法中检查，如果不是 None，那么 join 只会引发相同的异常。因此，捕获的异常在调用方线程中被引发，因为连接在调用方线程(这里是主线程)中返回，因此被相应地处理。

## 蟒蛇 3

```py
# Importing the modules
import threading
import sys

# Custom Exception Class
class MyException(Exception):
    pass

# Custom Thread Class
class MyThread(threading.Thread):

  # Function that raises the custom exception
    def someFunction(self):
        name = threading.current_thread().name
        raise MyException("An error in thread "+ name)

    def run(self):

        # Variable that stores the exception, if raised by someFunction
        self.exc = None           
        try:
            self.someFunction()
        except BaseException as e:
            self.exc = e

    def join(self):
        threading.Thread.join(self)
        # Since join() returns in caller thread
        # we re-raise the caught exception
        # if any was caught
        if self.exc:
            raise self.exc

# Driver function
def main():

    # Create a new Thread t
    # Here Main is the caller thread
    t = MyThread()
    t.start()

    # Exception handled in Caller thread
    try:
        t.join()
    except Exception as e:
        print("Exception Handled in Main, Details of the Exception:", e)

# Driver code
if __name__ == '__main__':
    main()
```

**输出:**

> 在 Main 中处理的异常，异常的详细信息:线程 Thread-1 中的错误