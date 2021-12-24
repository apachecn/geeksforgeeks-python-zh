# Python |接球游戏

> 原文:[https://www . geesforgeks . org/python-接球游戏/](https://www.geeksforgeeks.org/python-catching-the-ball-game/)

Python 是一种多用途语言，几乎可以用于开发的每个领域。Python 也可以用来开发不同类型的游戏。让我们尝试使用 Python 和 TKinter 开发一个简单的*接球游戏*。
游戏很简单。游戏窗口底部有一个栏，可以使用游戏窗口中的按钮向左或向右移动。红球会从上到下不断下落，可以从任意随机的 x 轴距离开始。任务是通过向左或向右移动将该杆带到合适的位置，这样红色的球将落在该杆上(将球接住到杆上)，而不是落在地面上。如果球员将球接到杆上，那么得分将增加，球将消失，新的红色球将从随机的 x 轴距离开始从上到下下落。如果玩家在杆上接球失误，那么你将输掉比赛，最终记分卡将出现在游戏窗口上。
**进场:**

1.  使用 python 中的 Tkinter 包来构建 GUI(图形用户界面)。
2.  在 Python 中使用画布绘制对象–画布是一个矩形区域，用于绘制图片或其他复杂布局。我们可以在画布上放置图形、文本、小部件或框架。

```
Syntax: w = Canvas ( master, option=value, ... )

Parameters:
master - This represents the parent window.
options - List of most commonly used options for this widget. 
These options can be used as key-value pairs separated by commas. 
Example- width, height etc. 
```

1.  使用 canvas.create_oval 创建球。
    **create_oval** 在给定的坐标下创建一个圆或椭圆。它需要两对坐标；椭圆形边框的左上角和右下角。

```
Syntax: oval = canvas.create_oval(x0, y0, x1, y1, options)
```

1.  使用 canvas.create_rectangle 创建栏。
    **create_rectangle** 在给定的坐标下创建一个矩形。它需要两对坐标；左上角和右下角的坐标。

```
Syntax: oval = canvas.create_rectangle(x0, y0, x1, y1, options)
```

1.  使用 canvas.move 移动球或棒。
    **canvas.move** 使对象能够以指定的(x，y)坐标移动。

```
Syntax: move=canvas.move(name of object, x, y) 
```

1.  **注:** ***** 取 x=0 只在垂直方向移动球，取 y=0 只在水平方向移动杆。 ***** 用 canvas.delete(object)当球接触地面或杆时消失。
2.  使用按钮向前或向后移动栏，然后对其应用动作事件。参考 [Python gui Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

**Python 代码:**

## 蟒蛇 3

```
# Python code for catching the ball game

# importing suitable packages
from tkinter import Tk,Button,Label
from tkinter import Canvas
from random import randint

# defining Tk from Tkinter
root = Tk()
root.title("Catch the ball Game")
root.resizable(False,False)

# for defining the canvas
canvas = Canvas(root, width=600, height=600)
canvas.pack()

# variable for the vertical distance
# travelled by ball
limit = 0

# variable for horizontal distance
# of bar from x-axis
dist = 5

# variable for score
score = 0

# Class for the Creating and moving ball
class Ball:

    # for creation of ball on the canvas
    def __init__(self, canvas, x1, y1, x2, y2):
        self.x1 = x1
        self.y1 = y1
        self.x2 = x2
        self.y2 = y2
        self.canvas = canvas

        # for creation of ball object
        self.ball = canvas.create_oval(self.x1, self.y1, self.x2, self.y2,
                                                fill = "red",tags = 'dot1')

    # for moving the ball
    def move_ball(self):

        # defining offset
        offset = 10
        global limit

        # checking if ball lands ground or bar
        if limit >= 510:
            global dist,score,next

            # checking that ball falls on the bar
            if(dist - offset <= self.x1 and
               dist + 40 + offset >= self.x2):

                # incrementing the score
                score += 10

                # disappear the ball
                canvas.delete('dot1')

                # calling the function for again
                # creation of ball object
                ball_set()

            else:
                # disappear the ball
                canvas.delete('dot1')
                bar.delete_bar(self)

                # display the score
                score_board()
            return

        # incrementing the vertical distance
        # travelled by ball by deltay
        limit += 1

        # moving the ball in vertical direction
        # by taking x=0 and y=deltay
        self.canvas.move(self.ball,0,1)

        # for continuous moving of ball again call move_ball
        self.canvas.after(10,self.move_ball)

# class for creating and moving bar        
class bar:

    # method for creating bar
    def __init__(self,canvas,x1,y1,x2,y2):
        self.x1 = x1
        self.y1 = y1
        self.x2 = x2
        self.y2 = y2
        self.canvas = canvas

        # for creating bar using create_rectangle
        self.rod=canvas.create_rectangle(self.x1, self.y1, self.x2, self.y2,
                                                  fill="yellow",tags='dot2')

    # method for moving the bar
    def move_bar(self,num):
        global dist

        # checking the forward or backward button
        if(num == 1):

            # moving the bar in forward direction by
            # taking x-axis positive distance and
            # taking vertical distance y=0
            self.canvas.move(self.rod,20,0)

            # incrementing the distance of bar from x-axis
            dist += 20
        else:

            # moving the bar in backward direction by taking x-axis 
            # negative distance and taking vertical distance y=0
            self.canvas.move(self.rod,-20,0)

            # decrementing the distance of bar from x-axis
            dist-=20

    def delete_bar(self):
        canvas.delete('dot2')

# Function to define the dimensions of the ball
def ball_set():
    global limit
    limit=0

    # for random x-axis distance from
    # where the ball starts to fall    
    value = randint(0,570)

    # define the dimensions of the ball
    ball1 = Ball(canvas,value,20,value+30,50)

    # call function for moving of the ball
    ball1.move_ball()

# Function for displaying the score
# after getting over of the game
def score_board():
    root2 = Tk()
    root2.title("Catch the ball Game")
    root2.resizable(False,False)
    canvas2 = Canvas(root2,width=300,height=300)
    canvas2.pack()

    w = Label(canvas2,text="\nOOPS...GAME IS OVER\n\nYOUR SCORE = "
                                            + str(score) + "\n\n")
    w.pack()

    button3 = Button(canvas2, text="PLAY AGAIN", bg="green",
                           command=lambda:play_again(root2))
    button3.pack()

    button4 = Button(canvas2,text="EXIT",bg="green",
                     command=lambda:exit_handler(root2))
    button4.pack()

# Function for handling the play again request
def play_again(root2):
    root2.destroy()
    main()

# Function for handling exit request
def exit_handler(root2):
    root2.destroy()
    root.destroy()

# Main function
def main():
    global score,dist
    score = 0
    dist = 0

    # defining the dimensions of bar    
    bar1=bar(canvas,5,560,45,575)

    # defining the text,colour of buttons and
    # also define the action after click on
    # the button by calling suitable methods
    button = Button(canvas,text="==>", bg="green",
                    command=lambda:bar1.move_bar(1))

    # placing the buttons at suitable location on the canvas
    button.place(x=300,y=580)

    button2 = Button(canvas,text="<==",bg="green",
                     command=lambda:bar1.move_bar(0))
    button2.place(x=260,y=580)

    # calling the function for defining
    # the dimensions of ball
    ball_set()
    root.mainloop()

# Driver code
if(__name__=="__main__"):
    main()
```

**输出:**

<video class="wp-video-shortcode" id="video-233070-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/geeks.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/geeks.mp4](https://media.geeksforgeeks.org/wp-content/uploads/geeks.mp4)</video>

**注意:**由于导入了 Tkinter 包，上述代码无法在联机 IDE 上运行。