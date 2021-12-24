# Python 中使用 Tkinter 的彩色游戏

> 原文:[https://www.geeksforgeeks.org/color-game-python/](https://www.geeksforgeeks.org/color-game-python/)

前提条件: [Python GUI Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

[TKinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 广泛用于开发 GUI 应用。除了应用程序，我们还可以使用 Tkinter GUI 开发游戏。

让我们试着用 Tkinter 做一个游戏。在这个游戏中，玩家必须输入出现在屏幕上的单词的颜色，因此分数增加 1，玩这个游戏的总时间是 30 秒。游戏中使用的颜色有红、蓝、绿、粉、黑、黄、橙、白、紫、棕。界面会以不同的颜色显示不同颜色的名称。玩家必须识别颜色并输入正确的颜色名称才能赢得游戏。

下面是上面游戏的实现:

```
# import the modules 
import tkinter
import random

# list of possible colour.
colours = ['Red','Blue','Green','Pink','Black',
           'Yellow','Orange','White','Purple','Brown']
score = 0

# the game time left, initially 30 seconds.
timeleft = 30

# function that will start the game.
def startGame(event):

    if timeleft == 30:

        # start the countdown timer.
        countdown()

    # run the function to
    # choose the next colour.
    nextColour()

# Function to choose and
# display the next colour.
def nextColour():

    # use the globally declared 'score'
    # and 'play' variables above.
    global score
    global timeleft

    # if a game is currently in play
    if timeleft > 0:

        # make the text entry box active.
        e.focus_set()

        # if the colour typed is equal
        # to the colour of the text
        if e.get().lower() == colours[1].lower():

            score += 1

        # clear the text entry box.
        e.delete(0, tkinter.END)

        random.shuffle(colours)

        # change the colour to type, by changing the
        # text _and_ the colour to a random colour value
        label.config(fg = str(colours[1]), text = str(colours[0]))

        # update the score.
        scoreLabel.config(text = "Score: " + str(score))

# Countdown timer function 
def countdown():

    global timeleft

    # if a game is in play
    if timeleft > 0:

        # decrement the timer.
        timeleft -= 1

        # update the time left label
        timeLabel.config(text = "Time left: "
                               + str(timeleft))

        # run the function again after 1 second.
        timeLabel.after(1000, countdown)

# Driver Code

# create a GUI window
root = tkinter.Tk()

# set the title
root.title("COLORGAME")

# set the size
root.geometry("375x200")

# add an instructions label
instructions = tkinter.Label(root, text = "Type in the colour"
                        "of the words, and not the word text!",
                                      font = ('Helvetica', 12))
instructions.pack() 

# add a score label
scoreLabel = tkinter.Label(root, text = "Press enter to start",
                                      font = ('Helvetica', 12))
scoreLabel.pack()

# add a time left label
timeLabel = tkinter.Label(root, text = "Time left: " +
              str(timeleft), font = ('Helvetica', 12))

timeLabel.pack()

# add a label for displaying the colours
label = tkinter.Label(root, font = ('Helvetica', 60))
label.pack()

# add a text entry box for
# typing in colours
e = tkinter.Entry(root)

# run the 'startGame' function 
# when the enter key is pressed
root.bind('<Return>', startGame)
e.pack()

# set focus on the entry box
e.focus_set()

# start the GUI
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-190544-1" width="665" height="427" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/tkinter_game.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/tkinter_game.mp4](https://media.geeksforgeeks.org/wp-content/uploads/tkinter_game.mp4)</video>

**注意:**由于 TKinter 模块，上述代码可能无法在联机 IDE 上运行。