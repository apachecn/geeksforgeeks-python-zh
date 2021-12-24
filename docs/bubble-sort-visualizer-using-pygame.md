# 使用 PyGame 的气泡分类可视化工具

> 原文:[https://www . geesforgeks . org/bubble-sort-visualizer-using-pygame/](https://www.geeksforgeeks.org/bubble-sort-visualizer-using-pygame/)

在本文中，我们将看到如何使用 pygame 可视化[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)算法，即当 PyGame 应用程序启动时，我们可以看到不同高度的未排序条，当我们单击空格键时，它开始以冒泡排序方式排列，即每次迭代后，最大值元素应该最终出现。

**冒泡排序**是一种简单的算法，用于对以具有 n 个元素的数组的形式提供的 n 个元素的给定集合进行排序。冒泡排序逐个比较所有元素，并根据它们的值对它们进行排序。

> 实施步骤:
> 
> 1.创建主窗口
> 2。用黑色填充主窗口
> 3。创建一个方法来显示它们之间有特定间隙的酒吧列表
> 4。获取用户输入的按键
> 5。如果按下空格键，开始排序过程
> 6。对列表实施冒泡排序算法
> 7。每次内部迭代后，用黑色填充屏幕，并调用 show 方法以条形图的形式显示迭代列表。

下面是实现

```
# importing pygame
import pygame

pygame.init()

# setting window size
win = pygame.display.set_mode((500, 400))

# setting title to the window
pygame.display.set_caption("Bubble sort")

# initial position
x = 40
y = 40

# width of each bar
width = 20

# height of each bar (data to be sorted)
height = [200, 50, 130, 90, 250, 61, 110,
            88, 33, 80, 70, 159, 180, 20]

run = True

# method to show the list of height
def show(height):

    # loop to iterate each item of list
    for i in range(len(height)):

        # drawing each bar with respective gap
        pygame.draw.rect(win, (255, 0, 0), (x + 30 * i, y, width, height[i]))

# infinite loop
while run:

    # execute flag to start sorting
    execute = False

    # time delay
    pygame.time.delay(10)

    # getting keys pressed
    keys = pygame.key.get_pressed()

    # iterating events
    for event in pygame.event.get():

        # if event is to quit
        if event.type == pygame.QUIT:

            # making run = false so break the while loop
            run = False

    # if space bar is pressed
    if keys[pygame.K_SPACE]:
        # make execute flag to true
        execute = True

    # checking if execute flag is false
    if execute == False:

        # fill the window with black color
        win.fill((0, 0, 0))

        # call the height method to show the list items
        show(height)

        # update the window
        pygame.display.update()

    # if execute flag is true
    else:

        # start sorting using bubble sort technique
        for i in range(len(height) - 1):

            # after this iteration max element will come at last
            for j in range(len(height) - i - 1):

                # starting is greater then next element
                if height[j] > height[j + 1]:

                    # save it in temporary variable
                    # and swap them using temporary variable
                    t = height[j]
                    height[j] = height[j + 1]
                    height[j + 1] = t

                # fill the window with black color
                win.fill((0, 0, 0))

                # call show method to display the list items
                show(height)

                # create a time delay
                pygame.time.delay(50)

                # update the display
                pygame.display.update()

# exiting the main window
pygame.quit()
```

**输出:**

<video class="wp-video-shortcode" id="video-400000-1" width="640" height="512" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200419005933/Bubble-sort-19-04-2020-00_07_00.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200419005933/Bubble-sort-19-04-2020-00_07_00.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200419005933/Bubble-sort-19-04-2020-00_07_00.mp4)</video>