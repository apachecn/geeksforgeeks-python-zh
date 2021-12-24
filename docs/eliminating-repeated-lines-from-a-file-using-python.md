# 使用 Python 消除文件中的重复行

> 原文:[https://www . geeksforgeeks . org/使用 python 消除文件中的重复行/](https://www.geeksforgeeks.org/eliminating-repeated-lines-from-a-file-using-python/)

让我们看看如何使用 Python 的文件处理能力从文件中删除几个重复的行。如果文件很小，只有几行，那么从文件中删除/消除重复行的任务可以手动完成，但是当涉及到大文件时，这就是 Python 帮助您的地方。

**进场:**

1.  使用 **open()** 功能打开输入文件，并输入标志 **-r** 以阅读模式打开。
2.  打开一个输出文件，使用 **-w** 标志，在那里我们将删除文件中所有重复的行后存储文件的内容。
3.  使用 **set()** 方法跟踪到目前为止看到的所有行，这样我们就可以将其与当前读取的行进行比较。
4.  现在，迭代输入文件的每一行，并将其与目前看到的行进行比较。
5.  如果当前行也出现在目前看到的行中，那么跳过该行，否则将该行写入输出文件，并且不要忘记将当前行添加到目前看到的行中。
6.  关闭文件。

**示例:**

为了这个例子，让我们创建一个文件(Lorem_input.txt)，其中包含一些 lipsum 文本。所有重复的行都用粗体标出。

> **Lorem ipsum 疼痛静坐 amet，结果肥胖精英。**
> 相曲霉呈乳晕，软毛呈丝状质，调味品容易 ipsum。mauris vitae mollis magna .
> **Lorem ipsum 疼痛静坐 amet，由此导致肥胖精英。**
> aliqua lareet vite nisi 想要鹿特丹。渴欲盟 nec enim 残馀爱琴师维至 sapien。球探们喜欢快乐的自我主义。尼布奥创的球探、萨皮尼德的车队、萨皮蒂的憎恨。vivamus plaza rat ex sed liga porter dignisim .我们活在饥渴之中。
> **Lorem ipsum 疼痛静坐 amet，由此导致肥胖精英。**
> 阶级适应社会沉默的能力每升火炬为我们的妻子干杯，为喜马拉雅山脉的知觉干杯。病态的姿势爱琴海讨厌 ut 毒药。nam lobortis bibendum maximus .南狼队，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯。多诺 ec 毒药 sapien sed varius accumsan .多诺 EC venezuelas sapien sed various .

现在让我们创建一个空的输出文件(Lorem_output.txt)，我们将在其中存储修改后的输入文件。

## 蟒蛇 3

```
# creating the output file
outputFile = open('C:/Users/user/Desktop/Lorem_output.txt', "w")

# reading the input file
inputFile = open('C:/Users/user/Desktop/Lorem_input.txt', "r")

# holds lines already seen
lines_seen_so_far = set()

# iterating each line in the file
for line in inputFile:

    # checking if line is unique
    if line not in lines_seen_so_far:

        # write unique lines in output file
        outputFile.write(line)

        # adds unique lines to lines_seen_so_far
        lines_seen_so_far.add(line)        

# closing the file
inputFile.close()
outputFile.close()
```

运行上述 Python 脚本将从输入文件中删除所有重复的行，并将修改后的文件写入输出文件。运行这个脚本后，输出文件(Lorem_output.txt)看起来如下所示

> Lorem ipsum 疼痛静坐 amet，结果肥胖精英。
> 相曲霉呈空心状，软毛呈绒毛状质，调味品容易 ipsum。mauris vitae mollis magna .
> aliquam lareet vite nisi 想要芦荟。渴欲盟 nec enim 残馀爱琴师维至 sapien。球探们喜欢快乐的自我主义。尼布奥创的球探、萨皮尼德的车队、萨皮蒂的憎恨。vivamus plaza rat ex sed liga porter dignisim .我们活在饥渴之中。
> 阶级适者社会沉默者升者为我们的妾干杯，为喜玛拉雅的感受性干杯。病态的姿势爱琴海讨厌 ut 毒药。nam lobortis bibendum maximus .南狼队，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯，马西默斯。多诺 ec 毒药 sapien sed varius accumsan .多诺 EC venezuelas sapien sed various .