# 使用 FER 的面部表情识别器–使用深度神经网络

> 原文:[https://www . geesforgeks . org/面部表情识别器-使用-fer-使用-深层神经网络/](https://www.geeksforgeeks.org/facial-expression-recognizer-using-fer-using-deep-neural-net/)

在日常生活中，我们会有意或无意地进行不同类型的面部表情。这些动作传达了人类的情感状态。

我们可以通过下一个人的面部表情来判断他的情绪和精神状态。二十世纪初，埃克曼和弗里森定义了“六种”基本情绪。

这个表达不会随着文化而改变，它们是普遍的。六个面部表情是:-

*   快乐
*   悲哀
*   害怕
*   愤怒
*   惊喜
*   厌恶

在本文中，我将分享如何使用 python 中的“FER”库来构建面部表情识别器。

#### FER 图书馆:

面部表情识别库由 [Justin Shenk](//pypi.org/user/jshenk)) 开发。该库需要在系统中安装 *OpenCV > =3.2* 和 *Tensorflow > =1.7.0* 依赖项。使用 OpenCV 的哈尔级联分类器检测人脸。更多信息和 FER 图书馆的源代码，可以访问 [FER 的 GitHub 页面。](//github.com/justinshenk/fer))

#### 设置我们的代码！

对于本文，您可以使用名为 [Repl.it](//repl.it/site/about)) 的在线代码编辑器，也可以使用您最喜欢的代码编辑器。它可以通过安装

```
pip:`$ pip install fer`
```

1.使用以下代码编辑新的“main.py”文件:

## 蟒蛇 3

```
import cv2

from fer import FER

import matplotlib.pyplot as plt

import matplotlib.image as mpimg
```

上面的代码说:

*   导入完成` *cv2* `俗称打开 cv 库。它为我们提供了各种计算机视觉解决方案。我们将主要使用这个库来阅读和操作图像。你可以在上阅读更多关于[开放简历库的信息](//opencv.org/about/))
*   从 *FER* 库中导入【fer】函数。这是我们将在本次研讨会中使用的主库。
*   添加` *matplotlib.pyplot* 模块为` *plt* `。它将帮助我们绘制图表
*   包括“matplotlib.image”模块作为“T0”mpimg。matplotlib 库的 [matplotlib.image](//matplotlib.org/tutorials/introductory/images.html)) 用于在带有“x”和“y”轴的图形上绘制图像。

2.接下来，我们将通过给出输入图像来预测静态图像的情绪:

## 蟒蛇 3

```
# Input Image
input_image = cv2.imread("smile.jpg")
emotion_detector = FER()
# Output image's information
print(emotion_detector.detect_emotions(input_image))
```

![](img/26fc98b467315baa0b17ffa561f6e1ba.png)

输入图像

试着理解上面的代码想要表达的意思。以下是上述代码的解释:

*   我们的` *image* '变量通过使用` *cv2.imread("abc.jpg")* 方法从指定文件`*abc.jpg*'加载图像。
*   接下来，我们将把之前导入的` *FER()* 分配给** *探测器* **变量。
*   以“*detector . detect _ emotions(image)*”为参数的打印语法将返回边界框符号的字典。

以下是示例输出:

## 蟒蛇 3

```
[{'box': [277, 90, 48, 63], 'emotions': {
  'angry': 0.02, 'disgust': 0.0, 'fear': 0.05,
  'happy': 0.16, 'neutral': 0.09, 'sad': 0.27, 'surprise': 0.41}]
```

#### 引擎盖下发生了什么？？？

“检测器”是我们代码的主要部分。让我们看看探测器的功能:

探测器是为存储“FER”()而创建的对象。检测器返回边界框符号的有序字典。它观察并检测脸部所处的位置，并将其分为从“0”到“1”的十进制值，分别代表所有 6 种情绪。FER 展示了用美国有线电视新闻网或众所周知的卷积神经网络建立的喀拉斯模型。它将值存储在“HDF5”模型中。默认情况下，FER 使用 OpenCV 的哈尔级联分类器检测人脸。或者，我们可以使用更先进的多级联卷积网络，简称“MTCNN”。它将在后端使用 Peltarion API 来代替 Keras 模型。默认情况下，FER 使用美国有线电视新闻网，但如果我们想使用先进的美国有线电视新闻网，只需在 FER 括号中传递`*美国有线电视新闻网=真*,就像`*探测器= FER(美国有线电视新闻网=真)*`。为了进一步使用，我们将使用 MTCNN 模型来获得更准确的结果。

**数据:**

数据被称为 21 世纪的新石油。我们可以用上面生成的数据做不同的事情，最后我们将在“黑客部分”讨论，敬请关注。我们将存储情感和检测到的面部。然后在检测到的人脸周围显示黄色边框，并在下面打分。下面让我们看看如何做到这一点。

## 蟒蛇 3

```
import cv2
from fer import FER
import matplotlib.pyplot as plt
import matplotlib.image as mpimg
input_image = cv2.imread("smile.jpg")
emotion_detector = FER(mtcnn=True)
```

直到现在我们已经到达这里。

接下来，我们将声明新的变量“result”，并将我们的输出存储在一个单独的数组中。

## 蟒蛇 3

```
# Save output in result variable
result = emotion_detector.detect_emotions(input_image)
```

#### 现在是时候突出显示面部周围的黄色边框了:

## 蟒蛇 3

```
bounding_box = result[0]["box"]
emotions = result[0]["emotions"]
cv2.rectangle(input_image,(
  bounding_box[0], bounding_box[1]),(
  bounding_box[0] + bounding_box[2], bounding_box[1] + bounding_box[3]),
              (0, 155, 255), 2,)
```

上述代码的解释是:

*   “边界框”变量将存储生成并存储在“结果”变量中的边界框坐标。它将从“盒子”键的第 0 个元素(或通用语言中的第一个元素)开始访问和存储。如果你打印这个变量，你会得到类似这样的输出`(298，361，825，825)`。
*   与“情绪”变量相同，它将访问“结果”，并从“情绪”键的第“0”个元素开始存储。如果您打印，您将获得输出为` { '愤怒':0.08，'厌恶':0.03，'恐惧':0.05，'快乐':0.09，'悲伤':0.35，'惊讶':0.0，'中性':0.38 ' '
*   ` cv2.rectangle()'方法用于在检测到的人脸周围绘制一个矩形。它以“输入图像、起点、终点、颜色、厚度”为参数。
*   在我们的例子中，我们使用“图像”作为“图像”的参数来指定我们将要使用的图像。` start _ point ` as `(bounding_box[0]，bounding_box[1])，其中` bounding _ box[0]'是起点的 X 坐标，` bounding_box[1]'是起点的 Y 坐标。
*   下一个“end_point”为`(bounding _ box[0]+bounding _ box[2]，bounding _ box[1]+bounding _ box[3])，其中` ` bounding _ box[0]+bounding _ box[2]'是 X 坐标,` bounding _ box[1]+bounding _ box[3]'是端点的 Y 坐标。
*   * `(0，155，255)` `是我们要用作盒子颜色的黄色。
*   *“厚度”表示为“2”。定义 2px 到 box 的厚度。

#### 向边界框添加分数

现在，我们将使用以下代码向边界框添加分数:

## 蟒蛇 3

```
emotion_name, score = emotion_detector.top_emotion(image )
for index, (emotion_name, score) in enumerate(emotions.items()):
   color = (211, 211,211) if score < 0.01 else (255, 0, 0)
   emotion_score = "{}: {}".format(emotion_name, "{:.2f}".format(score))

   cv2.putText(input_image,emotion_score,
               (bounding_box[0], bounding_box[1] + bounding_box[3] + 30 + index * 15),
               cv2.FONT_HERSHEY_SIMPLEX,0.5,color,1,cv2.LINE_AA,)

#Save the result in new image file
cv2.imwrite("emotion.jpg", input_image)
```

上面的代码说:

*   使用“*检测器. top_emotion(img)* ”方法将顶级情绪值存储在“emotion_name，score”变量中。
*   我们将使用一个基本的“for”循环和“enumerate”方法来遍历列表中某项的索引和值。所以现在在给定的时间重复 1 种情绪。这个过程发生 6 次，因为我们有 6 种情绪要测试。你可以看文件。
*   基于分数，颜色被分配给“颜色”变量。 **IF & Else** 语句的简写用于更好地理解代码。
*   * `emotion_score '变量存储情绪得分，并将用于打印。
*   * `cv2.putText()`方法用于在任何图像上绘制文本字符串。
*   方法将创建并保存名为“emotion.jpg”的新的最终输出图像。

#### 显示输出图像

## 蟒蛇 3

```
# Read image file using matplotlib's image module
result_image = mpimg.imread('emotion.jpg')
imgplot = plt.imshow(result_image)
# Display Output Image
plt.show()
```

我们正处于文章的最后一步。其中我们通过使用 matplotlib 库函数`*mpimg . imread(' emotion . jpg ')*'方法显示输出图像读取括号中提供的图像。使用` *plt.imshow(img)* ,将图像图像存储在` *imgplot* 。最后` *plt.show()* 将显示我们的输出图像。

![](img/ece0c86a3c28f234f9a8c5ffb94a74b9.png)

输出图像

我们的面部表情识别器只是新的和创新的 FER 系统的起点。现在是时候了，你可以通过到目前为止所学的东西来建立新的东西。以下是我的一些想法，你可以尝试一下:

1.  我们为静态图像建造了 FER。你可以试试 FER 对视频中面部情绪的视频分析。
2.  使用实时相机创建实时面部表情识别器将是一件非常令人兴奋的尝试。
3.  通过从“结果”变量中提取和处理数据，您可以基于人类的情感创建不同的推荐系统。比如向有悲伤情绪或动机的人推荐有趣的书籍、视频、礼物等，向恐惧或愤怒的人推荐书籍、视频。