# 使用 Python 创建网站警报

> 原文:[https://www . geesforgeks . org/create-a-网站-报警-使用-python/](https://www.geeksforgeeks.org/create-a-website-alarm-using-python/)

我们使用书签来记住我们认为将来会经常使用的重要网站。
这里有一个简单的 python 代码，它把网站的 URL 作为第一个输入，把你想要打开它的时间作为第二个输入。

当时间到达您给定的时间值时，它会自动打开您在网络浏览器中请求的网址。
在这段代码中，我们将导入两个 python 模块——Time 和 Webbrowser。

```
# Import the time module, it provides various time-related 
# functions. 
import time 

# Import the webbrowser module, it is used to 
# display various HTML documents to the user. 
import webbrowser 

# First Input: It is the time of the form 
# 'Hours:Minutes:Seconds' that you'll 
# use to set the alarm. 
Set_Alarm = input("Set the website alarm as H:M:S:") 

# Second Input: It is the URL that you want 
# to open on the given time. 
url = input("Enter the website you want to open:") 

# This is the actual time that we will use to print. 
Actual_Time = time.strftime("%I:%M:%S") 

# This is the while loop that'll print the time 
# until it's value will be equal to the alarm time 
while (Actual_Time != Set_Alarm): 
    print ("The time is " + Actual_Time) 
    Actual_Time = time.strftime("%I:%M:%S") 
    time.sleep(1) 

# This if statement plays the role when its the 
# alarm time and executes the code within it. 
if (Actual_Time == Set_Alarm): 
    print ("You should see your webpage now :-)")

    # We are calling the open() 
    # function from the webrowser module. 
    webbrowser.open(url) 
```

你可以通过进入[这里](https://github.com/Shivams334/LearningPython/blob/master/WebsiteAlarm.py)来贡献代码。

本文由**希瓦姆·夏尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

你可以通过进入[这里](https://github.com/Shivams334/LearningPython/blob/master/WebsiteAlarm.py)来贡献代码。