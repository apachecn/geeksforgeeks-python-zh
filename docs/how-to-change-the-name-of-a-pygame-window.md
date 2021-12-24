# 如何更改 Pygame 窗口的名称？

> 原文:[https://www . geesforgeks . org/如何更改游戏窗口名称/](https://www.geeksforgeeks.org/how-to-change-the-name-of-a-pygame-window/)

**PyGame 窗口**是一个简单的窗口，在窗口屏幕上显示我们的游戏。默认情况下，pygame 使用“pygame window”作为标题，Pygame 图标作为 Pygame window 的徽标。我们可以使用 **set_caption()** 功能更改名称，使用 **set_icon()** 设置我们窗口的图标。

**更改 pygame 窗口名称:**

```py
Syntax: pygame.display.set_caption('Title of window')
```

**更改 pygame 窗口图标:**

```py
Syntax: pygame.display.set_icon(Icon_name)
```

### 逐步实施:

**第一步:**首先我们导入并初始化所有导入的模块。我们使用 import pygame 来导入所有模块和。init()函数来初始化这些模块。

```py
import pygame
pygame.init() 
```

**第二步:**初始化一个窗口显示。我们使用**。set_mode()** 功能创建窗口。我们将窗口的宽度和高度作为参数传递给 set_mode()函数。

```py
pygame.display.set_mode((width_of_window,height_of_window))
```

**第三步:**要更改 pygame 窗口的默认标题和图标，我们使用**。set_caption()** 和**。set_icon()** 功能。要更改图标，我们首先使用 pygame.image.load("image_path ")函数加载图标图像，然后使用。set_icon()更改默认图像。

```py
pygame.display.set_caption('GeeksforGeeks')

Icon = pygame.image.load('gfglogo.png')

pygame.display.set_icon(Icon)
```

**步骤 4:** 保持该窗口运行，直到用户按下退出按钮。我们使用的变量是真的，除非用户按下退出按钮。为了保持游戏运行，我们使用 while 循环来检查变量是否为真。

```py
running  = True

while running:  
    for event in pygame.event.get():  
        if event.type == pygame.QUIT:  
           running = False
```

**完整代码:**

## 蟒蛇 3

```py
# import pygame module
import pygame

# initializing imported module
pygame.init()

# Displaying a window of height
# 500 and width 400
pygame.display.set_mode((400, 500))

# Here we set name or title of our
# pygame window
pygame.display.set_caption('GeeksforGeeks')

# Here we load the image we want to
# use
Icon = pygame.image.load('gfglogo.png')

# We use set_icon to set new icon
pygame.display.set_icon(Icon)

# Creating a bool value which checks if
# game is running
running = True

# Keep game running till running is true
while running:

    # Check for event if user has pushed
    # any event in queue
    for event in pygame.event.get():

        # If event is of type quit then set
        # running bool to false
        if event.type == pygame.QUIT:
            running = False
```

**输出:**

![](img/31a67a12a7532c30b58c265b4c93bd85.png)