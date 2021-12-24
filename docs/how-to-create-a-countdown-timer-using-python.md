# 如何用 Python 创建倒计时定时器？

> 原文:[https://www . geesforgeks . org/如何使用 python 创建倒计时定时器/](https://www.geeksforgeeks.org/how-to-create-a-countdown-timer-using-python/)

在本文中，我们将看到如何使用 Python 创建倒计时定时器。该代码将接受用户关于倒计时长度(以秒为单位)的输入。之后，倒计时将在*‘分:秒’格式的屏幕上开始。*我们将在这里使用时间模块。

### 方法

在本项目中，我们将使用时间模块及其 **sleep()** 功能。按照以下步骤创建倒计时定时器:

*   **第一步:**导入时间模块。
*   **第二步:**然后要求用户以秒为单位输入倒计时的长度。
*   **第 3 步:**该值作为参数‘t’发送至用户自定义功能 ***倒计时()*** 。使用输入函数读取的任何变量都是字符串。因此，将此参数转换为“int ”,因为它是字符串类型。
*   **第 4 步:**在此功能中，会运行一个 while 循环，直到时间变为 0。
*   **第五步:**使用 ***divmod()*** 计算分钟数和秒数。你可以在这里读到更多。
*   **第 6 步:**现在使用变量 ***时间格式*** 在屏幕上打印分和秒。
*   **第 7 步:**使用 ***end = '\r'*** 我们强制光标回到屏幕开始处(回车)，这样打印的下一行将覆盖上一行。
*   **第八步:*****time . sleep()*****用于使代码等待一秒钟。**
*   ****步骤 9:** 现在递减时间，这样 while 循环就可以收敛了。**
*   ****第十步:**循环完成后，我们会打印“洞中之火”，表示倒计时结束。**

**下面是上述方法的实现**

## **蟒蛇 3**

```
# import the time module
import time

# define the countdown func.
def countdown(t):

    while t:
        mins, secs = divmod(t, 60)
        timer = '{:02d}:{:02d}'.format(mins, secs)
        print(timer, end="\r")
        time.sleep(1)
        t -= 1

    print('Fire in the hole!!')

# input time in seconds
t = input("Enter the time in seconds: ")

# function call
countdown(int(t))
```

****输出:**** 

**<video class="wp-video-shortcode" id="video-430687-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200729151851/python-countdown-timer.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200729151851/python-countdown-timer.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200729151851/python-countdown-timer.webm)</video>**