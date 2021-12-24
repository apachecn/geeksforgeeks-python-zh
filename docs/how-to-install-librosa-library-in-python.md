# 如何用 Python 安装 Librosa 库？

> 原文:[https://www . geesforgeks . org/how-install-librosa-library-in-python/](https://www.geeksforgeeks.org/how-to-install-librosa-library-in-python/)

Librosa 是一个用于音乐和音频分析的 Python 包。Librosa 基本上是在我们处理音频数据时使用的，比如音乐生成(使用 LSTM 的)，自动语音识别。

它为创建音乐信息检索系统提供了必要的构件。Librosa 有助于可视化音频信号，并使用不同的信号处理技术提取其中的特征。

#### 装置

*   **Using PyPI(Python Package Index)**

    打开系统上的命令提示符，并编写其中任何一个命令。

    ```py
    pip install librosa 
    sudo pip install librosa
    pip install -u librosa
    ```

    ![Install librosa using pip](img/5a9202767db7bb6b00872a37f9004b10.png)

*   **Conda Install**

    如果使用 conda/Anaconda 环境，可以从 conda-forge 通道安装 librosa。打开 Anaconda 提示符并写道:

    ```py
    conda install -c conda-forge librosa
    ```

    ![Download librosa on anaconda-1](img/8986098e8598f1eebf96406a7cab4eee.png)
    ![Download librosa on anaconda-2](img/e760687e07b561a69f3ef051e610a766.png)

    **注意:**如果在 conda 中使用 Python 3.5 环境，可能会遇到 numba 依赖的问题。这可以通过在安装 librosa 之前从 numba conda 通道安装来避免:

    ```py
    conda install -c numba numba
    ```