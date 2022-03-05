# 微分基本形式的矩阵表达

上一节中已经提到了一个对象的矩阵表示：微分$df$可以被编码为雅可比矩阵$J$，包含$f$的一阶偏导数。它的诱导度量$g$很容易写出：

$g(u, v) = df(u) \cdot df(v) = u^TIv = (Ju)^T(Jv) = u^TJ^TJv$

也就是说度量矩阵(第一微分基本形式)可以用一个$2\times2$的矩阵描述：

$I = J^TJ$

在关于微分几何的旧书中，你可能还会看到人们谈论“$E$”、“$F$”和“$G$”，它们指的是：

$$ I = \left[ \begin{matrix} E & F \\ F & G \end{matrix} \right] $$

实际上人们可能会猜测，字母表中的第五、第六和第七个字母已经过时，正是因为它们是坐标依赖的，因此本身几乎没有几何意义。

前面我们还研究了形状算子$S: TM \to TM$：

$dN(X) = df(SX)$

第二位微分基本形式可以这样定义：

$$ II(u, v) = g(Su, v) $$

（记住，$S$对于$g$是自伴的，同样地，$II$对于它的参数u和v也是对称的。）如果我们让矩阵$S,II \in \mathbb{R}^{2\times 2}$表示这两个算子，那么：

$$ u^TIIv = u^TISv $$

即：

$$ II = IS $$

第二微分基本形式的分量用小写字母表示：

$$ II = \left[\begin{matrix} e & f \\ f & g \end{matrix} \right] $$

$$ e = N \cdot f_{xx}, f = N \cdot f_{xy}, g = N\cdot f_{yy} $$

其中$N$是曲面在$f(u,v)$处的法向量,$f_{xy}$，指的是同一点处的二阶偏导数。

现在，我们可能想停下来问问：像$IS$这样的矩阵是如何根据基的变化进行变换的？第一项$I$是双线性形式，但第二项$S$是线性映射。正如上面强调的，我们不能仅仅通过观察矩阵本身来确定答案，我们需要记住它们代表什么。在这种情况下，我们知道$IS$对应于第二基本形式，所以它应该像任何其他双线性形式一样变换，即$IS\mapsto P^{-T}ISP^{-1}$

最后，我们可以验证使用矩阵的经典几何表达式与我们之前使用微分导出的表达式是否一致。例如，法曲率的经典表达式是:

$$ k_n(u) = \frac{II(u, u)}{I(u, u)} $$

将它写成矩阵形式为：

$$ \frac{u^TIIu}{u^TIu} = \frac{u^ISu}{u^Iu} = \frac{(Ju)^T(JSu)}{(Ju)^T(Ju)} = \frac{df(u)\cdot dN(u)}{|df(u)|^2}$$

这个表达式与我们之前通过考虑嵌入在曲面中的曲线得到的表达式是一致的。