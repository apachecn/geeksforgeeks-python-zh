# 冠助纣

> 原文:[https://www.geeksforgeeks.org/corona-helpbot/](https://www.geeksforgeeks.org/corona-helpbot/)

这是一个聊天机器人，可以回答你大多数与电晕相关的问题。聊天机器人将根据世卫组织提供的数据(https://www.who.int/)给你答案。这将帮助那些需要信息或帮助的人更多地了解这种病毒。

它使用一个具有两个隐藏层的神经网络(对于这些 QnA 来说足够了)，可以预测哪种模式与用户的问题相匹配，并将其发送到该节点。可以从用户的问题中添加更多的模式来训练它，以获得更好的结果，并在 JSON 文件中添加更多关于冠状病毒的信息。你训练这个聊天机器人越多，它就越精确。使用深度学习的优势在于，您不必问与 JSON 文件中所写的相同的问题，因为来自模式的词源与用户问题相匹配

**先决条件:**

```py
Python 3
NumPy
nltk
TensorFlow v.1.15 (no GPU required)
tflearn
```

**训练数据:**
为了将数据反馈给 chatbot，我使用了带有可能的问题模式和我们想要的答案的 json。
项目使用的 json 文件是 [WHO](https://write.geeksforgeeks.org/wp-content/uploads/WHO.txt)
对于这个项目，我已经将我的 JSON 文件命名为 WHO.json
在 JSON 文件标签中是所有那些响应所属的类别。
模式用于列出所有可能的问题模式。
回答包含与模式化问题相关的所有回答

## 蟒蛇 3

```py
import nltk
import numpy
import tflearn
import tensorflow
import pickle
import random
import json
nltk.download('punkt')

from nltk.stem.lancaster import LancasterStemmer
stemmer = LancasterStemmer()

 #loading the json data
with open("WHO.json") as file:                 
    data = json.load(file)

#print(data["intents"])
try:
    with open("data.pickle", "rb") as f:
        words, l, training, output = pickle.load(f)
except:

    #  Extracting Data
    words = []
    l = []
    docs_x = []
    docs_y = []

   # converting each pattern into list of words using nltk.word_tokenizer
    for i in data["intents"]:  
        for p in i["patterns"]:
            wrds = nltk.word_tokenize(p)
            words.extend(wrds)
            docs_x.append(wrds)
            docs_y.append(i["tag"])

            if i["tag"] not in l:
                l.append(i["tag"])
    # Word Stemming           
    words = [stemmer.stem(w.lower()) for w in words if w != "?"]        
    words = sorted(list(set(words)))
    l = sorted(l)                                     

    # This code will simply create a unique list of stemmed
    # words to use in the next step of our data preprocessing
    training = []
    output = []
    out_empty = [0 for _ in range(len(l))]
    for x, doc in enumerate(docs_x):
        bag = []

        wrds = [stemmer.stem(w) for w in doc]

        for w in words:
            if w in wrds:
                bag.append(1)
            else:
                bag.append(0)
        output_row = out_empty[:]
        output_row[l.index(docs_y[x])] = 1

        training.append(bag)
        output.append(output_row)

    # Finally we will convert our training data and output to numpy arrays   
    training = numpy.array(training)       
    output = numpy.array(output)
    with open("data.pickle", "wb") as f:
        pickle.dump((words, l, training, output), f)

# Developing a Model       
tensorflow.reset_default_graph()                   

net = tflearn.input_data(shape=[None, len(training[0])])
net = tflearn.fully_connected(net, 8)
net = tflearn.fully_connected(net, 8)
net = tflearn.fully_connected(net, len(output[0]), activation="softmax")
net = tflearn.regression(net)

# remove comment to not train model after you satisfied with the accuracy
model = tflearn.DNN(net)
"""try:                              
    model.load("model.tflearn")
except:"""

# Training & Saving the Model
model.fit(training, output, n_epoch=1000, batch_size=8, show_metric=True)       
model.save("model.tflearn")

# making predictions
def bag_of_words(s, words):                               
    bag = [0 for _ in range(len(words))]

    s_words = nltk.word_tokenize(s)
    s_words = [stemmer.stem(word.lower()) for word in s_words]

    for se in s_words:
        for i, w in enumerate(words):
            if w == se:
                bag[i] = 1

    return numpy.array(bag)

def chat():
    print("""Start talking with the bot and ask your
    queries about Corona-virus(type quit to stop)!""")

    while True:
        inp = input("You: ")
        if inp.lower() == "quit":
            break

        results = model.predict([bag_of_words(inp, words)])[0]
        results_index = numpy.argmax(results)

        #print(results_index)
        tag = l[results_index]
        if results[results_index] > 0.7:
            for tg in data["intents"]:
                if tg['tag'] == tag:
                    responses = tg['responses']

            print(random.choice(responses))
        else:
            print("I am sorry but I can't understand")

chat()
```

**单词包:**
众所周知，神经网络和机器学习算法需要数字输入。所以字符串列表不会切断它。我们需要一些方法来用数字来表示我们的句子，这就是单词包的来源。我们要做的是用一个列表来表示每个句子，这个列表列出了我们的模型词汇表中单词的长度。如果列表中的位置是 1，那么这意味着这个单词存在于我们的句子中，如果它是 0，那么这个单词既不存在也不存在。

**开发模型:**

```py
model = tflearn.DNN(net)
model.fit(training, output, n_epoch=1000, batch_size=8, show_metric=True) 
model.save("model.tflearn")
```

我们的聊天机器人会根据我们训练的模型预测答案。这里我们将使用神经网络来建立模型。我们网络的目标是查看一包单词，并给出它们所属的类(JSON 文件中的一个标签)。

```py
Input: what is coronavirus ?
Output:COVID-19 is an infectious disease caused by the most recently discovered coronavirus. This new virus and disease were unknown before the outbreak began in Wuhan, China, in December 2019.

Input: what are the symptoms of COVID 19?
Output: He most common symptoms of COVID-19 are fever, tiredness, and dry cough. Some patients may have aches and pains, nasal congestion, runny nose, sore throat or diarrhea. These symptoms are usually mild and begin gradually. Some people become infected but don’t develop any symptoms and don't feel unwell. Most people (about 80%) recover from the disease without needing special treatment.
```