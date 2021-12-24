# 如何创建一个空的 PyGame 窗口？

> 原文:[https://www . geeksforgeeks . org/如何创建一个空的 pygame 窗口/](https://www.geeksforgeeks.org/how-to-create-an-empty-pygame-window/)

Pygame 窗口是一个简单的窗口，就像任何其他窗口一样，我们在其中显示我们的游戏屏幕。这是我们做的第一个任务，这样我们就可以把我们的输出显示到某个东西上。我们在这里的主要目标是创建一个窗口，并保持它运行，除非用户想退出。要执行这些任务，我们首先需要安装 pygame 包，并在其中导入一些预定义的函数。

### **安装**

要安装此模块，请在终端中键入以下命令。

```
pip install pygame 
```

#### 逐步实施:

**第一步:**首先我们导入并初始化所有导入的模块。我们使用 import pygame 来导入所有模块和。init()函数来初始化这些模块。

```
import pygame
pygame.init() 
```

**第二步:**初始化一个窗口显示。我们用。函数创建一个窗口。我们将窗口的宽度和高度作为参数传递给 set_mode()函数。

```
pygame.display.set_mode((width_of_window,height_of_window))
```

**步骤 3:** 保持该窗口运行，直到用户按下退出按钮。我们使用的变量是真的，除非用户按下退出按钮。为了保持游戏运行，我们使用 while 循环来检查变量是否为真。

```
running  = True

while running:  

    for event in pygame.event.get():  
        if event.type == pygame.QUIT:  
           running = False
```

**完整代码:**

## 蟒蛇 3

```
# import pygame package
import pygame

# initializing imported module
pygame.init()

# displaying a window of height
# 500 and width 400
pygame.display.set_mode((400, 500))

# creating a bool value which checks
# if game is running
running = True

# keep game running till running is true
while running:

    # Check for event if user has pushed
    # any event in queue
    for event in pygame.event.get():

        # if event is of type quit then 
        # set running bool to false
        if event.type == pygame.QUIT:
            running = False
```

**输出:**

![](img/dbb05e795c83de1ea7086a31d2ee97f8.png)