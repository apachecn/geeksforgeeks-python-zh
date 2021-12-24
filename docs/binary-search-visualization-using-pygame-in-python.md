# 使用 Python 中 Pygame 的二分搜索法可视化

> 原文:[https://www . geesforgeks . org/binary-search-visualization-use-pygame-in-python/](https://www.geeksforgeeks.org/binary-search-visualization-using-pygame-in-python/)

像[二分搜索法](https://www.geeksforgeeks.org/binary-search/)这样的算法通过可视化很容易理解。本文实现了一个可视化二分搜索法算法的程序。[图形用户界面](https://www.geeksforgeeks.org/difference-between-cli-and-gui/)使用 [pygame](https://www.geeksforgeeks.org/introduction-to-pygame/) 库在 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中实现。

### 方法

生成随机数组，使用任何排序算法对其进行排序，并用条填充 pygame 窗口。条形是垂直的直线，代表数组元素。

*   将所有条形设置为绿色。
*   使用 pygame.time.delay()来降低算法的速度，这样我们就可以看到搜索过程。
*   实现一个计时器，看看算法如何执行。
*   这些操作是使用“pygame.event.get()”方法执行的，该方法存储用户执行的所有事件，如启动、重置。
*   蓝色用于高亮显示与找到的键相等的条。
*   橙色突出显示左右条。

下面是上述可视化工具的实现:

## 计算机编程语言

```py
# Python implementation of the
# Sorting visualiser: Insertion Sort

# Imports
import pygame
import random
import time

pygame.font.init()
startTime = time.time()

# Total window
screen = pygame.display.set_mode(
    (900, 650)
)

# Title and Icon
pygame.display.set_caption(
    "BINARY SEARCH VISUALISER"
)

# Uncomment below lines for setting
# up the icon for the visuliser
# img = pygame.image.load('sorticon.png')
# pygame.display.set_icon(img)

# Boolean variable to run
# the program in while loop
run = True

# Window size and some initials
width = 900
length = 600
array = [0]*151
key = 0
foundkey = False

arr_clr = [(0, 204, 102)]*151
clr_ind = 0

clr = [(0, 204, 102), (255, 0, 0),
       (0, 0, 153), (255, 102, 0)]

bigfont = pygame.font.SysFont("comicsans", 70)
fnt = pygame.font.SysFont("comicsans", 30)
fnt1 = pygame.font.SysFont("comicsans", 20)

# Sorting Algorithm: Heap Sort
def heapSort(array):
    n = len(array)

    for i in range(n//2-1, -1, -1):
        heapify(array, i, n)

    for i in range(n-1, 0, -1):
        array[i], array[0] = array[0], array[i]
        heapify(array, 0, i)

def heapify(array, root, size):
    left = root*2+1
    right = root*2+2
    largest = root

    if left < size and array[left] > array[largest]:
        largest = left

    if right < size and array[right] > array[largest]:
        largest = right

    if largest != root:
        array[largest], array[root] = array[root], array[largest]
        heapify(array, largest, size)

# Function to generate new Array

def generate_arr():
    for i in range(1, 151):
        arr_clr[i] = clr[0]
        array[i] = random.randrange(1, 100)
    heapSort(array)

# Initially generate a array
generate_arr()

# Function to refill the
# updates on the window
def refill():
    screen.fill((255, 255, 255))
    draw()
    pygame.display.update()
    pygame.time.delay(200)

def binarySearch(array, key):
    left = 0
    right = len(array)-1

    while left < right:
        arr_clr[left] = clr[1]
        arr_clr[right] = clr[1]
        refill()
        refill()
        mid = left+(right-left)//2

        if array[mid] == key:
            arr_clr[left] = clr[0]
            arr_clr[right] = clr[0]
            arr_clr[mid] = clr[2]
            return 1

        elif array[mid] < key:
            arr_clr[left] = clr[0]
            left = mid+1

        else:
            arr_clr[right] = clr[0]
            right = mid-1
        refill()
    arr_clr[left] = clr[0]
    arr_clr[right] = clr[0]
    refill()
    return -1

# Function to Draw the array values
def draw():

    # Text should be rendered
    txt = fnt.render("SEARCH: PRESS 'ENTER'",
                     1, (0, 0, 0))

    # Position where text is placed
    screen.blit(txt, (20, 20))
    txt1 = fnt.render("NEW ARRAY: PRESS 'R'",
                      1, (0, 0, 0))
    screen.blit(txt1, (20, 40))
    txt2 = fnt1.render("ENTER NUMBER TO SEARCH:" +
                       str(key), 1, (0, 0, 0))
    screen.blit(txt2, (600, 60))
    text3 = fnt1.render("Running Time(sec): " +
                        str(int(time.time() - startTime)),
                        1, (0, 0, 0))
    screen.blit(text3, (600, 20))
    element_width = (width-150)//150
    boundry_arr = 900 / 150
    boundry_grp = 550 / 100
    pygame.draw.line(screen, (0, 0, 0), (0, 95),
                     (900, 95), 6)

    # Drawing the array values as lines
    for i in range(1, 151):
        pygame.draw.line(screen, arr_clr[i],
                         (boundry_arr * i-3, 100),
                         (boundry_arr * i-3,
                          array[i]*boundry_grp + 100), element_width)
    if foundkey == 1:
        text4 = bigfont.render("Key Found. Press N to Reset Key", 1, (0, 0, 0))
        screen.blit(text4, (100, 300))

    elif foundkey == -1:
        text4 = bigfont.render(
            "Key Not Found. Press N to Reset Key", 1, (0, 0, 0))
        screen.blit(text4, (30, 300))

# Program should be run
# continuously to keep the window open
while run:

    # background
    screen.fill((255, 255, 255))

    # Event handler stores all event
    for event in pygame.event.get():

        # If we click Close button in window
        if event.type == pygame.QUIT:
            run = False

        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_r:
                key = 0
                foundkey = 0
                generate_arr()
            if event.key == pygame.K_n:
                foundkey = 0
                key = 0
                for i in range(0, len(array)):
                    arr_clr[i] = clr[0]
            if event.key == pygame.K_RETURN and key != 0:
                foundkey = binarySearch(array, key)
            if event.key == pygame.K_0:
                key = key*10
            if event.key == pygame.K_1:
                key = key*10+1
            if event.key == pygame.K_2:
                key = key*10+2
            if event.key == pygame.K_3:
                key = key*10+3
            if event.key == pygame.K_4:
                key = key*10+4
            if event.key == pygame.K_5:
                key = key*10+5
            if event.key == pygame.K_6:
                key = key*10+6
            if event.key == pygame.K_7:
                key = key*10+7
            if event.key == pygame.K_8:
                key = key*10+8
            if event.key == pygame.K_9:
                key = key*10+9
    draw()
    pygame.display.update()

pygame.quit()
```

**输出:**

<video class="wp-video-shortcode" id="video-460036-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727160706/binary-search-visualization.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727160706/binary-search-visualization.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200727160706/binary-search-visualization.webm)</video>