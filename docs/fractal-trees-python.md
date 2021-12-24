# Python 中的分形树

> 原文:[https://www.geeksforgeeks.org/fractal-trees-python/](https://www.geeksforgeeks.org/fractal-trees-python/)

分形二叉树的 python 实现。

**简介**分形树被称为可以递归对称分支创建的树。

长度为 1 的主干分成长度为 r 的两个分支，每个分支与主干的方向成一个角度 q。这两个分支都分成两个长度为 r*r 的分支，每个分支都与其父分支的方向成一个角度 q。以这种方式继续无限多的分支，树是一组分支，连同它们的极限点，称为分支尖端。

理论已经讲够了，现在让我们尝试用 Python 实现。为此，我们需要两个 python 库 **pygame** 用于 GUI 或图形用户界面，以及**数学**，这是 python 中的内置库，将用于数学调整。

要安装 pygame

```py
pip install pygame
```

那么如何进行呢，强烈建议你对 pygame 和分形有所了解。

首先创建一个主干，然后开始为每个主干创建分支，取大小等于 0.9*(主干长度)的分支大小，然后再次将分支视为主干，如此重复该过程。

```py
# Importing the python libraries
import pygame, math

# Initialize all imported pygame modules
pygame.init()

# Create a new surface and window.
surface_height, surface_width = 800, 600        #Surface variables
main_surface = pygame.display.set_mode((surface_height,surface_width))

# Captioning the window
pygame.display.set_caption("Fractal_Tree_geeksforgeeks")

def draw_tree(order, theta, sz, posn, heading, color=(0,0,0), depth=0):

   # The relative ratio of the trunk to the whole tree  
   trunk_ratio = 0.29     

   # Length of the trunk  
   trunk = sz * trunk_ratio
   delta_x = trunk * math.cos(heading)
   delta_y = trunk * math.sin(heading)
   (u, v) = posn
   newpos = (u + delta_x, v + delta_y)
   pygame.draw.line(main_surface, color, posn, newpos)

   if order > 0:   # Draw another layer of subtrees

      # These next six lines are a simple hack to make 
      # the two major halves of the recursion different 
      # colors. Fiddle here to change colors at other 
      # depths, or when depth is even, or odd, etc.
      if depth == 0:
          color1 = (255, 0, 0)
          color2 = (0, 0, 255)
      else:
          color1 = color
          color2 = color

      # make the recursive calls to draw the two subtrees
      newsz = sz*(1 - trunk_ratio)
      draw_tree(order-1, theta, newsz, newpos, heading-theta, color1, depth+1)
      draw_tree(order-1, theta, newsz, newpos, heading+theta, color2, depth+1)

def main():
    theta = 0

    while True:

        # Update the angle
        theta += 0.01

        # This little part lets us draw the stuffs 
        # in the screen everything
        main_surface.fill((255, 255, 0))
        draw_tree(9, theta, surface_height*0.9, (surface_width//2, surface_width-50), -math.pi/2)
        pygame.display.flip()

# Calling the main function
main()
pygame.quit()
```

输出:

```py

<video class="wp-video-shortcode" id="video-167844-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2017-12-18-at-18-40-42.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/2017-12-18-at-18-40-42.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2017-12-18-at-18-40-42.mp4)</video>

```