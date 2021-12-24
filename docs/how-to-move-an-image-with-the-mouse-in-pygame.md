# 如何在 PyGame 中用鼠标移动图像？

> 原文:[https://www . geeksforgeeks . org/如何在 pygame 中用鼠标移动图像/](https://www.geeksforgeeks.org/how-to-move-an-image-with-the-mouse-in-pygame/)

Pygame 是一个 Python 库，用来创建跨平台的视频游戏。Pygame 创建的游戏可以通过任何输入设备轻松运行，如鼠标、键盘和操纵杆。你想制作一个通过鼠标控制运行的游戏吗？你不知道鼠标在里面的时候怎么移动图像吗？别担心，你需要做的是声明两个值，即运行和移动。一旦声明了值，设置应用程序在运行状态下应该做什么。阅读下面的文章，了解更多细节。

### 方法:

**第一步:**首先导入库 pygame。

```py
import pygame
from pygame.locals import *
```

**第二步:**现在，把我们想在游戏中使用的颜色作为输入。

```py
color_1 = #RGB value of color 1
color_2 = #RGB value of color 2
color_n = #RGB value of color n
```

**第三步:**然后，构建一个 GUI 游戏。

```py
pygame.init()
```

**第四步:**进一步，设置你的 GUI 游戏的维度。

```py
w, h = #Width dimension, #Height dimension
screen = pygame.display.set_mode((w, h))
```

**第五步:**接下来，将图像作为输入，用鼠标移动

```py
img = pygame.image.load('#Enter the image')
img.convert()
```

**第六步:**此外，你可以通过在图像周围添加矩形边框来使图像看起来有吸引力。

```py
rect = img.get_rect()
rect.center = w//2, h//2
```

**步骤 7:** 稍后，设置运行游戏的运行值和移动图像的移动值。

```py
running = True
moving = False
```

**第八步:**设置你希望你的应用在运行状态下要做的事情。

```py
while running:
   for event in pygame.event.get():
```

*   **第 8.1 步:**一旦 app 处于运行状态，如果用户想退出，就让它退出。

```py
       if event.type == QUIT:
           running = False
```

*   **第 8.2 步:**万一用户不想退出，把你的图片在 GUI app 的维度上移动。

```py
       elif event.type == MOUSEBUTTONDOWN:
          if rect.collidepoint(event.pos):
              moving = True  
```

*   **第 8.3 步:**接下来，如果您想仅用鼠标点击来移动图像，请将移动值设置为 False，否则，如果您想不用鼠标点击来移动图像，请将移动设置为 True。

```py
       elif event.type == MOUSEBUTTONUP:          
           moving = False
```

*   **步骤 8.4:** 此外，如果您的图像已经移动过一次，请将其设置为移动状态。

```py
       elif event.type == MOUSEMOTION and moving:
           rect.move_ip(event.rel)  
```

**第九步:**接下来需要在屏幕上设置屏幕颜色和图像。

```py
   screen.fill(YELLOW)
   screen.blit(img, rect)
```

**步骤 10:** 此外，通过构建图像的边框来使您的图像看起来有吸引力。

```py
   pygame.draw.rect(screen, BLUE, rect, 2)
```

**步骤 11:** 此外，更新在 GUI 游戏中所做的更改。

```py
   pygame.display.update()
```

**第十二步:**最后退出 GUI 游戏。

```py
pygame.quit()
```

下面是实现。

## 计算机编程语言

```py
# Python program to move the image
# with the mouse

# Import the library pygame
import pygame
from pygame.locals import *

# Take colors input
YELLOW = (255, 255, 0)
BLUE = (0, 0, 255)

# Construct the GUI game
pygame.init()

# Set dimensions of game GUI
w, h = 640, 350
screen = pygame.display.set_mode((w, h))

# Take image as input
img = pygame.image.load('geek.jpg')
img.convert()

# Draw rectangle around the image
rect = img.get_rect()
rect.center = w//2, h//2

# Set running and moving values
running = True
moving = False

# Setting what happens when game
# is in running state
while running:

    for event in pygame.event.get():

        # Close if the user quits the
        # game
        if event.type == QUIT:
            running = False

        # Making the image move
        elif event.type == MOUSEBUTTONDOWN:
            if rect.collidepoint(event.pos):
                moving = True

        # Set moving as False if you want
        # to move the image only with the
        # mouse click
        # Set moving as True if you want
        # to move the image without the
        # mouse click
        elif event.type == MOUSEBUTTONUP:
            moving = False

        # Make your image move continuously
        elif event.type == MOUSEMOTION and moving:
            rect.move_ip(event.rel)

    # Set screen color and image on screen
    screen.fill(YELLOW)
    screen.blit(img, rect)

    # Construct the border to the image
    pygame.draw.rect(screen, BLUE, rect, 2)

    # Update the GUI pygame
    pygame.display.update()

# Quit the GUI game
pygame.quit()
```

**输出:**

![pygame move image mouse](img/7bfe8e19a43a0686090a5d80faca77c4.png)