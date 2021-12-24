# tkinter | python 中的 progress bar widget

> 原文:[https://www . geesforgeks . org/progress bar-widget-in-tkinter-python/](https://www.geeksforgeeks.org/progressbar-widget-in-tkinter-python/)

这个小部件的目的是让用户确信有事情正在发生。它可以在两种模式中的一种下运行–
在**确定模式**下，小部件显示一个在程序控制下从头到尾移动的指示器。
在**不确定模式**中，小部件被动画化，因此用户会相信有事情正在进行。在这种模式下，指示器在小部件的两端之间来回跳动。

**语法:**

```py
widget_object = Progressbar(parent, **options)

```

**代码#1** 在**确定**模式下

```py
# importing tkinter module
from tkinter import * from tkinter.ttk import *

# creating tkinter window
root = Tk()

# Progress bar widget
progress = Progressbar(root, orient = HORIZONTAL,
              length = 100, mode = 'determinate')

# Function responsible for the updation
# of the progress bar value
def bar():
    import time
    progress['value'] = 20
    root.update_idletasks()
    time.sleep(1)

    progress['value'] = 40
    root.update_idletasks()
    time.sleep(1)

    progress['value'] = 50
    root.update_idletasks()
    time.sleep(1)

    progress['value'] = 60
    root.update_idletasks()
    time.sleep(1)

    progress['value'] = 80
    root.update_idletasks()
    time.sleep(1)
    progress['value'] = 100

progress.pack(pady = 10)

# This button will initialize
# the progress bar
Button(root, text = 'Start', command = bar).pack(pady = 10)

# infinite loop
mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-298666-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190430235939/demonstration_of_progressbar_widget.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190430235939/demonstration_of_progressbar_widget.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190430235939/demonstration_of_progressbar_widget.mp4)</video>

**Code #2:** In **indeterminate** mode

```py
# importing tkinter module
from tkinter import * from tkinter.ttk import *

# creating tkinter window
root = Tk()

# Progress bar widget
progress = Progressbar(root, orient = HORIZONTAL,
            length = 100, mode = 'indeterminate')

# Function responsible for the updation
# of the progress bar value
def bar():
    import time
    progress['value'] = 20
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 40
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 50
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 60
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 80
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 100
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 80
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 60
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 50
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 40
    root.update_idletasks()
    time.sleep(0.5)

    progress['value'] = 20
    root.update_idletasks()
    time.sleep(0.5)
    progress['value'] = 0

progress.pack(pady = 10)

# This button will initialize
# the progress bar
Button(root, text = 'Start', command = bar).pack(pady = 10)

# infinite loop
mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-298666-2" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20190501001802/progressbar_in_indeterminate_mode.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20190501001802/progressbar_in_indeterminate_mode.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20190501001802/progressbar_in_indeterminate_mode.mp4)</video>