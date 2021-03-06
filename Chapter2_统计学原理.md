## 抽样：总体/样本和误差

抽样：（1）尽可能选择优化操作前后相邻的数据，因为取优化操作前后越近的数据，就能保证假设的准确性（2）样本数据的积累不仅要看时间长短，更要看样本量大小（3）如果样本数据中出现某些特别高或者特别低的奇异值，应将其剔除

## 概率

广告数据分析中：一些常见的指标，包括点击率，转化率，流失率等都是统计意义上的概率，都是通过对一定量的样本观测得到的

注意：在相同的条件下，这一点在广告优化实践中式很难做到的，以手机百度为例，MAU高大5亿多，DAU是1亿多，这意味着，除了少部分重度用户每天都在使用外，大多数用户一个月内只有可能不到一半的时间能看到某个广告主的广告，所以，广告优化实践中我们只能尽力保证控制的部分保持稳定，如落地页，广告创意，定向等，以此来观测样本，统计概率，进行数据分析

## 概率分布

正态分布，标准正态分布

中心极限定理：（1）任何一个样本的平均值都会约等于其所在总体的平均值（2）不管总体什么分布，任意一个总体的样本均值都会围绕在总体均值周围，呈正态分布，换句话说，未来广告是否投放取决于历史数据，这个就是中心极限定理：根据样本估算未来广告效果

## 统计推断：估计
- 估计：用样本数据预估总体，比如：历史这一周的平均点击率作为样本统计量，历史和未来整体的平均点击率即为筒体参数
- 区间估计：如果同时考虑抽样误差，就是区间估计，需要设置置信水平
- 总体比例置信区间：适用于用户转化漏斗各环节的转化率估计
- 总体均值置信区间：适用于估计流量大小，比如点击量，下载量，注册量等，不可用于估计类似广告消费等认为因素较大的指标，也不可以用于估计类似CPC，CPD等二次计算指标（书本举了一个某app在360应用商店两个月的注册量数据，当单凭均值比较，很难评估优化效果是否显著的时候，抽样误差和置信区间则帮助其精益评估优化策略）

## 统计推断：假设检验
- p值：原假设成立的情况下，小概率事件发生率，利用反证法的逻辑，拒绝原假设
- 两个总体比例之差的显著性检验：https://vwo.com/ab-split-test-significance-calculator/
- 两个总体均值之差的显著性检验

## 变量间关系

如果是因果关系，首先应该用常识判断这种关系是否有现实价值，注意自变量是否发生在应变量之前，如果可能，尝试适当调整自变量，观察因变量的值是否会受到影响，即使自变量是决定变量的原因，也要意识到，是否存在没有考虑到的可能对因变量有其他影响的其他变量

## 自变量和因变量之间的关系
- 数值型变量关系：相关系数（r），回归分析（系数，判定系数R^2: y值的变化有多大比例来着x与y之间的线性变化，标准误差）
  - 比如：小米应用上商店广告优化中，竞品广告下载量和总激活量是有强相关性的（r=0.87），根据回归方程，可以知道精品广告下载量x每增加1000，总激活量y大约增加672, 平均的估计误差在1300左右，结合y的取值范围（10000-20000），这个误差比例不到10%，在总激活量的波动中，有76%可以由精品广告下载量与总激活量之间的线性关系来解释
- 分类和数值型变量关系：方差分析（书本举了一个某app在各应用商店推广渠道一个月的激活注册率分布）
