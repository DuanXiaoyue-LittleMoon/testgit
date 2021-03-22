## Network Slimming

### Abstract

1）减小模型尺寸

2）减小运行内存

3）减小计算总量

据论文描述，大部分低秩分解/量化/二值化/权重剪枝/动态inference的方法只能解决上述一个或者两个问题

对BN层中的scaling factor采用L1 regularization，scaling factor越接近于0，对应通道越不重要，被裁减掉，不改变原本CNN的结构。

20×模型压缩量；5×计算量减少

### Network Slimming

稀疏方式：weight-level（灵活，需要专门的软硬件加速器）, kernel-level, channel-level（trade off）, layer-level（需要网络本身层数较深）。本文采用channel-level的方式

$L=\sum_{(x,y)}l(f(x,W),y)+\lambda\sum_{\gamma\in\Gamma}g(\gamma)$

where $g(s)=|s|$ 或者用smooth-L1 penalty避免non-smooth点的SGD





