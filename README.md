# Search_Picture
基于深度学习的图像检索系统
## 思路
1. 选取图像特征

传统的检索通常采用颜色、形状、纹理、能量等，我们使用深度学习模型（vgg16, resnet50,densenet121）进行特征提取。为了简便，直接用Keras的预训练模型

2. 索引化数据集

对图像库中的每张图片抽取特征，存储在数据库中。为了简便，存到h5文件中

3. 定义相似度

常用的相似性度量有：欧氏距离、曼哈顿距离、闵可夫斯基距离、切比雪夫距离、夹角余弦等。这里采用的夹角余弦。

4. 检索

首先提取测试图片的特征，再与数据库中的向量逐一计算距离，然后排序，取相似度Top3

## 测试
- index.py: 提取图像库中每张图片的特征向量
- test.py: 给定图片进行索引

## To do list
1. 包装成Web/App
2. 性能优化：模型优化、距离计算优化、排序优化

## 参考链接
- [图像检索系列——利用深度学习实现以图搜图](https://zhuanlan.zhihu.com/p/80886534)
- [Python Numpy计算各类距离](https://blog.csdn.net/qq_19707521/article/details/78479532)
- [实现图像检索系统大概的步骤，需要用到哪方面的知识？](https://www.zhihu.com/question/25833727)


## pip 安装问题

1. 使用python3环境，并进行pip升级`pip install --upgrade pip`
2. 安装以下模块`pip install -r requirements.txt`