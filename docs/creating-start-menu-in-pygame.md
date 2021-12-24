# 在 Pygame 中创建开始菜单

> 原文:[https://www . geesforgeks . org/creating-start-menu-in-pygame/](https://www.geeksforgeeks.org/creating-start-menu-in-pygame/)

[**Pygame**](https://www.geeksforgeeks.org/introduction-to-pygame/) 是一个 Python 库，可以专门用来设计和构建游戏。Pygame 仅支持使用不同形状或精灵构建的 2d 游戏。Pygame 没有内置的布局设计或任何内置的 UI 系统，这意味着没有简单的方法来为游戏制作 UI 或关卡。在 pygame 中制作关卡或不同菜单的唯一方法是使用函数。

## **使用功能作为菜单**

**Pygame 中的函数**是一种通过在每个函数中定义一个事件类型，然后从各自的容器函数中调用函数来包含不同菜单或级别的方式。

例如，如果玩家点击开始菜单上的播放按钮，游戏功能将被调用。因此，开始菜单功能成为游戏功能的容器功能。需要注意的重要一点是，启动函数不能直接从游戏函数中调用。如果游戏包含不同的可解锁等级，那么上一级就成为下一级的容器函数。

**包含开始菜单的游戏示例代码**

演示菜单和级别的 Python 程序

## 计算机编程语言

```py
import pygame 
import sys 

# initializing the constructor 
pygame.init() 

# screen resolution 
res = (720,720) 

# opens up a window 
screen = pygame.display.set_mode(res) 

# white color 
color = (255,255,255) 

# light shade of the button 
color_light = (170,170,170) 

# dark shade of the button 
color_dark = (100,100,100) 

# stores the width of the 
# screen into a variable 
width = screen.get_width() 

# stores the height of the 
# screen into a variable 
height = screen.get_height() 

# defining a font 
smallfont = pygame.font.SysFont('Corbel',35) 

# rendering a text written in 
# this font 
text = smallfont.render('quit' , True , color) 

while True: 

    for ev in pygame.event.get(): 

        if ev.type == pygame.QUIT: 
            pygame.quit() 

        #checks if a mouse is clicked 
        if ev.type == pygame.MOUSEBUTTONDOWN: 

            #if the mouse is clicked on the 
            # button the game is terminated 
            if width/2 <= mouse[0] <= width/2+140 and height/2 <= mouse[1] <= height/2+40: 
                pygame.quit() 

    # fills the screen with a color 
    screen.fill((60,25,60)) 

    # stores the (x,y) coordinates into 
    # the variable as a tuple 
    mouse = pygame.mouse.get_pos() 

    # if mouse is hovered on a button it 
    # changes to lighter shade 
    if width/2 <= mouse[0] <= width/2+140 and height/2 <= mouse[1] <= height/2+40: 
        pygame.draw.rect(screen,color_light,[width/2,height/2,140,40]) 

    else: 
        pygame.draw.rect(screen,color_dark,[width/2,height/2,140,40]) 

    # superimposing the text onto our button 
    screen.blit(text , (width/2+50,height/2)) 

    # updates the frames of the game 
    pygame.display.update() 
```

**输出:**

<video class="wp-video-shortcode" id="video-475638-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825140241/pygame-window-2020-08-25-13-58-26_770T9JQ7.compressed.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200825140241/pygame-window-2020-08-25-13-58-26_770T9JQ7.compressed.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825140241/pygame-window-2020-08-25-13-58-26_770T9JQ7.compressed.mp4)</video>