# 使用 pygame 的 8 位游戏

> 原文:[https://www.geeksforgeeks.org/8-bit-game-using-pygame/](https://www.geeksforgeeks.org/8-bit-game-using-pygame/)

Pygame 是一个 python 库，可以专门用来设计和构建游戏。Pygame 只支持使用不同精灵构建的 2d 游戏。Pygame 并不特别适合设计游戏，因为它使用起来非常复杂，没有像 unity 这样合适的图形用户界面，但它无疑为更复杂的项目构建了逻辑。
我们将用以下规则创建一个简单的游戏:-

*   玩家只能垂直移动。

*   除了玩家区，还有两个其他区。

*   其中一个将是敌人街区，其中一个将是得分街区。

*   如果玩家与敌方方块相撞，那么游戏结束画面会弹出，如果玩家与分数方块相撞，分数会增加，并且必须收集所有分数方块。

我们将使用各种技术，如函数、随机变量、各种 pygame 函数等的使用。

#### 装置

在初始化 pygame 库之前，我们需要安装它。要安装它，请在终端中键入以下命令。

```py
pip install pygame
```

在安装完 pygame 库之后，我们需要编写以下几行来初始化 pygame 库:-

```py
import pygame
pygame.init()
```

这些台词很容易理解。pygame.init()函数启动 pygame 库。
然后我们需要初始化我们想要放置区块的屏幕。这可以通过写下面几行来完成:-

```py
res = (720, 720)
screen = pygame.display.set_mode(res)
```

元组 res 包含两个定义游戏分辨率的值。然后，我们需要定义另一个变量屏幕，它实际上将充当我们的工作台。这可以通过使用 pygame.display.set_mode((arg，arg))来完成。元组(arg，arg)可以存储到变量 res 中，以减少处理器负载。
现在我们需要一个实际的屏幕来弹出，当我们运行代码时，这可以通过一个 for 和 while 循环来完成，方式如下:-

```py
while True:
for ev in pygame.event.get():
if ev.type==pygame.QUIT:
pygame.quit()
```

这里使用的 while 循环一直运行到条件为真。我们在 pygame.event 中定义了一个变量 ev。现在，如果用户点击窗口的十字按钮，条件将变为 false，while 循环结束，杀死当前窗口。
下面是实现。

## 蟒蛇 3

```py
# Python program to demonstrate
# 8 bit game

import pygame
import sys
import random

# initialize the constructor
pygame.init()
res = (720, 720)

# randomly assigns a value to variables
# ranging from lower limit to upper
c1 = random.randint(125, 255) 
c2 = random.randint(0, 255)
c3 = random.randint(0, 255)

screen = pygame.display.set_mode(res)
clock = pygame.time.Clock()
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)
color_list = [red, green, blue]
colox_c1 = 0
colox_c2 = 0
colox_c3 = 254
colox_c4 = 254

# randomly assigns a colour from color_list
# to player
player_c = random.choice(color_list)

# light shade of menu buttons
startl = (169, 169, 169) 

# dark shade of menu buttons
startd = (100, 100, 100) 
white = (255, 255, 255)
start = (255, 255, 255)
width = screen.get_width()
height = screen.get_height()

# initial X position of player
lead_x = 40

# initial y position of player
lead_y = height / 2
x = 300
y = 290
width1 = 100
height1 = 40
enemy_size = 50

# defining a font
smallfont = pygame.font.SysFont('Corbel', 35)

# texts to be rendered on screen
text = smallfont.render('Start', True, white)
text1 = smallfont.render('Options', True, white)
exit1 = smallfont.render('Exit', True, white)

# game title
colox = smallfont.render('Colox', True, (c3, c2, c1)) 
x1 = random.randint(width / 2, width)
y1 = random.randint(100, height / 2)
x2 = 40
y2 = 40
speed = 15

# score of the player
count = 0 
rgb = random.choice(color_list)

# enemy position
e_p = [width, random.randint(50, height - 50)] 
e1_p = [random.randint(width, width + 100), random.randint(50, height
        - 100)]

# function for game_over
def game_over():

    while True:

        # if the player clicks the cross
        # button
        for ev in pygame.event.get():
            if ev.type == pygame.QUIT:
                pygame.quit()

            if ev.type == pygame.MOUSEBUTTONDOWN:
                if 100 < mouse1[0] < 140 and height - 100 < mouse1[1] \
                    < height - 80:
                    pygame.quit()

                if ev.type == pygame.MOUSEBUTTONDOWN:
                    if width - 180 < mouse1[0] < width - 100 and height \
                        - 100 < mouse1[1] < height - 80:

                        # calling function game
                        game(lead_x, lead_y, speed, count) 

        # fills the screen with specified colour
        screen.fill((65, 25, 64)) 
        smallfont = pygame.font.SysFont('Corbel', 60)
        smallfont1 = pygame.font.SysFont('Corbel', 25)
        game_over = smallfont.render('GAME OVER', True, white)
        game_exit = smallfont1.render('exit', True, white)
        restart = smallfont1.render('restart', True, white)
        mouse1 = pygame.mouse.get_pos()

        # exit
        if 100 < mouse1[0] < 140 and height - 100 < mouse1[1] < height - 80:
            pygame.draw.rect(screen, startl, [100, height - 100, 40,20])
        else:
            pygame.draw.rect(screen, startd, [100, height - 100, 40,20])

        # restart
        if width - 180 < mouse1[0] < width - 100 and height - 100 < mouse1[1] < height - 80:
            pygame.draw.rect(screen, startl, [width - 180, height- 100, 80, 20])
        else:
            pygame.draw.rect(screen, startd, [width - 180, height- 100, 80, 20])

        screen.blit(game_exit, (100, height - 100))

        # superimposes one object on other
        screen.blit(restart, (width - 180, height - 100)) 
        screen.blit(game_over, (width / 2 - 150, 295))

        # updates frames of the game
        pygame.display.update()

pygame.draw.rect(screen, startd, [100, height - 100, 40, 20])
pygame.draw.rect(screen, startd, [width - 180, height - 100, 40, 50])

# function for body of the game
def game(
    lead_y,
    lead_X,
    speed,
    count,
    ):

    while True:
        for ev in pygame.event.get():
            if ev.type == pygame.QUIT:
                pygame.quit()

        # player control
        # keeps track of the key pressed
        keys = pygame.key.get_pressed() 
        if keys[pygame.K_UP]:

            # if up key is pressed then the players
            # y pos will decrement by 10
            lead_y -= 10 
        if keys[pygame.K_DOWN]:

            # if down key is pressed then the y pos
            # of the player is incremented by 10
            lead_y += 10 
        screen.fill((65, 25, 64))
        clock.tick(speed)

        # draws a rectangle on the screen
        rect = pygame.draw.rect(screen, player_c, [lead_x, lead_y, 40,40]) 
        pygame.draw.rect(screen, (c1, c2, c3), [0, 0, width, 40])
        pygame.draw.rect(screen, (c3, c2, c1), [0, 680, width, 40])
        pygame.draw.rect(screen, startd, [width - 100, 0, 100, 40])
        smallfont = pygame.font.SysFont('Corbel', 35)
        exit2 = smallfont.render('Exit', True, white)

        # exit
        # gets the X and y position of mouse
        # pointer and stores them as a tuple
        mouse = pygame.mouse.get_pos() 
        if width - 100 < mouse[0] < width and 0 < mouse[1] < 40:
            pygame.draw.rect(screen, startl, [width - 100, 0, 100, 40])
        else:
            pygame.draw.rect(screen, startd, [width - 100, 0, 100, 40])
        if width - 100 < mouse[0] < width and 0 < mouse[1] < 40:
            if ev.type == pygame.MOUSEBUTTONDOWN:
                pygame.quit()

        # enemy position
        if e_p[0] > 0 and e_p[0] <= width:

            # if the enemy block's X coordinate is between 0 and
            # the width of the screen the X value gets
            # decremented by 10
            e_p[0] -= 10 
        else:
            if e_p[1] <= 40 or e_p[1] >= height - 40:
                e_p[1] = height / 2
            if e1_p[1] <= 40 or e1_p[1] >= height - 40:
                e1_p[1] = random.randint(40, height - 40)
            e_p[1] = random.randint(enemy_size, height - enemy_size)
            e_p[0] = width

        # game over
        # collision detection
        if lead_x <= e_p[0] <= lead_x + 40 and lead_y >= e_p[1] >= lead_y - 40:
            game_over() 

        # checks if the player block has collided with the enemy block
        if lead_y <= e_p[1] + enemy_size <= lead_y + 40 and lead_x <= e_p[0] <= lead_x + 40:
            game_over()

        pygame.draw.rect(screen, red, [e_p[0], e_p[1], enemy_size,enemy_size])
        if e1_p[0] > 0 and e1_p[0] <= width + 100:
            e1_p[0] -= 10
        else:
            if e1_p[1] <= 40 or e1_p[1] >= height - 40:
                e1_p[1] = height / 2
            e1_p[1] = random.randint(enemy_size, height - 40)
            e1_p[0] = width + 100

        if lead_x <= e1_p[0] <= lead_x + 40 and lead_y >= e1_p[1] >= lead_y - 40:
            e1_p[0] = width + 100
            e1_p[1] = random.randint(40, height - 40)
            count += 1
            speed += 1
        if lead_y <= e1_p[1] + enemy_size <= lead_y + 40 and lead_x <= e1_p[0] <= lead_x + 40:
            e1_p[0] = width + 100
            e1_p[1] = random.randint(40, height - 40)

            # increases the score when blue box is hit
            count += 1 

            # increases the speed as score increases
            speed += 1 

            if count >= 45:

                # freezes the game FPS to 60 if
                # score reaches 45 or more
                speed = 60 

        if lead_y <= 38 or lead_y >= height - 38:
            game_over()
        if e1_p[0] <= 0:
            game_over()

        pygame.draw.rect(screen, blue, [e1_p[0], e1_p[1], enemy_size,
                         enemy_size])
        score1 = smallfont.render('Score:', True, white)
        screen.blit(score1, (width - 120, height - 40))
        screen.blit(exit2, (width - 80, 0))
        pygame.display.update()

# intro
def intro(
    colox_c1,
    colox_c2,
    colox,
    exit1,
    text1,
    text,
    ):
    intro = True
    while intro:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
        screen.fill((65, 25, 64))
        mouse = pygame.mouse.get_pos()

        # start screen
        if x < mouse[0] < x + width1 and y < mouse[1] < y + height1:

            # if mouse is hovered on a button
            # its colour shade becomes lighter
            pygame.draw.rect(screen, startl, [x, y, width1, height1]) 
        else:
            if x < mouse[0] < x + width1 + 40 and y + 70 < mouse[1] < y \
                + 70 + height1:
                pygame.draw.rect(screen, startl, [x, y + 70, width1+40,height1])
            else:

                if x < mouse[0] < width1 + x and y + 140 < mouse[1] < y + 140 + height1:
                    pygame.draw.rect(screen, startl, [x, y + 140,width1,height1])
                else:
                    pygame.draw.rect(screen, startd, [x, y, width1,height1])
                    pygame.draw.rect(screen, startd, [x, y + 70, width1
                            + 40, height1])
                    pygame.draw.rect(screen, startd, [x, y + 140,width1, height1])

        # start button
        if event.type == pygame.MOUSEBUTTONDOWN:
            if x < mouse[0] < x + width1 and y < mouse[1] < y + height1:
                #music()
                game(lead_y, lead_x, speed, count)

        if event.type == pygame.MOUSEBUTTONDOWN:
            if x < mouse[0] < width1 + x and y + 140 < mouse[1] < y + 140 + height1:
                pygame.quit()

        # this handles the colour breezing effect
        if 0 <= colox_c1 <= 254 or 0 <= colox_c2 <= 254:
            colox_c1 += 1
            colox_c2 += 1
        if colox_c1 >= 254 or colox_c2 >= 254:
            colox_c1 = c3
            colox_c2 = c3

        pygame.draw.rect(screen, (c2, colox_c1, colox_c2), [0, 0, 40,
                         height])
        pygame.draw.rect(screen, (c2, colox_c1, colox_c2), [width - 40,
                         0, 40, height])
        smallfont = pygame.font.SysFont('Corbel', 35)
        sig = smallfont.render('Designed by :- Antriksh', True, white)
        text = smallfont.render('Start', True, white)
        text1 = smallfont.render('Options', True, white)
        exit1 = smallfont.render('Exit', True, white)
        colox = smallfont.render('Colox', True, (c1, colox_c1,
                                 colox_c2))
        screen.blit(colox, (312, 50))
        screen.blit(text, (312, 295))
        screen.blit(text1, (312, 365))
        screen.blit(exit1, (312, 435))
        screen.blit(sig, (320, height - 50))
        clock.tick(60)
        pygame.display.update()

intro(
    colox_c1,
    colox_c2,
    colox,
    exit1,
    text1,
    text,
    )
```

**输出:**

<video class="wp-video-shortcode" id="video-373599-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200117123314/media.io_Screencast-from-Friday-17-January-2020-12_27_00-IST.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200117123314/media.io_Screencast-from-Friday-17-January-2020-12_27_00-IST.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200117123314/media.io_Screencast-from-Friday-17-January-2020-12_27_00-IST.mp4)</video>