# 在 Pygame 中为对象添加边界

> 原文:[https://www . geeksforgeeks . org/添加边界到 pygame 中的对象/](https://www.geeksforgeeks.org/adding-boundary-to-an-object-in-pygame/)

任何游戏的边界都非常重要。在蛇游戏、太空入侵者、乒乓球游戏等。边界条件非常重要。乒乓球比赛中，球在屏幕的边界反弹。

所以，这种界限背后的想法是，一旦球或物体碰到墙壁，就反向改变它的位置。

让我们看看如何为一个球从边界反弹的游戏添加边界。

**1。**首先，我们将制作 PyGame 窗口。

```py
# importing the module
import pygame

# instantiating the class
pygame.init()

# dimension of the screen
width = 700
height = 550

# colours
white = (255, 255, 255)
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
black = (0, 0, 0)

# creating a Screen
screen = pygame.display.set_mode((width, height))

# title of the screen
pygame.display.set_caption("Bouncy Ball")
```

**2。**现在，我们正在创造一个球。球只是画在屏幕上的一个圆。将在 while 循环中写入。这里我们宣布它的位置和速度。最初，球将被放置在中心(宽/2 和高/2)。然后我们将通过交换和交换各自的值来增加球的速度。由于 X 和 Y 方向都在变化，球将沿对角线方向移动，其进一步的路径将取决于碰撞体。

```py
# importing the module
import random

# declaring variables for the ball
ball_X = width/2 - 12
ball_Y = height/2 - 12
ball_XChange = 3* random.choice((1, -1))
ball_YChange = 3
ballPixel = 24
```

**3。**现在我们开始基本的游戏运行循环。我们也给我们的屏幕一个背景色。

```py
# gaming Loop
running = True
while running:

    # background color
    screen.fill(red)

    # to exit the loop
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
```

**4。**我们游戏的主要部分来了。我们提供了一个条件，如果球的 X 位置大于屏幕的宽度或小于 0(即，如果球在屏幕的右端或左端碰撞或到来)，那么我们将 X 方向速度乘以负 1。意思是方向反了。如果球是以 3 像素的速度来的，那么在碰撞左墙或右墙时，它的速度将是-3 像素，即反向，当它再次撞击墙壁时，它的速度将是正 3，即反向-3。因此，这将给球一个边界。

同样，同样的逻辑也将适用于上墙和下墙。

如果球的 Y 值大于屏幕高度或小于 0，则反转其方向。
然后我们通过分别用 XChange 和 YChange 增加球的位置来移动球。

(下面的代码在游戏循环下)

```py
# inside the gaming Loop

    # bouncing the ball
    if ball_X + ballPixel >= width or ball_X <= 0:
        ball_XChange *= -1
    if ball_Y + ballPixel >= height or ball_Y <= 0:
        ball_YChange *= -1

    # moving the ball
    ball_X += ball_XChange
    ball_Y += ball_YChange
```

**5。**现在，我们将在 while 循环中绘制球，以便在每个循环中显示它。我们在 BalX 和 BalY 位置画圆，这样球的 X 和 Y 位置在每个循环中递增，球将在每个循环中的下一个位置画出，因此球将在屏幕内移动。最后我们更新屏幕。

```py
# inside the gaming Loop

    # drawing the ball
    ballImg = pygame.draw.circle(screen, (0,0,255),
                                 (int(ball_X), int(ball_Y)),
                                 15)
    pygame.display.update()
```

这就是我们如何在 PyGame 中为对象添加边界。

完整的代码如下:

```py
# importing the modules
import pygame
import random

# instantiating the class
pygame.init()

# dimension of the screen
width = 700
height = 550

# colours
white = (255, 255, 255)
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
black = (0, 0, 0)

# creating a Screen
screen = pygame.display.set_mode((width, height))

# title of the screen
pygame.display.set_caption("Bouncy Ball")

# declaring variables for the ball
ball_X = width/2 - 12
ball_Y = height/2 - 12
ball_XChange = 3* random.choice((1, -1))
ball_YChange = 3
ballPixel = 24

# gaming Loop
running = True
while running:

    # background color
    screen.fill(red)

    # to exit the loop
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # bouncing the ball
    if ball_X + ballPixel >= width or ball_X <= 0:
        ball_XChange *= -1
    if ball_Y + ballPixel >= height or ball_Y <= 0:
        ball_YChange *= -1

    # moving the ball
    ball_X += ball_XChange
    ball_Y += ball_YChange

    # drawing the ball
    ballImg = pygame.draw.circle(screen, (0,0,255),
                                 (int(ball_X), int(ball_Y)),
                                 15)
    pygame.display.update()
```

**输出:**

<video class="wp-video-shortcode" id="video-454943-1" width="665" height="547" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200718103322/PyGame-boundary.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200718103322/PyGame-boundary.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200718103322/PyGame-boundary.mp4)</video>