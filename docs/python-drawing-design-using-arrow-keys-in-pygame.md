# Python–在 PyGame 中使用箭头键进行绘图设计

> 原文:[https://www . geesforgeks . org/python-drawing-design-use-箭头键-in-pygame/](https://www.geeksforgeeks.org/python-drawing-design-using-arrow-keys-in-pygame/)

Pygame 是一套跨平台的 Python 模块，设计用于编写视频游戏。它包括设计用于 Python 编程语言的计算机图形和声音库。现在，这取决于开发者的想象力或必要性，他/她想使用这个工具包开发什么类型的游戏。

在本文中，我们将看到如何在 PyGame 中借助按键进行设计，即当按下键盘上的右箭头键或左箭头键时，标记水平移动，而当按下上箭头键或下箭头键时，标记垂直移动。我们可以通过在各自的坐标上做一个点(标记)来做到这一点，这可以在按键的帮助下得到改变。

```
Change in Co-ordinates of marker for respective keys pressed :

Left arrow key: Decrement in x co-ordinate
Right arrow key: Increment in x co-ordinate
Up arrow key: Decrement in y co-ordinate
Down arrow key: Increment in y co-ordinate

```

以下是实施–

```
# import pygame module in this program
import pygame

# activate the pygame library .   
# initiate pygame and give permission   
# to use pygame's functionality.   
pygame.init()

# create the display surface object   
# of specific dimension..e(500, 500).   
win = pygame.display.set_mode((500, 500))

# set the pygame window name  
pygame.display.set_caption("Moving rectangle")

# marker current co-ordinates  
x = 200
y = 200

# dimensions of the marker 
width = 10
height = 10

# velocity / speed of movement 
vel = 10

# Indicates pygame is running 
run = True

# infinite loop  
while run:
    # creates time delay of 10ms  
    pygame.time.delay(10)

    # iterate over the list of Event objects   
    # that was returned by pygame.event.get() method.   
    for event in pygame.event.get():

        # if event object type is QUIT   
        # then quitting the pygame   
        # and program both.   
        if event.type == pygame.QUIT:
            # it will make exit the while loop
            run = False
    # stores keys pressed  
    keys = pygame.key.get_pressed()

    # if left arrow key is pressed 
    if keys[pygame.K_LEFT] and x > 0:
        # decrement in x co-ordinate
        x -= vel

        # if left arrow key is pressed
    if keys[pygame.K_RIGHT] and x < 500 - width:
        # increment in x co-ordinate
        x += vel

        # if left arrow key is pressed
    if keys[pygame.K_UP] and y > 0:
        # decrement in y co-ordinate
        y -= vel

        # if left arrow key is pressed
    if keys[pygame.K_DOWN] and y < 500 - height:
        # increment in y co-ordinate 
        y += vel

    # drawing spot on screen which is rectangle here  
    pygame.draw.rect(win, (255, 0, 0), (x, y, width, height))

    # it refreshes the window 
    pygame.display.update()

# closes the pygame window  
pygame.quit() 
```

**输出:**

<video class="wp-video-shortcode" id="video-396953-1" width="640" height="640" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200329025606/Design-maker-29-03-2020-02_55_22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200329025606/Design-maker-29-03-2020-02_55_22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200329025606/Design-maker-29-03-2020-02_55_22.mp4)</video>