# 在 Python 中模拟事件

> 原文:[https://www.geeksforgeeks.org/mimicking-events-python/](https://www.geeksforgeeks.org/mimicking-events-python/)

**首先，什么是事件？**
事件是一个类在感兴趣的事情发生时通知其他类的结构。
在外行人的语言中，基本上类似于举旗示意别人发生了感兴趣的事情。

**Python 中什么时候使用事件？**

基于事件的编程主要用于使用用户界面(UI)的情况，在这种情况下，需要向不同的组件发出某种事件的信号。例如，设想一个货币转换器，当用户在框 1 中输入某个值时，它需要在框 2 中输出转换后的货币。【box2 如何得知用户已经在 box1 中输入了某个内容，以及在对该内容的响应中需要做什么。
这是基于事件编程最基本的例子之一。
另一个可能的例子是家庭安全系统，在该系统中，一些可能的动作，例如警报需要被发出，信息需要被发送给所有者，并且警察需要被告知可能的盗窃，将在锁被破坏时被执行。使用基于事件的机制可以很容易地设计这些类型的系统，在这种机制中，一旦有人打破锁，就会引发事件，然后通知事件处理程序发挥它们的作用。
现在，在这篇文章中，我们将使用后一个例子来理解如何在 Python 中设计默认不支持的事件。

## 计算机编程语言

```py
class Event(object):

    def __init__(self):
        self.__eventhandlers = []

    def __iadd__(self, handler):
        self.__eventhandlers.append(handler)
        return self

    def __isub__(self, handler):
        self.__eventhandlers.remove(handler)
        return self

    def __call__(self, *args, **keywargs):
        for eventhandler in self.__eventhandlers:
            eventhandler(*args, **keywargs)

class Police(object):
    def __init__(self, policeTelephoneNo):
        self._telephone = policeTelephoneNo

    def CallPolice(self):
        print "police have been informed"

class Owner(object):
    def __init__(self, ownerMobile):
        self.__mobile = ownerMobile

    def Message(self):
        print "owner has been messaged about the possible theft"

class Alarm(object):

    def StartAlarm(self):
        print "Alarm has started"

# LockClass

class Lock(object):

    def __init__(self):
        self.OnLockBroken = Event()

    def LockBroken(self):
        # This function will be executed once a lock is broken and will
        # raise an event
        self.OnLockBroken()

    def AddSubscribersForLockBrokenEvent(self,objMethod):
        self.OnLockBroken += objMethod

    def RemoveSubscribersForLockBrokenEvent(self,objMethod):
        self.OnLockBroken -= objMethod

def Simulation():
    # In the simulation we have a lock
    # which will be broken and the object of Police
    # owner and Alarm classes which are
    # to be notified as soon as lock is broke

    # Required objects
    godrejLockObj = Lock()
    localPoliceObj = Police(100)
    ownerObj = Owner(99999999)
    mainDoorAlarmObj = Alarm()

    # Setting these objects to receive the events from lock
    godrejLockObj.AddSubscribersForLockBrokenEvent(localPoliceObj.CallPolice)
    godrejLockObj.AddSubscribersForLockBrokenEvent(ownerObj.Message)
    godrejLockObj.AddSubscribersForLockBrokenEvent(mainDoorAlarmObj.StartAlarm)

    # Now the Lock is broken by some burglar
    # thus LockBroken function will be called
    godrejLockObj.LockBroken()

    # All three notifications must be printed
    # as soon as Lock is broken now

    # You can also remove any receiver by
    # calling the RemoveSubscribersForLockBrokenEvent
    godrejLockObj.RemoveSubscribersForLockBrokenEvent(mainDoorAlarmObj.StartAlarm)
if __name__ == "__main__":        
    Simulation()
```

输出:

```py
police have been informed
owner has been messaged about the possible theft
Alarm has started
```

引发事件的类称为发布者，接收事件的类称为订阅者。
同样，一个事件可以有多个订阅者，一个订阅者可以处理来自多个发布者的多个事件
本文由**安基特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。