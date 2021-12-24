# 使用 Python 打开像 C、D 或 E 这样的计算机驱动器

> 原文:[https://www . geesforgeks . org/open-computer-drives-like-c-d-or-e-use-python/](https://www.geeksforgeeks.org/open-computer-drives-like-c-d-or-e-using-python/)

你有没有想过，只需输入 C、D 或 E 就可以打开你的驱动器，然后驱动器就会打开。这可以通过使用 Python 来实现。所以，为了执行这个任务，我们使用了 [**操作系统**](https://www.geeksforgeeks.org/os-module-python-examples/) 库的 **os.startfile()** 方法。此方法启动一个文件及其相关程序。

> **语法:** os.startfile(file_name)
> 
> **返回:**无。

现在让我们看看代码:

## 蟒蛇 3

```
# import library
import os

# take Input from the user 
query = input("Which drive you have to open ? C , D or E: \n")

# Check the condition for 
# opening the C drive
if "C" in query or "c" in query:
  os.startfile("C:")

# Check the condition for 
# opening the D drive
elif "D" in query or "d" in query:
  os.startfile("D:")

# Check the condition for 
# opening the D drive
elif "E" in query or "e" in query:
  os.startfile("E:")

else:
    print("Wrong Input")
```

**输出:**

<video class="wp-video-shortcode" id="video-476474-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200828185254/2020-08-28-18-50-05.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200828185254/2020-08-28-18-50-05.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200828185254/2020-08-28-18-50-05.mp4)</video>