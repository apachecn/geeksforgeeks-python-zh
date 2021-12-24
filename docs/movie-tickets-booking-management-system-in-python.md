# Python 中的电影票预约管理系统

> 原文:[https://www . geesforgeks . org/电影票-订票-管理-python 中的系统/](https://www.geeksforgeeks.org/movie-tickets-booking-management-system-in-python/)

在本文中，我们将为预订电影票编写一个简单的程序。对于那些想要从事任何项目的热情的初学者来说，这将非常有用。

用 Python 编写一个程序来构建一个简单的电影票预订管理系统。

我们使用了如下六个函数:

*   t_movie()
*   剧院()
*   时机(a)
*   电影(剧场)
*   中心()
*   城市()

**进场:**下面是做以上操作的进场:

**1。t_movie:** 此方法用于选择电影名称。

```
#this t_movie function is used to select movie name 
def t_movie():
    global f
    f = f+1
    print("which movie do you want to watch?")
    print("1,movie 1 ")
    print("2,movie 2 ")
    print("3,movie 3")
    print("4,back")
    movie = int(input("choose your movie: "))
    if movie == 4:
      # in this it goes to center function and
      # from center it goes to movie function 
      # and it comes back here and then go to theater 
      center()
      theater()
      return 0
    if f == 1:
      theater()
```

**2。theater():** 此方法用于选择屏幕。

```
# this theater function used to select screen 
def theater():
    print("which screen do you want to watch movie: ")
    print("1,SCREEN 1")
    print("2,SCREEN 2")
    print("3,SCREEN 3")
    a = int(input("choose your screen: "))
    ticket = int(input("number of ticket do you want?: "))
    timing(a)
```

**3。定时(a):** 此方法用于选择电影的定时。

```
# this timing function used to select timing for movie 
def timing(a):
    time1 = {
        "1": "10.00-1.00",
        "2": "1.10-4.10",
        "3": "4.20-7.20",
        "4": "7.30-10.30"
    }
    time2 = {
        "1": "10.15-1.15",
        "2": "1.25-4.25",
        "3": "4.35-7.35",
        "4": "7.45-10.45"
    }
    time3 = {
        "1": "10.30-1.30",
        "2": "1.40-4.40",
        "3": "4.50-7.50",
        "4": "8.00-10.45"
    }
    if a == 1:
        print("choose your time:")
        print(time1)
        t = input("select your time:")
        x = time1[t]
        print("successful!, enjoy movie at "+x)
    elif a == 2:
        print("choose your time:")
        print(time2)
        t = input("select your time:")
        x = time2[t]
        print("successful!, enjoy movie at "+x)
    elif a == 3:
        print("choose your time:")
        print(time3)
        t = input("select your time:")
        x = time3[t]
        print("successful!, enjoy movie at "+x)
    return 0
```

**4。电影(剧场):**此方法用于根据剧场选择电影。

```
def movie(theater):
    if theater == 1:
        t_movie()
    elif theater == 2:
        t_movie()
    elif theater == 3:
        t_movie()
    elif theater == 4:
        city()
    else:
        print("wrong choice")
```

**5。center():** 此方法用于选择剧场。

```
def center():
    print("which theater do you wish to see movie? ")
    print("1,Inox")
    print("2,Icon")
    print("3,pvp")
    print("4,back")
    a = int(input("choose your option: "))
    movie(a)
    return 0
```

**6。city():** 此方法用于选择城市。

```
# this function is used to select city 
def city():
    print("hi welcome to movie ticket booking: ")
    print("where you want to watch movie?:")
    print("1,city 1")
    print("2,city 2 ")
    print("3,city 3 ")
    place = int(input("choose your option: "))
    if place == 1:
      center()
    elif place == 2:
      center()
    elif place == 3:
      center()
    else:
      print("wrong choice")
```

**全面实施:**

## 蟒蛇 3

```
global f
f = 0

#this t_movie function is used to select movie name
def t_movie():
    global f
    f = f+1
    print("which movie do you want to watch?")
    print("1,movie 1 ")
    print("2,movie 2 ")
    print("3,movie 3")
    print("4,back")
    movie = int(input("choose your movie: "))
    if movie == 4:
      # in this it goes to center function and from center it goes to movie function and it comes back here and then go to theater
      center()
      theater()
      return 0
    if f == 1:
      theater()

# this theater function used to select screen
def theater():
    print("which screen do you want to watch movie: ")
    print("1,SCREEN 1")
    print("2,SCREEN 2")
    print("3,SCREEN 3")
    a = int(input("choose your screen: "))
    ticket = int(input("number of ticket do you want?: "))
    timing(a)

# this timing function used to select timing for movie
def timing(a):
    time1 = {
        "1": "10.00-1.00",
        "2": "1.10-4.10",
        "3": "4.20-7.20",
        "4": "7.30-10.30"
    }
    time2 = {
        "1": "10.15-1.15",
        "2": "1.25-4.25",
        "3": "4.35-7.35",
        "4": "7.45-10.45"
    }
    time3 = {
        "1": "10.30-1.30",
        "2": "1.40-4.40",
        "3": "4.50-7.50",
        "4": "8.00-10.45"
    }
    if a == 1:
        print("choose your time:")
        print(time1)
        t = input("select your time:")
        x = time1[t]
        print("successful!, enjoy movie at "+x)
    elif a == 2:
        print("choose your time:")
        print(time2)
        t = input("select your time:")
        x = time2[t]
        print("successful!, enjoy movie at "+x)
    elif a == 3:
        print("choose your time:")
        print(time3)
        t = input("select your time:")
        x = time3[t]
        print("successful!, enjoy movie at "+x)
    return 0

def movie(theater):
    if theater == 1:
        t_movie()
    elif theater == 2:
        t_movie()
    elif theater == 3:
        t_movie()
    elif theater == 4:
        city()
    else:
        print("wrong choice")

def center():
    print("which theater do you wish to see movie? ")
    print("1,Inox")
    print("2,Icon")
    print("3,pvp")
    print("4,back")
    a = int(input("choose your option: "))
    movie(a)
    return 0

# this function is used to select city
def city():
    print("Hi welcome to movie ticket booking: ")
    print("where you want to watch movie?:")
    print("1,city 1")
    print("2,city 2 ")
    print("3,city 3 ")
    place = int(input("choose your option: "))
    if place == 1:
      center()
    elif place == 2:
      center()
    elif place == 3:
      center()
    else:
      print("wrong choice")

city() # it calls the function city
```

**输出:**

> 嗨，欢迎来到电影票预订:
> 你想在哪里看电影？:
> 1、城市 1
> 2、城市 2
> 3、城市 3
> 选择你的选项:2
> 你希望看哪家影院的电影？
> 1、Inox
> 2、Icon
> 3、pvp
> 4、back
> 选择你的选项:1
> 你想看哪部电影？
> 1、电影 1
> 2、电影 2
> 3、电影 3
> 4、后退
> 选择你的电影:3
> 你想看哪个屏幕电影:
> 1、screen EN 1
> 2、screen EN 2
> 3、screen EN 3
> 选择你的屏幕:1
> 你想要多少张票？:4
> 选择你的时间:
> {'1': '10.00-1.00 '，' 2': '1.10-4.10 '，' 3': '4.20-7.20 '，' 4': '7.30-10.30'}
> 选择你的时间:2
> 成功！，在 1.10-4.10
> 欣赏电影