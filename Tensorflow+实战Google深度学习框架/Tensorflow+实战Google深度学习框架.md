- 深度学习能完成这样的技术突破在于它可以自动地从海量数据中提取更加复杂且有效的特征，而高斯混合模型需要人工提取特征。
- 单词向量将每个单词表示成一个相对较低维度的向量，对于语义较近的单词，其对应的单词向量在空间上的距离也应该接近。单词语义上的相似度可以通过空间中的距离来描述

- [人脸识别数据集](http://vis-www.cs.umass.edu/lfw)
- [SVHN 长串数字数据集](http://ufldl.stanford.edu/housenumbers)
- [TIMIT 语音识别数据集](https://catalog.ldc.upenn.edu/ldc93s1)
- [WordNet 自然语言处理数据集](https://wordnet.princeton.edu)
- [ConceptNet 自然语言处理数据集](http://conceptnet5.media.mit.edu/)
- [FrameNet 自然语言处理数据集](https://framenet.icsi.berkeley.edu/fndrupal)
- [GloVe 自然语言处理数据集](http://nlp.stanford.edu/projects/glove)

# 第2章 TensorFlow 环境搭建
- 机构化数据：指的是拥有多个属性的数据。例如包含名字，ID，Email 三种不同属性的用户信息。
- 要持久化或者进行网络传输时需要将这些数据序列化。
- 序列化就是将结构化的数据编程数据流的形式，简单地说就是变成一个字符串
## 2.1 TensorFlow 的主要依赖包
### 2.1.1 Protocol Buffer
- Protocal Buffer 定义数据格式的文件一般保存在 .proto 文件中，每一个 messgae 代表了一类结构化数据。
#### Protocal Buffer 数据类型
- 布尔型
- 整数型
- 实数型
- 字符型
- 另外一个 message
#### Protocal Buffer 数据要求
- 必须的
- 可选的
- 可重复的，取值为一个列表
### 2.1.2 Bazel
#### 项目空间
- 项目空间中包含了编译一个软件所需要的源代码以及输出编译结果的软链接地址
- 一个项目空间内可以只包含一个应用
- 也可以包含多个应用
- 一个项目空间所对应的文件夹是这个项目的根目录，这个根目录需要有一个 WOEKSPACE 文件，此文件定义了对外部资源的依赖关系，空文件也合法
- Bazel 通过 BUILD文件来找到需要编译个目标。
- Bazel 的编译方式是事先定义好的。
- Bazel 对 Python 支持的编译方式只有三种：
    - py_binary：将 Python 程序编译为可执行文件
    - py_library：将Python程序编译成库函数供其他py_binary 或 py_test 调用
    - py_test：编译 Python 测试程序
- ![Bazel 工作方式](https://github.com/yyxyz/Book/blob/master/Tensorflow%2B%E5%AE%9E%E6%88%98Google%E6%B7%B1%E5%BA%A6%E5%AD%A6%E4%B9%A0%E6%A1%86%E6%9E%B6/resource/Bazel-%E5%B7%A5%E4%BD%9C%E6%96%B9%E5%BC%8F.png)

