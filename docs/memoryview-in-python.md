# Python 中的 memoryview()

> 原文:[https://www.geeksforgeeks.org/memoryview-in-python/](https://www.geeksforgeeks.org/memoryview-in-python/)

**Python memoryview()函数**返回对象的内存视图。在了解更多关于 memoryview()函数之前，让我们来看看为什么要使用这个函数。

## **为什么****我们使用 memoryview()函数？**

由于内存视图是在 Python 中公开缓冲区协议的一种安全方式，并且内存视图在许多有用的上下文中表现得就像字节一样(例如，它支持映射协议)，因此如果小心使用，它可以提供足够的替换。最棒的是，它在封面下使用了缓冲协议，以避免复制和篡改指向数据的指针。所以在我们进入什么内存视图之前，我们需要先了解缓冲协议。

### **缓冲协议**

缓冲协议提供了一种访问对象内部数据的方法。这个内部数据是一个内存阵列或缓冲区。它允许一个对象公开其内部数据(缓冲区)，另一个对象访问这些缓冲区，而无需中间复制。缓冲协议只能在 **C-API** 级别访问，不能使用我们正常的代码库。因此，为了将相同的协议公开给一个普通的 Python 代码库，内存视图是存在的。

### **记忆视图**

memoryview 对象允许 Python 代码访问支持缓冲区协议的对象的内部数据，而无需复制。memoryview()函数允许直接读写对象的面向字节的数据，而不需要先复制它。当在大对象上操作时，这可以产生很大的性能提升，因为它在切片时不会创建副本。

> **语法:** memoryview(obj)
> 
> **参数:**
> 
> *   Obj- the object of internal data to be exposed.
> *   Buffer protocols–-str and bytearray are supported (but unicode is not supported).
> 
> **返回值:**返回 memoryview 对象。

## **Python 内存视图()示例**

### **示例 1: Python memoryview()工作方式**

## 蟒蛇 3

```py
byte_array = bytearray('XYZ', 'utf-8')

mv = memoryview(byte_array)

print(mv[0])
print(bytes(mv[0:1]))
```

**输出:**

```py
88
b'X
```

### 示例 2:使用 memoryview 修改内部数据

## 蟒蛇 3

```py
# Python program to illustrate
# Modifying internal data using memory view

# random bytearray
byte_array = bytearray('XYZ', 'utf-8')
print('Before update:', byte_array)

mem_view = memoryview(byte_array)

# update 2nd index of mem_view to J
mem_view[2] = 74
print('After update:', byte_array)
```

**输出:**

```py
Before update: bytearray(b'XYZ')
After update: bytearray(b'XYJ')
```

**解释我们如何在上面的程序中修改内部数据:**这里，我们将内存视图的第二个索引更新为 ASCII 值 74 (J)。在这个 memoryview 对象中，mem_view 引用相同的缓冲区或内存，并更新 mem_view 中的索引，它还更新 byte_array。

### 示例 3: Python memoryview()转换为字节

## 蟒蛇 3

```py
# Python program to illustrate memory view

# random bytearray
byte_array = bytearray('XYZ', 'utf-8')

mem_view = memoryview(byte_array)
print(type(mem_view))

byt = bytes(mem_view)
print(type(byt))
```

**输出:**

```py
<class 'memoryview'>
<class 'bytes'>
```

### 示例 4:将 Python memoryview()转换为字符串

## 蟒蛇 3

```py
# Python program to illustrate memory view

# random bytearray
byte_array = bytearray('XYZ', 'utf-8')

mem_view = memoryview(byte_array)
print(type(mem_view))

string = str(mem_view)
print(type(string))
```

**输出:**

```py
<class 'memoryview'>
<class 'str'>
```

**缓冲协议和内存视图的重要性**

通过使用缓冲协议，我们可以像处理图像的二进制数据一样处理大数据。缓冲协议，可以创建另一个对象访问修改大数据而不复制它。这使得程序使用更少的内存，提高了执行速度。