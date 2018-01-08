### 利用PCA来简化数据
数据显示 并非大规模特征下的唯一难题，对数据进行简化还有如下一系列的原因：

1. 使得数据集更容易使用。
2. 降低很多算法的计算开销。
3. 去除噪音。
4. 使得结果易懂。

**PCA** 主成分分析---Principal Component Analysis: 就是找出一个最主要的特征，然后进行分析。

在已标注与未标注的数据上都有降维技术，这里我们将主要关注未标注数据上的降维技术，将技术同样也可以应用于已标注的数据。

**PCA工作原理：**

1. 找出第一个主成分的方向，也就是数据 方差最大 的方向。
2. 找出第二个主成分的方向，也就是数据 方差次大 的方向，并且该方向与第一个主成分方向 正交(orthogonal 如果是二维空间就叫垂直)。
3. 通过这种方式计算出所有的主成分方向。
4. 通过数据集的协方差矩阵及其特征值分析，我们就可以得到这些主成分的值。
5. 一旦得到了协方差矩阵的特征值和特征向量，我们就可以保留最大的 N 个特征。
   这些特征向量也给出了 N 个最重要特征的真实结构，我们就可以通过将数据乘上这 N 个特征向量 从而将它转换到新的空间上。

**PCA优缺点**
- 优点：降低数据的复杂性，识别最重要的多个特征。
- 缺点：不一定需要，且可能损失有用信息。
- 适用数据类型：数值型数据

### 代码思路顺序

**pca ---> pcaDemo**

### 代码大致结构

#### pca模块：

    在Numpy中实现PCA。
    1. loadDataSet(fileName,delim='\t')
        加载数据函数
    2. pca(dataMat, topNfeat=9999999)
        PCA核心代码
    3. main
        测试PCA函数
        绘制图像观察
     
#### pcaDemo模块：
    
    处理大规模特征数据集案例
    1. replaceNanWithMean(datMat)
        把数据集中所有的NAN替换为平均值
    2. main
        运行，测试，观察