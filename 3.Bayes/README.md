
### 朴素贝叶斯算法介绍

### 1.算法简介

朴素贝叶斯是贝叶斯决策理论的一部分。我们现在用 p1(x,y) 表示数据点 (x,y) 属于类别 1 的概率，用 p2(x,y) 表示数据点 (x,y) 属于类别 2 的概率，那么对于一个新数据点 (x,y)，可以用下面的规则来判断它的类别：

如果 p1(x,y) > p2(x,y) ，那么类别为1
如果 p2(x,y) > p1(x,y) ，那么类别为2

也就是说，我们会选择高概率对应的类别。这就是贝叶斯决策理论的核心思想，即选择具有最高概率的决策。


### 2.算法步骤

```
 提取所有文档中的词条并进行去重
 获取文档的所有类别
 计算每个类别中的文档数目
 
 对每篇训练文档: 
     对每个类别: 
         如果词条出现在文档中-->增加该词条的计数值（for循环或者矩阵相加）
         增加所有词条的计数值（此类别下词条总数）
         
 对每个类别: 
     对每个词条: 
         将该词条的数目除以总词条数目得到的条件概率(P(词条|类别))
         
 返回该文档属于每个类别的条件概率（P(类别|文档的所有词条)）
```

注意：

1.为了防止其中某个值为0，最后的乘积为0，可以将所有词的出现树初始化为1，将分母初始化为2.

2.为了防止下溢出，最后的乘积为0，可以对乘积取自然对数。F(x)与Ln(x)的曲线在相同区域内单调性一致，并在相同点上取到极值。

### 3.算法优缺点

1.优点

在数据较少的情况下仍然有效，可以处理多类别问题。

2.缺点

对于输入数据的准备方式较为敏感


### 4.算法优化

[数学之美番外篇：平凡而又神奇的贝叶斯方法](http://mindhacks.cn/2008/09/21/the-magical-bayesian-method/)



