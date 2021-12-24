# 如何在 Scala 地图中找到最大的键

> 原文:[https://www . geesforgeks . org/如何在 scala-map 中找到最大的键/](https://www.geeksforgeeks.org/how-to-find-largest-key-in-scala-map/)

在 Scala 中，映射与保存键:值对的字典相同。在本文中，我们将学习如何在 Scala 中找到给定映射中最大的键。利用 **max()** 方法寻找地图的最大元素。
**语法:**

```py
m1.max 
Here, m1 is name of a map.
```

让我们借助几个例子来更好地理解它。
**例 1:**

```py
// Scala program to get highest keys

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a map 
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs") 

        // Displays max key 
        println(m1.max) 

    } 
} 
```

**输出:**

```py
(4, for)

```

**示例#2:** 仅使用`keysIterator`迭代键

```py
// Scala program to get highest keys

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a map 
        val mapIm = Map("Ajay" -> 30, 
                        "Bhavesh" -> 20, 
                        "Charlie" -> 50) 

        // Displays output 
        println(mapIm.keysIterator.max) 

    } 
} 
```

**输出:**

```py
Charlie

```