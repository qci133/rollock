# Rollock 中文说明
在指定股票中轮动。指定股票最好是同一板块的。该算法的前提是，长期来看，同一板块不同股票的涨跌幅度是接近的。在此过程中，利用轮动获取超额收益。

## 依据
推导过程很简单，暂略。结论如下：

起初同时持有等量 a 与 b。i 时刻，将 a 全部置换为 b，j 时刻，再将 b 全部置换为 a。则总体收益为：

<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{x=1}^{i}a_x&space;&plus;&space;\sum_{x=j&plus;1}^{n}a_x&space;&plus;&space;\sum_{x=1}^{n}b_x&space;&plus;&space;\sum_{x=i&plus;1}^{j}b_x&space;=&space;2P&space;&plus;&space;(La_{i&plus;1}-Lb_{i&plus;1})&space;&plus;&space;(Lb_{j}-La_{j})" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{x=1}^{i}a_x&space;&plus;&space;\sum_{x=j&plus;1}^{n}a_x&space;&plus;&space;\sum_{x=1}^{n}b_x&space;&plus;&space;\sum_{x=i&plus;1}^{j}b_x&space;=&space;2P&space;&plus;&space;(La_{i&plus;1}-Lb_{i&plus;1})&space;&plus;&space;(Lb_{j}-La_{j})" title="\sum_{x=1}^{i}a_x + \sum_{x=j+1}^{n}a_x + \sum_{x=1}^{n}b_x + \sum_{x=i+1}^{j}b_x = 2P + (La_{i+1}-Lb_{i+1}) + (Lb_{j}-La_{j})" /></a>

也就是说，以某一时刻作为起点，当 a 的累计涨幅比 b 高一个阈值时，可将 a 置换为 b。然后当 b 累计涨幅比 a 高一个阈值时，可将 b 置换为 a。

**注意：**所谓累计涨幅，全部都要从一个固定的开始时间起进行计算。
