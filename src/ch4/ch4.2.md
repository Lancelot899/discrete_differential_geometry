# wedge算子和霍奇星算子的一些示例

为了使得这些概念具体一些，我们给出一些具体的例子。这些例子并不特别”深入“但是阐明了k向量微积分的基本运算方法。（你能在课后习题中找到更多有趣的例子）。我们将1向量$v$做用$e_1, e_2, \cdots , e_n$做坐标分解。比如在2D平面上$ v := e_1 + e_2$是一个长度为$\sqrt{2}$，和水平方向差了$45^\circ$的向量。



例1：令$u:= e_1 + 2e_2$，$v := e_1 + e_2 - e_3$是$\mathbb{R}^3$中的1向量。把他们wedge一下可得：

$$ \begin{split} u\wedge v  &= (e_1 + 2e_2) \wedge (e_1 + e_2 - e_3) \\ &= e_1 \wedge (e_1 + e_2 - e_3) + 2e_2 \wedge (e_1 + e_2 - e_3) \\ &= \underbrace{e_1 \wedge e_1}_0 + e_1 \wedge e_2 - e_1\wedge e_3 + 2e_2 \wedge e_1 +  \underbrace{2e_2 \wedge e_2}_0 - 2e_2 \wedge e_3 \\ &=e_1 \wedge e_2 - 2e_1 \wedge e_2 - e_1 \wedge e_3 - 2e_2 \wedge e_3 \\ &= -e_1 \wedge e_2 - e_1 \wedge e_3 - 2e_2 \wedge e_3 \end{split} $$

在这个运算过程中，有些值得注意的点。第一：$e_i \wedge e_i = 0$。因为两条平行的向量无法围成平行四边形。注意到我们用$-2e_1 \wedge e_2 $代替了$2e_2 \wedge e_1$，这是由于$e_1\wedge e_2$和$e_2 \wedge e_1$描述的是两个大小相同方向相反的2向量。



例2： 令$w := -e_1 \wedge e_2 - e_1 \wedge e_3 - 2e_2 \wedge e_3$，这正好是先前例子化简后的值。我们对它取霍奇星算子：

$$  \begin{split}*w &= *(-e_1 \wedge e_2 - e_1 \wedge e_3 - 2e_2 \wedge e_3) \\ &= - *(e_1 \wedge e_2) - *(e_1 \wedge e_3) -2 *(e_2 \wedge e_3) \\ &= -e_3 -(-e_2) - 2e_1 \\ &= -2e_1 + e_2 - e_3 \end{split}   $$ 

这里比较值得注意的事情是，我们使用了右手法则去定义了霍奇星作用后，向量的朝向。比如正如$e_1 \cross e_2 = e_3$，$*(e_1 \wedge e_2) = e_3$。我们会在[4.5.1](./ch4.5.1.md)节更加详细地讨论它们之间的关系。



例3：令$u:= e_1 + e_2 + e_3$，$v := e_1 + 2e_2 + 3e_3$，$w := e_1 - e_2$为$\mathbb{R}^3$中的1向量，我们需要计算$u\wedge v \wedge w$，由于wedge满足结合律，我们可以先计算$u \wedge v$或者$v \wedge w$，然后再wedge剩下那个1向量。由此：

$$ \begin{split}v \wedge w &= (e_1 + 2 e_2 + 3e_3) \wedge (e_1 - e_3) \\ &=  \underbrace{e_1 \wedge e_1}_0 - e_1 \wedge e_3 + 2e_2 \wedge e_1- 2e_2 \wedge e_3 + 3e_3 \wedge r_1 - 3  \underbrace{e_3 \wedge e_3}_0 \\ &= -2e_1 \wedge e_2 - 4e_1 \wedge e_3 - 2e_2 \wedge e_3 \end{split} $$

然后我们再和u做wedge可得：

$$ \begin{split} u \wedge (v \wedge w) &= (e_1 + e_2 + e_3) \wedge (-2 e_1 \wedge e_2 - 4 e_1 \wedge e_3 - 2 e_2 \wedge e_3) \\ &= -2 e_1 \wedge e_2 \wedge e_3 - 4e_2 \wedge e_1 \wedge e_3 - 2 e_3 \wedge e_1 \wedge e_2\\ &= -2 e_1 \wedge e_2 \wedge e_3 + 4e_1 \wedge e_2 \wedge e_3 - 2 e_1 \wedge e_2 \wedge e_3 \\ &= 0 \end{split} $$

这里这个计算，我们省略了自己和自己wedge(比如：$e_1 \wedge e_1 \wedge _2$)等于0的那些项，最后表达式中只留下了3个基向量wedge到一起的那些项(比如：$e_2 \wedge e_3 \wedge e_1$)。通过交换这些基的顺序，我们可以合并同类项，本来得到一个数值(代表大小和方向)乘以$e_1 \wedge e_2 \wedge e_3$的项，但这个特殊的问题最终算出来等于0。等于0在几何上意为着什么呢？意味着这三个1向量$u,v,w$线性相关，也就是它们围成的平行六面体体积为0.
