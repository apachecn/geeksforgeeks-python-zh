# 使用 Python3 翻转瓷砖(记忆游戏)

> 原文:[https://www . geeksforgeeks . org/fling-tiles-memory-game-using-python 3/](https://www.geeksforgeeks.org/flipping-tiles-memory-game-using-python3/)

翻转瓷砖游戏可以用来测试我们的记忆力。在这种情况下，我们有一定数量的偶数瓷砖，其中每个数字/图形都有一对。瓷砖面朝下，我们必须翻转才能看到。在一个回合中，一个人翻转 2 个瓷砖，如果瓷砖匹配，则它们被移除。如果没有，那么它们被翻转并放回原位。我们继续这样做，直到所有的瓷砖都被匹配和移除。

为了用 Python 模拟这个游戏，我们将使用**海龟**和随机**模块**。

**进场:**

1.  导入海龟和随机模块。Python 提供了可以生成随机数的随机模块，海龟模块被用于制作不同的对象。
2.  设置屏幕，并选择输出屏幕窗口的背景颜色。
3.  定义一个为你的游戏基础制作正方形的函数。
4.  定义一个函数来检查索引号。
5.  定义一个功能，使你的游戏用户友好，即用户点击。
6.  编写一个函数，在步骤 3 中定义的正方形基底上绘制图块。
7.  最后，使用 shuffle()函数对放置在方形框中的方形瓷砖上的数字进行洗牌。

## 蟒蛇 3

```py
# import modules
from random import *
from turtle import *

# set the screen
screen = Screen()

#choose background color
screen.bgcolor("yellow")

# define the function
# for creating a square section
# for the game
def Square(x, y):
    up()
    goto(x, y)
    down()
    color('white', 'green')
    begin_fill()
    for count in range(4):
        forward(50)
        left(90)
    end_fill()

# define function to
# keep a check of index number
def Numbering(x, y):
    return int((x + 200) // 50 + ((y + 200) // 50) * 8)

# define function
def Coordinates(count):
    return (count % 8) * 50 - 200, (count // 8) * 50 - 200

# define function
# to make it interactive
# user click
def click(x, y):
    spot = Numbering(x, y)
    mark = state['mark']

    if mark is None or mark == spot or tiles[mark] != tiles[spot]:
        state['mark'] = spot
    else:
        hide[spot] = False
        hide[mark] = False
        state['mark'] = None

def draw():
    clear()
    goto(0, 0)
    stamp()

    for count in range(64):
        if hide[count]:
            x, y = Coordinates(count)
            Square(x, y)

    mark = state['mark']

    if mark is not None and hide[mark]:
        x, y = Coordinates(mark)
        up()
        goto(x + 2, y)
        color('black')
        write(tiles[mark], font=('Arial', 30, 'normal'))

    update()
    ontimer(draw, 10)

tiles = list(range(32)) * 2
state = {'mark': None}
hide = [True] * 64

# for shuffling the
# numbers placed inside
# the square tiles
shuffle(tiles)
tracer(False)
onscreenclick(click)
draw()
done()
```

**输出:**

<video class="wp-video-shortcode" id="video-491818-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200915143723/Test-Your-memory.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200915143723/Test-Your-memory.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200915143723/Test-Your-memory.mp4)</video>