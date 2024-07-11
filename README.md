# COVID-19

#### 介绍
大数据分析课设--新冠肺炎预测---给40个州的前三天的features（以及前两天的label，即新冠确诊）预测第三天的新冠确诊。
使用了线性回归模型、多层感知机模型、循环神经网络、卷积神经网络进行预测

#### CSDN博客地址

    https://blog.csdn.net/weixin_50354282/article/details/136769262?spm=1001.2014.3001.5501

#### 数据集介绍

数据集介绍：训练数据2700例，测试数据893例（最后一列未知，需要模型预测）。

40个州（one-hot编码形式）+第一天的features+第一天label+第二天features+第二天label+第三天的features+第三天的label

第0列是id

第1-40列是40个州的one-hot编码

41-44是COVID-like illness

45-52是Behavior Indicators

53-58是Mental Health Indicators

59是最后检测结果，阳不阳

后续是第2天-第3天的特征数据，都写成列

#### 课设主要实现的内容

1、数据预处理：

        删除无用列、特征值切分、数据集划分、标准化处理、转换数据类型等，方便数据分析。

2、相关性分析特征值的选取：

        使用Pandas库（pandas）中corr()函数计算了40个州、第一天特征数据、第二天特征数据、第三天特征数据和目标变量之间的相关系数矩阵。该方法显示了每对变量之间的线性相关程度，可以理解变量之间的关系，并使用Seaborn库的heatmap函数创建热力图，分别绘制了相关系数矩阵热力图。

        通过Scikit-learn库中的f_regression函数计算特征与目标变量之间的相关性并返回了特征值与分数，然后通过Scikit-learn库中的SelectKBest类，根据指定的评分函数选择最重要的k个特征。本次实验使用SelectKBest选取了30个特征值。

        最终通过综合分析相关系数矩阵热力图与f_regression函数得到的相关性分数，选取了29个特征值进行模型训练。

3、线性回归模型

        简述了线性回归模型的原理以及公式，说明了线性回归模型是如何定义的，并详细描述了模型的训练过程，包括参数设置、模型初始化、优化器选择等，通过优化器选择和添加L1正则化优化了模型，并添加了RMSE指标，通过可视化分析进行了参数调整。

4、多层感知机模型

        简述了多层感知机模型的原理以及公式，定义了多层感知机的模型，包括三个全连接层，并详细描述了模型的训练过程，包括参数设置、模型初始化、优化器选择等，通过可视化分析进行了参数调整。

5、循环神经网络

        简述了循环神经网络模型的原理以及公式，定义了一个简单的循环神经网络模型包括一个RNN层、一个全连接层，并详细描述了模型的训练过程，包括参数设置、模型初始化、优化器选择等，通过优化器选择和特征值选取优化了模型。

6、卷积神经网络

        简述了卷积神经网络模型的原理以及公式，定义了卷积神经网络模型，包括2个卷积层，每个卷积层还包含一个最大化池，以及一个展平层，一个全连接层，并详细描述了模型的训练过程，包括参数设置、模型初始化、优化器选择等，通过优化器选择、特征值选取和添加全连接层优化了模型。
