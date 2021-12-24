# 如何使用 pygame 添加色彩微风效果？

> 原文:[https://www . geeksforgeeks . org/how-add-color-breezing-effect-use-pygame/](https://www.geeksforgeeks.org/how-to-add-color-breezing-effect-using-pygame/)

**Pygame** 是一个 python 库，可以专门用来设计和构建游戏。Pygame 只支持使用不同精灵构建的 2d 游戏。Pygame 并不特别适合设计游戏，因为它使用起来非常复杂，也没有像 unity 这样合适的 GUI，但是它确实为更复杂的项目构建了逻辑。

#### 安装:

在初始化 pygame 库之前，我们需要安装它。要安装它，请在终端中键入以下命令。

```
pip install pygame
```

#### 色彩微风效果:

Pygame 包含三元组格式的颜色编码，三元组包含三个值，这些值表示三种核心颜色，即红、蓝、绿的强度。各个颜色的值可以改变，以形成另一种独特的颜色。因为元组的值在运行时也是可变的，所以它给了我们添加一些颜色效果的灵活性，以使我们的游戏/应用程序更加独特和美丽。

其中一种颜色效果是微风效果，微风效果是一种颜色从一种色调平稳地变化到另一种色调而没有突然或突然变化的效果。这些效果可以在 RGB 键盘和鼠标中看到。

**示例:**

## 蟒蛇 3

```
import pygame
import random
import sys

# initializing the constructor
pygame.init()

# setting up variable screen
screen = pygame.display.set_mode((720,720))

# three arguments of the color tuple
c1 = random.randint(0,255)
c2 = random.randint(0,255)
c3 = random.randint(0,255)

# setting up variable clock
clock = pygame.time.Clock()

while True:
    for ev in pygame.event.get():
        if ev.type == pygame.QUIT:
            pygame.quit()

    # increases the shade of
    # the current color
    if 0 < c1 < 255:
        c1 += 1

    # if value of c1 exceeds
    # 255 it resets it to 0
    elif c1 >= 255:
        c1 -= 255

    # if value of c1 preceeds 0
    # it is incremented by 3
    elif c1 <= 0:
        c1 += 3

    # sets game fps to 60
    clock.tick(60)

    # sets bg color to tuple
    # (c1,c2,c3)
    screen.fill((c1,c2,c3))

    # updates the frames of
    # the game
    pygame.display.update()
```

**输出:**

<video class="wp-video-shortcode" id="video-386339-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200318152551/python-pygame-breezing-effect.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200318152551/python-pygame-breezing-effect.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200318152551/python-pygame-breezing-effect.webm)</video>