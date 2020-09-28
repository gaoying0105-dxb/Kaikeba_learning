#1.ALS都有哪些应用场景?
ALS交替最小二乘法，是一种协同过滤的优化算法。它能够同时考虑User和Item两个方面，可基于用户进行推荐又可基于物品进行推荐。应用于推荐系统中，可进行电影推荐,商品推荐,广告推荐等.
#2.ALS进行矩阵分解的时候，为什么可以并行化处理？
ALS进行矩阵分解时，是先固定一个矩阵X，求解另一个矩阵Y；再固定矩阵Y，求解矩阵X。以X矩阵固定，求解Y矩阵为例，假设其目标评分矩阵为A，求解是，Y矩阵的每一行都可独立求解，Y矩阵的第i行和X的计算得到A的第i行。
也就是说，对于每一步，X或Y的行或者列都是可以独立并行求解的，这样ALS就可以进行并行的计算了。
#3.梯度下降法中的批量梯度下降（BGD），随机梯度下降（SGD），和小批量梯度下降有什么区别（MBGD）？
（1）批量梯度下降：在每一次迭代时，使用所有样本进行梯度更新，优点：利用矩阵进行操作时，可并行；且能够更好的代表样本的总体，能够更好的向极值所在方向训练。缺点：样本数很大时，每次迭代都需要计算所有样本，
计算量巨大，训练过程很慢。
（2）随机梯度下降：每次迭代使用一个随机样本来对参数进行更新。优点：训练速度大大加快；缺点：准确度下降，可能会收敛到局部最优，且不易于并行实现。
（3）小批量梯度下降：每次迭代使用指定数量的样本来对参数进行更新。优点：可以大大减小收敛所需要的迭代次数，同时能使收敛结果更加接近于梯度下降的效果，并且可实现并行化；缺点是对样本批量大小的确定非常
关键，选择不当可能会带来一些问题。
#4.你阅读过和推荐系统/计算广告/预测相关的论文么？有哪些论文是你比较推荐的，可以分享到微信群中？
因为之前未进行相关领域的学习，我没有阅读过相关的论文，近期上了陈老师的课之后，才刚刚开始学习，时间有限，目前还没有能够推荐的论文。