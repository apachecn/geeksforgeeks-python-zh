# 如何在 Pygame 中制作 Flappy 小鸟游戏？

> 原文:[https://www . geesforgeks . org/how-to-make-flappy-bird-game in-pygame/](https://www.geeksforgeeks.org/how-to-make-flappy-bird-game-in-pygame/)

在本文中，我们将看到如何在 Pygame 中制作一个 flappy 鸟游戏。

我们都熟悉这个游戏。在这个游戏中，玩家的主要目标是通过防御障碍获得最大分数。在这里，我们将使用 Python 构建我们自己的 Flappy Bird 游戏。

我们将使用 Pygame(一个 Python 库)来创建这个 Flappy Bird 游戏。 **Pygame** 是一个为制作视频游戏而设计的开源库。它帮助我们用 python 创建功能齐全的游戏和多媒体程序。

首先，您必须使用以下命令安装 Pygame 库:-

```py
pip install pygame
```

## 逐步实施

**第一步:**在第一步中，我们要导入库。

之后，我们必须设置游戏将被播放到的屏幕的高度和宽度。现在，我们必须定义一些图像，我们将在我们的游戏中使用，如管道作为障碍，鸟类图像，以及一个背景图像的飞禽游戏。

## 蟒 3

```py
# For generating random height of pipes
import random  
import sys 
import pygame
from pygame.locals import * 

# Global Variables for the game
window_width = 600
window_height = 499

# set height and width of window
window = pygame.display.set_mode((window_width, window_height))   
elevation = window_height * 0.8
game_images = {}      
framepersecond = 32
pipeimage = 'images/pipe.png'
background_image = 'images/background.jpg'
birdplayer_image = '/images/bird.png'
sealevel_image = '/images/base.jfif'
```

**第二步:**在声明游戏变量和导入库之后，我们必须初始化 Pygame

使用过的文件可以从[这里下载。](https://drive.google.com/drive/folders/1slswL541szNDXfaptHRHp4_XzSxBabHO?usp=sharing)

使用 **pygame.init()** 初始化程序，设置窗口标题。这里 pygame.time.Clock()将在游戏的主循环中进一步使用，以改变鸟的速度。使用 pygame.image.load()在 pygame 中从系统加载图像。

## 蟒 3

```py
# program where the game starts
if __name__ == "__main__":          

    # For initializing modules of pygame library
    pygame.init()  
    framepersecond_clock = pygame.time.Clock()

    # Sets the title on top of game window
    pygame.display.set_caption('Flappy Bird Game')      

    # Load all the images which we will use in the game
    # images for displaying score
    game_images['scoreimages'] = (
        pygame.image.load('images/0.png').convert_alpha(),
        pygame.image.load('images/1.png').convert_alpha(),
        pygame.image.load('images/2.png').convert_alpha(),
        pygame.image.load('images/3.png').convert_alpha(),
        pygame.image.load('images/4.png').convert_alpha(),        
        pygame.image.load('images/5.png').convert_alpha(),
        pygame.image.load('images/6.png').convert_alpha(),
        pygame.image.load('images/7.png').convert_alpha(),
        pygame.image.load('images/8.png').convert_alpha(),
        pygame.image.load('images/9.png').convert_alpha()
    )
    game_images['flappybird'] = pygame.image.load(birdplayer_image).convert_alpha()                  
    game_images['sea_level'] = pygame.image.load(sealevel_image).convert_alpha()
    game_images['background'] = pygame.image.load(background_image).convert_alpha()
    game_images['pipeimage'] = (pygame.transform.rotate(pygame.image.load(pipeimage)
                                                        .convert_alpha(),
                                                        180),
                                pygame.image.load(pipeimage).convert_alpha())

    print("WELCOME TO THE FLAPPY BIRD GAME")
    print("Press space or enter to start the game")
```