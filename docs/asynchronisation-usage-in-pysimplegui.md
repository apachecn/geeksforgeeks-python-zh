# pysimplegui 中的异步使用

> 哎哎哎:# t0]https://www . geeksforgeeks . org/asynchronous-using-in-pysimplegui/

我们将这种设计模式用于实际上需要定期轮询或输出的项目。在这种情况下，我们表示希望在窗口中有一个**超时=10** 。此外，这将导致调用返回一个“超时键”，因为每 10 毫秒的事件已经过去，而没有一些图形用户界面的事情首先发生。超时键是 **PySimpleGUI。TIMEOUT_KEY** 通常写成 **sg。普通 PySimpleGUI 代码中的 TIMEOUT_KEY** 。

使用带超时的窗口时请小心。您很少需要使用**超时=0** 。零值是非阻塞调用，因此我们不需要试图滥用这种设计模式。
关于计时器的一个简短说明是，这不是秒表的好设计，因为它很容易漂移。这绝对不会被认为是一个商业代码中的好解决方案。为了更好的准确性，我们应该总是从一个有信誉的来源获得实际时间，也许是从操作系统。我们可以用它来测量和显示时间。

**为了理解它，我们将使用 PySimpleGUI 在 Python 中实现一个秒表。**

```
import PySimpleGUI as sg

sg.theme('SandyBeach')

layout = [  [sg.Text('Stopwatch', size =(20, 2), justification ='center')],
            [sg.Text(size =(10, 2), font =('Arial', 20), justification ='center', key ='-OUTPUT-')],
            [sg.T(' ' * 5), sg.Button('Start / Stop', focus = True), sg.Quit()]]

window = sg.Window('Stopwatch Timer', layout)

timer_running, counter = True, 0

# Event Loop
while True:  

    # Please try and use as high of a timeout value as you can                               
    event, values = window.read(timeout = 10) 

    # if user closed the window using X or clicked Quit button
    if event in (None, 'Quit'):             
        break
    elif event == 'Start / Stop':
        timer_running = not timer_running
    if timer_running:
        window['-OUTPUT-'].update('{:02d}:{:02d}.{:02d}'.format((counter // 100) // 60, 
                                                 (counter // 100) % 60, counter % 100))
        counter += 1
window.close()
```

**输出**T2】

<video class="wp-video-shortcode" id="video-430680-1" width="608" height="486" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515104831/2020-05-15-10-34-49-online-video-cutter.com_.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515104831/2020-05-15-10-34-49-online-video-cutter.com_.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515104831/2020-05-15-10-34-49-online-video-cutter.com_.mp4)</video>