# 如何将多个命令绑定到 Tkinter 按钮？

> 原文:[https://www . geesforgeks . org/how-bind-multi-commands-to-tkinter-button/](https://www.geeksforgeeks.org/how-to-bind-multiple-commands-to-tkinter-button/)

Tkinter 中的按钮小部件提供了一种与应用程序交互的方式。用户按下一个按钮来执行附加到该按钮的某些操作。一般来说，我们用户为一个按钮提供一个操作，但是如果用户想要为一个按钮附加多个操作，该怎么办。

在本文中，我们将看到如何将多个操作/命令绑定到一个按钮。

要在 Tkit 中创建按钮，请遵循以下语法。

> **语法:**按钮(主，text =“Button”，command=function，options，…)
> 
> **参数:**
> 
> *   **主**:指放置按钮的顶层窗口
> *   **文本:**显示按钮的文本
> *   **命令:**按钮按下时将调用的动作
>     还有其他选项，但很少使用。
> *   **复合**:显示图像和文字
> *   **图像**:显示图像
> *   **pady** :提供垂直填充
> *   **padx** :提供水平填充

**方法 1** :使用[λ功能](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)和列表

在这个方法中，我们将把函数列表传递给 lambda，然后 lambda 将被传递给 command。

## 蟒蛇 3

```
# Import tkinter and Button Widget
from tkinter import Tk
from tkinter.ttk import Button

# Demo function 1
def fun1():
    print("Function 1")

# Demo function 2
def fun2():
    print("Function 2")

if __name__ == "__main__":
    # Creating top-level window
    master = Tk()

    # Setting window title
    master.title("Bind multiple function to Button")

    # Setting window Dimensions
    master.geometry("400x250")

    # Creating a button with more than one command using lambda
    button = Button(master, text="Button", command=lambda: [fun1(), fun2()])

    # Attaching button to the top-level window
    # Always remember to attach your widgets to the top-level
    button.pack()

    # Mainloop that will run forever
    master.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-529417-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4)</video>

**方法 2** :通过创建我们自己的泛型函数，该函数将为我们调用函数。

## 蟒蛇 3

```
# Import tkinter and Button Widget
from tkinter import Tk
from tkinter.ttk import Button

# funcs parameter will have the reference
# of all the functions that are passed as arguments i.e "fun1" and "fun2"
def combine_funcs(*funcs):

    # this function will call the passed functions
    # with the arguments that are passed to the functions
    def inner_combined_func(*args, **kwargs):
        for f in funcs:

            # Calling functions with arguments, if any
            f(*args, **kwargs)

    # returning the reference of inner_combined_func
    # this reference will have the called result of all
    # the functions that are passed to the combined_funcs
    return inner_combined_func

# Demo function 1
def fun1():
    print("Function 1")

# Demo function 2
def fun2():
    print("Function 2")

if __name__ == "__main__":
    # Creating top-level window
    master = Tk()

    # Setting window title
    master.title("Bind multiple function to Button")

    # Setting window Dimensions
    master.geometry("400x250")

    # Creating a button with more than one
    # command our own generic function
    button = Button(master, text="Button", 
                    command=combine_funcs(fun1, fun2))

    # Attaching button to the top-level window
    # Always remember to attach your widgets to the top-level
    button.pack()

    # Mainloop that will run forever
    master.mainloop()
```

在上面的方法中，您可能想知道我们如何将参数传递给 **fun1** 和 **fun2** ，因为如果我们执行以下操作

```
combine_funcs(fun1(arguments), fun2(arguments))
```

一旦应用程序运行，它将立即调用这些函数，但是我们希望这些函数只在按钮被按下时调用。因此，如果您想将参数传递给 fun1 或 fun2，答案很简单，请使用以下语法:

```
combine_funcs(lambda: fun1(arguments), lambda: fun2(arguments))
```

让我们看看下面的例子，我们实际上有参数到 **fun1** 和 **fun2** 。

## 蟒蛇 3

```
# Import tkinter and Button Widget
from tkinter import Tk
from tkinter.ttk import Button

# funcs parameter will have the reference
# of all the functions that are 
# passed as arguments i.e "fun1" and "fun2"
def combine_funcs(*funcs):

    # this function will call the passed functions
    # with the arguments that are passed to the functions
    def inner_combined_func(*args, **kwargs):
        for f in funcs:

            # Calling functions with arguments, if any
            f(*args, **kwargs)

    # returning the reference of inner_combined_func
    # this reference will have the called result of all
    # the functions that are passed to the combined_funcs
    return inner_combined_func

# Demo function 1 with params
def fun1(param):
    print("Function 1 {}".format(param))

# Demo function 2 with params
def fun2(param):
    print("Function 2 {}".format(param))

if __name__ == "__main__":
    # Creating top-level window
    master = Tk()

    # Setting window title
    master.title("Bind multiple function to Button")

    # Setting window Dimensions
    master.geometry("400x250")

    # Creating a button with more than
    # one command our own generic function
    button = Button(master,
                    text="Button",

                    # Passing arguments to "fun1" and "fun2"
                    command=combine_funcs(lambda: fun1("Function 1 PARAM"),
                                          lambda: fun2("Function 2 PARAM")))

    # Attaching button to the top-level window
    # Always remember to attach your widgets to the top-level
    button.pack()

    # Mainloop that will run forever
    master.mainloop()
```

**输出**:

<video class="wp-video-shortcode" id="video-529417-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201217192934/ice_video_20201217-192812.mp4)</video>