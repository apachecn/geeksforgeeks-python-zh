# python–datetime . tzinfo()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-datetime-tzinfo/

DateTime 类提供了各种函数来操作日期和时间间隔。您在`datetime.now()`中使用的日期时间对象实际上是日期时间类的对象。这些对象帮助我们使用日期和时间函数。

**注意:**更多信息请参考 [Python 日期时间模块，示例](https://www.geeksforgeeks.org/python-datetime-module-with-examples/)

## DateTime.tzinfo()

`datetime.now()`没有任何关于时区的信息。它只是使用当前的系统时间。在某些情况下，可能需要时区详细信息。在这种情况下，使用 **tzinfo** 抽象类。tzinfo 是一个抽象基类。它不能直接实例化。一个具体的子类必须派生它并实现这个抽象类提供的方法。

tzinfo 类的实例可以传递给 datetime 和 time 对象的构造函数。它适用于将当地时间转换为世界协调时或考虑夏令时的情况。

## 天真和感知日期时间对象

不包含任何时区信息的日期时间对象被称为“T2”天真日期时间对象“T3”。对于天真的日期时间对象，`datetime_object.tzinfo`将是`None`。感知日期时间对象包含嵌入其中的时区信息。

tzinfo 基类中可实现的方法有:

*   utcoffset(自我、dt)
*   dst(自我，dt)
*   tzname(自我、dt)
*   fromutc(自我，dt)

### utcoffset()

它返回作为参数传递的 datetime 实例的偏移量。

**这个偏移量指的是什么？**

它指的是时区偏移，表示时区比协调世界时或世界时坐标(UTC)提前了多少小时。偏移量写成+00:00。例如:对于亚洲/台北，写成 UTC +08:00。

它占用 datetime 对象的时间，并返回 datetime 对象中的时间与 UTC 中同一时间点的时间之差。它返回世界协调时以东**分钟的偏移量。如果当地时间在世界协调时以西，则为负值。一般实施形式如下:**

```py
*For fixed offset :*

 def utcoff(self, dt):
      return constant

*For time aware objects :*

def utcoffset(self, dt):
        return self.stdoffset + self.dst(dt)
```

### dst()

缩写为**D**ay-light**S**avi**T**ime。它表示在夏季将时钟提前 1 小时，这样黑暗会根据时钟晚些时候降临。它被设置为开或关。它基于包含 9 个元素的元组进行检查，如下所示:

> (dt.year，dt.month，dt.day，dt.hour，dt.minute，dt.second，dt.weekday()，0，0)

编写私有函数是为了根据这 9 个元素返回 0、1 或-1。在此基础上确定`dst(self, dt)`的值。函数写在定义`dst()`的类中。其内容如下:

```py
def _isdst(self, dt):

        tt = (dt.year, dt.month, dt.day,
              dt.hour, dt.minute, dt.second,
              dt.weekday(), 0, 0)

        stamp = _time.mktime(tt)
        tt = _time.localtime(stamp)

        return tt.tm_isdst > 0
```

这里`mktime()`取这个元组，并将其转换为从本地时间中的纪元开始经过的时间(以秒为单位)。然后，`tm_isdst()`与 mktime 一起使用。它返回如下值:

> **“1”**–夏令时开启
> **“0”**–夏令时关闭
> **“-1”**–夏令时信息未知

将该代码添加到类中后，`dst()`可以根据条件定义如下。

```py
*For fixed offset class :*

 def dst(self, dt):
        return ZERO

*For time aware objects :*

 def utcoffset(self, dt):
        if self._isdst(dt):
            return DSTOFFSET
        else:
            return STDOFFSET

```

### tzname()

这用于查找传递的 datetime 对象的时区名称。它返回一个 Python 字符串对象。

**示例:**

```py
import datetime as dt
from dateutil import tz

tz_string = dt.datetime.now(dt.timezone.utc).astimezone().tzname()

print("datetime.now() :", tz_string)

NYC = tz.gettz('Europe / Berlin')  
dt1 = dt.datetime(2015, 5, 21, 12, 0) 
dt2 = dt.datetime(2015, 12, 21, 12, 0, tzinfo = NYC) 

print("Naive Object :", dt1.tzname())
print("Aware Object :", dt2.tzname())
```

**Output:**

```py
datetime.now() : UTC
Naive Object : None
Aware Object : CET

```

### fromutc()

该函数采用对象的日期和时间(以世界协调时表示)，并返回等效的当地时间。它主要用于调整日期和时间。从默认`datetime.astimezone()`实现调用。dt.tzinfo 将作为自身传递，dt 的日期和时间数据将作为等效的当地时间返回。

**注意:**如果 dt.tzinfo 不是 self 或/和 dst()为 None，将会提升`ValueError`。

下面给出了一般实现:

```py
def fromutc(self, dt):
    dt_offset = dt.utcoffset()
    dt_dst = dt.dst()
    delta = dt_offset - dt_dst  

    if delta:
          dt += delta   
          dtdst = dt.dst()

    if dtdst:
          return dt + dtdst
    else:
          return dt
```