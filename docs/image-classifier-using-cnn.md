# 使用 CNN 的图像分类器

> 原文:[https://www.geeksforgeeks.org/image-classifier-using-cnn/](https://www.geeksforgeeks.org/image-classifier-using-cnn/)

这篇文章是关于使用 Python 中的 TFLearn 创建一个图像分类器来识别猫和狗。问题就在这里的 [kaggle](https://www.kaggle.com/c/dogs-vs-cats) 上。

**机器学习**现在是全球最热门的话题之一。嗯，甚至可以说是当今世界的新电。但是准确地说，什么是机器学习，这只是通过输入大量数据来教授机器的一种方式。要了解更多关于机器学习及其算法的知识，您可以参考本文参考部分提供的一些链接。

今天，我们将创建一个自己的图像分类器，它可以根据您的喂食数据来区分给定的图片是狗还是猫。为了实现我们的目标，我们将使用一种著名的机器学习算法，用于图像分类，即卷积神经网络。
那么基本上什么是 CNN——正如我们所知，这是一种机器学习算法，让机器有远见地理解图像的特征，并记住这些特征来猜测新图像的名称是否被输入到机器中。因为这不是一篇解释美国有线电视新闻网的文章，所以如果你们对美国有线电视新闻网的工作和行为感兴趣，我会在最后添加一些链接。
所以在经历了所有这些环节之后，让我们看看如何创建我们自己的猫对狗图像分类器。对于数据集，我们将使用猫对狗的卡格尔数据集:

*   训练数据集- [链接](https://www.kaggle.com/c/dogs-vs-cats/download/train.zip)
*   测试数据集- [链接](https://www.kaggle.com/c/dogs-vs-cats/download/test.zip)

现在，在获得数据集之后，我们需要对数据进行一点预处理，并为训练数据集期间给定的每个图像提供标签。为此，我们可以看到训练数据集的每个图像的名称都以“猫”或“狗”开头，因此我们将利用这一点，然后我们使用机器的一个热编码器来理解标签(猫[1，0]或狗[0，1])。

```py
def label_img(img):
    word_label = img.split('.')[-3]

 # DIY One hot encoder
    if word_label == 'cat': return [1, 0]
    elif word_label == 'dog': return [0, 1]
```

**所需库:**

*   **TF learn**–深度学习库，具有更高级别的 TensorFlow 应用编程接口，用于创建我们的 CNN 图层
*   **tqdm**–为了简单的设计，立即让你的循环显示智能进度计
*   [**numpy**](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/)–处理图像矩阵
*   **open-cv**–处理图像，如将其转换为灰度等。
*   **OS**–访问文件系统，从火车上读取图像，从我们的机器上读取测试目录
*   **随机**–对数据进行混洗以克服偏差
*   **matplotlib**–显示我们预测结果的结果。
*   **张量流**–只是为了使用张量板来比较损失和亚当曲线我们的结果数据或获得的日志。

TRAIN_DIR 和 TEST_DIR 应根据用户方便程度进行设置，玩转历元、学习速率等基本超参数，以提高准确率。我已经把图像转换成灰度，这样我们就只需要处理二维矩阵，否则三维矩阵很难直接应用到有线电视新闻网，尤其是不建议初学者使用。下面是大量评论的代码，或者你可以从这个[链接](https://github.com/Subhajit135/Image-Classifier-ConvNet-in-Cats-Dog-dataset)在我的 GitHub 账号中找到代码。

## 蟒蛇 3

```py
# Python program to create
# Image Classifier using CNN

# Importing the required libraries
import cv2
import os
import numpy as np
from random import shuffle
from tqdm import tqdm

'''Setting up the env'''

TRAIN_DIR = 'E:/dataset / Cats_vs_Dogs / train'
TEST_DIR = 'E:/dataset / Cats_vs_Dogs / test1'
IMG_SIZE = 50
LR = 1e-3

'''Setting up the model which will help with tensorflow models'''
MODEL_NAME = 'dogsvscats-{}-{}.model'.format(LR, '6conv-basic')

'''Labelling the dataset'''
def label_img(img):
    word_label = img.split('.')[-3]
    # DIY One hot encoder
    if word_label == 'cat': return [1, 0]
    elif word_label == 'dog': return [0, 1]

'''Creating the training data'''
def create_train_data():
    # Creating an empty list where we should store the training data
    # after a little preprocessing of the data
    training_data = []

    # tqdm is only used for interactive loading
    # loading the training data
    for img in tqdm(os.listdir(TRAIN_DIR)):

        # labeling the images
        label = label_img(img)

        path = os.path.join(TRAIN_DIR, img)

        # loading the image from the path and then converting them into
        # grayscale for easier covnet prob
        img = cv2.imread(path, cv2.IMREAD_GRAYSCALE)

        # resizing the image for processing them in the covnet
        img = cv2.resize(img, (IMG_SIZE, IMG_SIZE))

        # final step-forming the training data list with numpy array of the images
        training_data.append([np.array(img), np.array(label)])

    # shuffling of the training data to preserve the random state of our data
    shuffle(training_data)

    # saving our trained data for further uses if required
    np.save('train_data.npy', training_data)
    return training_data

'''Processing the given test data'''
# Almost same as processing the training data but
# we dont have to label it.
def process_test_data():
    testing_data = []
    for img in tqdm(os.listdir(TEST_DIR)):
        path = os.path.join(TEST_DIR, img)
        img_num = img.split('.')[0]
        img = cv2.imread(path, cv2.IMREAD_GRAYSCALE)
        img = cv2.resize(img, (IMG_SIZE, IMG_SIZE))
        testing_data.append([np.array(img), img_num])

    shuffle(testing_data)
    np.save('test_data.npy', testing_data)
    return testing_data

'''Running the training and the testing in the dataset for our model'''
train_data = create_train_data()
test_data = process_test_data()

# train_data = np.load('train_data.npy')
# test_data = np.load('test_data.npy')
'''Creating the neural network using tensorflow'''
# Importing the required libraries
import tflearn
from tflearn.layers.conv import conv_2d, max_pool_2d
from tflearn.layers.core import input_data, dropout, fully_connected
from tflearn.layers.estimator import regression

import tensorflow as tf
tf.reset_default_graph()
convnet = input_data(shape =[None, IMG_SIZE, IMG_SIZE, 1], name ='input')

convnet = conv_2d(convnet, 32, 5, activation ='relu')
convnet = max_pool_2d(convnet, 5)

convnet = conv_2d(convnet, 64, 5, activation ='relu')
convnet = max_pool_2d(convnet, 5)

convnet = conv_2d(convnet, 128, 5, activation ='relu')
convnet = max_pool_2d(convnet, 5)

convnet = conv_2d(convnet, 64, 5, activation ='relu')
convnet = max_pool_2d(convnet, 5)

convnet = conv_2d(convnet, 32, 5, activation ='relu')
convnet = max_pool_2d(convnet, 5)

convnet = fully_connected(convnet, 1024, activation ='relu')
convnet = dropout(convnet, 0.8)

convnet = fully_connected(convnet, 2, activation ='softmax')
convnet = regression(convnet, optimizer ='adam', learning_rate = LR,
      loss ='categorical_crossentropy', name ='targets')

model = tflearn.DNN(convnet, tensorboard_dir ='log')

# Splitting the testing data and training data
train = train_data[:-500]
test = train_data[-500:]

'''Setting up the features and labels'''
# X-Features & Y-Labels

X = np.array([i[0] for i in train]).reshape(-1, IMG_SIZE, IMG_SIZE, 1)
Y = [i[1] for i in train]
test_x = np.array([i[0] for i in test]).reshape(-1, IMG_SIZE, IMG_SIZE, 1)
test_y = [i[1] for i in test]

'''Fitting the data into our model'''
# epoch = 5 taken
model.fit({'input': X}, {'targets': Y}, n_epoch = 5,
    validation_set =({'input': test_x}, {'targets': test_y}),
    snapshot_step = 500, show_metric = True, run_id = MODEL_NAME)
model.save(MODEL_NAME)

'''Testing the data'''
import matplotlib.pyplot as plt
# if you need to create the data:
# test_data = process_test_data()
# if you already have some saved:
test_data = np.load('test_data.npy')

fig = plt.figure()

for num, data in enumerate(test_data[:20]):
    # cat: [1, 0]
    # dog: [0, 1]

    img_num = data[1]
    img_data = data[0]

    y = fig.add_subplot(4, 5, num + 1)
    orig = img_data
    data = img_data.reshape(IMG_SIZE, IMG_SIZE, 1)

    # model_out = model.predict([data])[0]
    model_out = model.predict([data])[0]

    if np.argmax(model_out) == 1: str_label ='Dog'
    else: str_label ='Cat'

    y.imshow(orig, cmap ='gray')
    plt.title(str_label)
    y.axes.get_xaxis().set_visible(False)
    y.axes.get_yaxis().set_visible(False)
plt.show()
```

输出图像将不是很清晰，因为所有图像都减少到 50X50，以便机器在速度和损失之间进行权衡后快速处理。
要访问张量板，请在您的 cmd(Windows 用户)中使用以下命令。

```py
tensorboard --logdir=foo:C:\Users\knapseck\Desktop\Dev\Cov_Net\log
```

**输出:**

<video class="wp-video-shortcode" id="video-168576-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2017-12-22-at-02-20-02.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/2017-12-22-at-02-20-02.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2017-12-22-at-02-20-02.mp4)</video>

机器学习初学者参考链接:

*   [机器学习极客 forGeeks](https://www.geeksforgeeks.org/getting-started-machine-learning/)
*   [Siraj Raval–YouTube](https://www.youtube.com/channel/UCWN3xxRkmTPmbKwht9FuE5A)
*   [Coursera 上的吴恩达机器学习课程](https://www.coursera.org/learn/machine-learning)
*   机器学习:凯文·墨菲的概率方法
*   机器学习 Reddit 社区。

**美国有线电视新闻网参考链接:**

*   Jupyter 笔记型电脑-[conv _ net](https://github.com/Subhajit135/Convolutional_neural_network)
*   维基百科–[卷积神经网络](https://en.wikipedia.org/wiki/Convolutional_neural_network)
*   斯坦福课程–[cs 231n](http://cs231n.stanford.edu/)