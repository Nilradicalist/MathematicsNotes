# Knowledge Proficiency

* Beginner ()
* Understanding ()
* Intermediate ()
* Mastery ()

---

# Definition (What is it?)

- Logical chain/Logical flow

---

# Intuition (Why is it needed?)

- observe

- examples

- counterexamples

---

# Results (What are the most important facts and results?)

- The Idea Behind the Demonstration (Idea della Dimostrazione)

- property

- theorem

- lemma

- corollary

- other propositions

---

# Connections (How does it connect with other concepts?)



---

# Exercises (Have I genuinely learnt how to apply it?)

- classic ex

- mistake ex

1. 我再次回答上次的“封闭回忆”，只用文字概述，不输入LaTeX公式以节约时间： Ax=b中，A是系数矩阵；x是未知量列向量；b是常数项列向量；在坐标表示中，它们也可以看作只有一列的矩阵。当Ax=0的时候被称为齐次线性系统。rank(A)是系数矩阵的秩rango/rank，将矩阵化为任意一个行阶梯形后，$\operatorname{rank}(A)$ 等于主元的数量。rank(A|b)是整个完全矩阵matrice completa的秩rango，同样也等于主元pivot的数量。当rank(A)=rank(A|b)的时候，线性系统相容，此时若未知数数量n>r（也就是秩）则有自由变量有n-r个，解的数量也会由n-r决定，若n=r，则只有一个解；当rank(A)<rank(A|b)的时候，线性系统不相容且无解。

(i) 我的解答：

Dal sistema lineare si ottiene:
$$
\begin{pmatrix}
0&\alpha-1&1\\
-1&\alpha&1\\
1-\alpha&\alpha-1&\alpha
\end{pmatrix}
$$
Calcoliamo il determinante sviluppando lungo la prima riga:

$det(A_{\alpha})=-a_{12}det(M_{12})+a_{13}det(M_{13})=\alpha(\alpha-1)$

Se $\det(A_\alpha)\neq 0$, il sistema ammette un’unica soluzione. Restano quindi da esaminare i valori per cui $\det(A_\alpha)=0$.

I valori critici sono $\alpha=0 \lor \alpha=1$

Per $\alpha=1$,

si ottiene
$$
\begin{pmatrix}
0&0&1&3\\
-1&1&1&2\\
0&0&1&2 \\
\end{pmatrix}
\xrightarrow{\text{Eliminazione di Gauss}}
\begin{pmatrix}
0&0&1&3\\
-1&1&1&2\\
0&0&0&1 \\
\end{pmatrix}
$$

Sappiamo che $\operatorname{rank}(A_{\alpha})=2<\operatorname{rank}(A_{\alpha}|b)=3$, il sistema è incompatibile e l’insieme delle soluzioni è vuoto.

Per $\alpha=0$,

si ottiene
$$
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
1&-1&0&1 \\
\end{pmatrix}
\xrightarrow{\text{Eliminazione di Gauss}}
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
0&0&0&0 \\
\end{pmatrix}
$$
Sappiamo che $\operatorname{rank}(A_{\alpha})=\operatorname{rank}(A_{\alpha}|b)=2$. Poiché $n-r=3-2=1$, vi è una variabile libera; pertanto il sistema ammette più di una soluzione.
Il sistema è compatibile se e solo se $\alpha\ne1$. 


(iii) 我的解答：

Per $\alpha=0$,

si ottiene
$$
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
1&-1&0&1 \\
\end{pmatrix}
\xrightarrow{\text{Eliminazione di Gauss}}
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
0&0&0&0 \\
\end{pmatrix}
$$
Quindi abbiamo:
Per $\alpha=0$,

si ottiene
$$
\begin{cases}
0x-y+z=1\\
-1x+0y+z=0
\end{cases}
$$
Risolvendo il sistema lineare, poniamo $z=t$, si ottiene:
$$
\begin{cases}
x=t\\
y=t-1\\
z=t
\end{cases}
$$
L'insieme delle soluzioni è:
$$
S=
\left\{
t
\begin{pmatrix}
1\\
1\\
1 \\
\end{pmatrix}
+
\begin{pmatrix}
0\\
-1\\
0 \\
\end{pmatrix}
\middle |
t\in k
\right\}
$$

第一个不确定的位置：暂时没有，我没有感觉到不确定的位置。

我使用了哪些判断：
- 判断rank(A) 的数量；
- 判断rank(A|b)的数量，并与rank(A)比较；
- 容易得到未知数数量 n=3；
- 视情况计算自由变量数量n-r 。

---

La matrice dei coefficienti è

$$
A_\alpha=
\begin{pmatrix}
0 & \alpha-1 & 1\\
-1 & \alpha & 1\\
1-\alpha & \alpha-1 & \alpha
\end{pmatrix}.
$$

Calcolando il determinante mediante lo sviluppo lungo la prima riga, si ottiene

$$
\det(A_\alpha)
=
-(\alpha-1)
\begin{vmatrix}
-1 & 1\\
1-\alpha & \alpha
\end{vmatrix}
+
\begin{vmatrix}
-1 & \alpha\\
1-\alpha & \alpha-1
\end{vmatrix}
=
\alpha(\alpha-1).
$$

Se $\alpha\notin\{0,1\}$, allora $\det(A_\alpha)\neq0$ e il sistema
ammette un’unica soluzione. Restano da esaminare i valori critici
$\alpha=0$ e $\alpha=1$.

Per $\alpha=1$, la matrice completa si riduce a

$$
\begin{pmatrix}
0&0&1&3\\
-1&1&1&2\\
0&0&1&2
\end{pmatrix}
\sim
\begin{pmatrix}
0&0&1&3\\
-1&1&1&2\\
0&0&0&1
\end{pmatrix}.
$$

Pertanto

$$
\operatorname{rank}(A_1)=2
<
3=\operatorname{rank}(A_1\mid b_1),
$$

quindi, per il teorema di Rouché-Capelli, il sistema è incompatibile.

Per $\alpha=0$, si ha

$$
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
1&-1&0&1
\end{pmatrix}
\sim
\begin{pmatrix}
0&-1&1&1\\
-1&0&1&0\\
0&0&0&0
\end{pmatrix}.
$$

Dunque

$$
\operatorname{rank}(A_0)
=
\operatorname{rank}(A_0\mid b_0)
=
2.
$$

Il sistema è quindi compatibile e, poiché $2<3$, ammette più di una
soluzione.

In conclusione, il sistema è compatibile se e solo se

$$
\boxed{\alpha\neq1}.
$$

---

Rouché–Capelli 的意大利语陈述：
Il sistema lineare $Ax=b$ è compatibile se e solo se

$$
\operatorname{rank}(A)=\operatorname{rank}(A\mid b).
$$

Se invece

$$
\operatorname{rank}(A)<\operatorname{rank}(A\mid b),
$$

il sistema è incompatibile.

Supponiamo ora che il sistema sia compatibile e poniamo

$$
\operatorname{rank}(A)=\operatorname{rank}(A\mid b)=r.
$$

Se $r=n$, dove $n$ è il numero delle incognite, il sistema ammette
un’unica soluzione.

Se $r<n$, il sistema ammette più di una soluzione e ha $n-r$
variabili libere.

(i) 我的解答：
La matrice dei coefficienti è $(A_{k})$
$$
(A_{k})= 
\begin{pmatrix}
1 & 1 & 1  \\
1 & k & 1  \\
1 & -1 & -k  \\
\end{pmatrix}, \quad 
$$

Calcolando il determinante mediante lo sviluppo lungo la prima colonna, si ottiene

$det(A_{k}) = a_{11}det(M_{11})+(-a_{21})det(M_{21})+a_{31}det(M_{31}) = -k^2+1+(k-1)+(1-k) = -k^2 + 1$

Se $k\notin\{-1,1\}$, allora $\det(A_{k})\neq0$ e il sistema ammette un’unica soluzione. Restano da esaminare i valori critici $k=-1$ e $k=1$.

Per $k=1$, la matrice completa si riduce a $(A_{1}|b_{1})$
$$
(A_{1}|b_{1}) =
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & 1 & 1 & 1 \\
1 & -1 & -1 & 1 \\
\end{pmatrix}
\sim
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 \\
2 & 0 & 0 & 2 \\
\end{pmatrix}
$$

Pertanto
$$
\operatorname{rank}(A_1)=\operatorname{rank}(A_1\mid b_1)=2
$$
Per il teorema di Rouché-Capelli, il sistema è quindi compatibile e, poiché $2<3$, ammette più di una soluzione.

Per $k=-1$, la matrice completa si riduce a $(A_{-1}|b_{-1})$
$$
(A_{-1}|b_{-1}) =
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & -1 & 1 & 1 \\
1 & -1 & 1 & -1 \\
\end{pmatrix}
\sim
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & -2 & 0 & 0 \\
0 & 2 & 0 & 2 \\
\end{pmatrix}
$$
quindi $\operatorname{rank}(A_{-1})=2,\quad \operatorname{rank}(A_{-1}\mid b_{-1})=3$, per il teorema di Rouché-Capelli, il sistema è incompatibile.

In conclusione, il sistema è compatibile se e solo se $k\ne-1$ .

(ii) 我的解答： 

Caso 1:

Per $k=1$, la matrice completa si riduce a $(A_{1}|b_{1})$
$$
(A_{1}|b_{1}) =
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & 1 & 1 & 1 \\
1 & -1 & -1 & 1 \\
\end{pmatrix}
\sim
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & 0 & 0 & 0 \\
2 & 0 & 0 & 2 \\
\end{pmatrix}
$$
quindi,
$$
\begin{cases}
x + y + z = 1 \\
0x + 0y + 0z = 0 \\
2x + 0y + 0z = 2
\end{cases}
$$

quindi,
$$
\begin{cases}
x + y + z = 1 \\
2x = 2
\end{cases}
\implies
\begin{cases}
1 + y + z = 1 \\
x = 1
\end{cases}
\text{poniamo} \quad z=t \quad
\text{si ottiene l´insieme delle soluzioni} \quad
\begin{cases}
1 + y + t = 1 \\
x = 1 \\
y = -t \\
z = t \\
\end{cases},
$$
$$
S = 
\left\{
\begin{pmatrix}
1\\
0\\
0
\end{pmatrix}
+
t
\begin{pmatrix}
0\\
-1\\
1
\end{pmatrix}
\middle |
t\in\mathbb{Q}
\right\}
$$

Caso 2:

Per $k \ne \pm1$, abbiamo la matrice generale $(A_{k}|b_{k})$
$$
(A_{k}|b_{k}) =
\begin{pmatrix}
1 & 1 & 1 & 1 \\
1 & k & 1 & 1 \\
1 & -1 & -k & k \\
\end{pmatrix}
\sim
\begin{pmatrix}
1 & 1 & 1 & 1 \\
0 & k-1 & 0 & 0 \\
2 & 0 & 1-k & k+1 \\
\end{pmatrix}
$$
quindi,
$$
\begin{cases}
x + y + z = 1 \\
0x + (k-1)y + 0z = 0 \\
2x + 0y + (1-k)z = k+1
\end{cases}
$$
$$
\begin{cases}
x + 0 + z = 1 \\
(k-1)y = 0 \\
2x + (1-k)z = k+1\\
\end{cases}
\implies
\begin{cases}
x + 0 + z = 1 \\
y = 0 \\
2x + (1-k)z = k+1 \\
\end{cases}
$$
$$
\text{abbiamo l´insieme dei soluzioni} \quad
\begin{cases}
x = \frac{2k}{1+k} \\
y = 0 \\
z = \frac{1-k}{1+k} \\
\end{cases}
\implies
S = 
\left\{
\begin{pmatrix}
\frac{2k}{1+k}\\
0\\
\frac{1-k}{1+k}
\end{pmatrix}
\right\}
$$

(iii) 我设的一般常数项与完全矩阵：

Sia

$$
\widetilde b=
\begin{pmatrix}
\alpha\\
\beta\\
\gamma
\end{pmatrix}
\in\mathbb Q^3
$$

un termine noto arbitrario. Per $k=-1$, la matrice completa del
nuovo sistema è

$$
\left(A_{-1}\mid\widetilde b\right)
=
\begin{pmatrix}
1&1&1&\alpha\\
1&-1&1&\beta\\
1&-1&1&\gamma
\end{pmatrix}.
$$



---

# 总体判断

你的 Rouché–Capelli 陈述已经正确；第 (i)、(ii) 问的数学结论也正确。现在真正需要解决的是第 (iii) 问的**题意解析和量词结构**。

你目前写出的

$$
\widetilde b=
\begin{pmatrix}
\alpha\
\beta\
\gamma
\end{pmatrix},
\qquad
(A_{-1}\mid\widetilde b)
========================

\begin{pmatrix}
1&1&1&\alpha\
1&-1&1&\beta\
1&-1&1&\gamma
\end{pmatrix}
$$

是正确的建模，但还没有完成“确定所有且仅有的常数项”。

---

# 一、第 (iii) 问的意大利语究竟说了什么

原题是：

> *Per i valori di (k) per cui il sistema è incompatibile, determinare tutti e soli i termini noti che rendono compatibile il sistema la cui matrice dei coefficienti è (A_k).*

可以分成四层：

```text
Per i valori di k
    per cui il sistema è incompatibile,

determinare
    tutti e soli i termini noti

che rendono compatibile
    il sistema

la cui matrice dei coefficienti è A_k.
```

逐层翻译：

1. **Per i valori di (k) per cui il sistema è incompatibile**
   对于那些使原系统不相容的 (k) 值。

   第 (i) 问已经告诉我们，这里只有

   $$
   k=-1.
   $$

2. **determinare tutti e soli i termini noti**
   确定所有且仅有的常数项。

3. **che rendono compatibile il sistema**
   它们能够使系统相容。

   这里的 **rendono** 就是“使……成为”的意思。它表明我们正在改变或选择新的常数项。

4. **la cui matrice dei coefficienti è (A_k)**
   该系统的系数矩阵是 (A_k)。

因此，题目没有使用 *mantenere invariata*（保持不变）这个词，但它已经通过

> *il sistema la cui matrice dei coefficienti è (A_k)*

明确指定：新系统的系数矩阵仍然是 (A_k)。

结合第一个从句，这里就是：

$$
\boxed{
\text{固定 }k=-1\text{ 和系数矩阵 }A_{-1},
\text{改变常数项，找出哪些常数项使系统相容。}
}
$$

6月23日试卷第 (iii) 问的原文确实使用了上述结构；同页第 (i) 问先确定不相容参数，第 (iii) 问再对这些参数研究新的常数项。

---

# 二、为什么可以设一般常数项 ((\alpha,\beta,\gamma)^T)

系数矩阵 (A_{-1}) 有三行，因此与它匹配的任何常数项都必须是 (\mathbb Q^3) 中的列向量。

而每一个 (\mathbb Q^3) 中的向量都可以唯一写成

$$
\begin{pmatrix}
\alpha\
\beta\
\gamma
\end{pmatrix},
\qquad
\alpha,\beta,\gamma\in\mathbb Q.
$$

所以设

$$
\widetilde b=
\begin{pmatrix}
\alpha\
\beta\
\gamma
\end{pmatrix}
$$

不是“随意猜了三个未知量”，而是在表示：

> 取 (\mathbb Q^3) 中任意一个可能的常数项。

这里 (\alpha,\beta,\gamma) 是这个候选常数项的三个坐标。

---

# 三、是不是 (x) 和 (b) 都未知，因此无法求解？

这里有两个层次，必须分开。

## 普通方程组问题

平常给定 (A) 和 (b)，求所有 (x)：

$$
Ax=b.
$$

此时：

* (A) 固定；
* (b) 固定；
* (x) 是未知量。

## 第 (iii) 问

现在 (A_{-1}) 固定，但 (b) 尚未指定。问题不是要求求一个固定的 (x)，而是问：

> 哪些 (b\in\mathbb Q^3) 至少对应一个 (x\in\mathbb Q^3)，使得
> (A_{-1}x=b)？

用量词写就是：

$$
\boxed{
\left{
b\in\mathbb Q^3
;\middle|;
\exists x\in\mathbb Q^3,\ A_{-1}x=b
\right}.
}
$$

所以并不是要同时求出一个唯一的 (x) 和一个唯一的 (b)，而是在分类所有可能的 (b)。

课程日志之后把这个集合称为线性映射 (L_A) 的像，也就是矩阵列向量生成的空间，并陈述：

$$
Ax=b\text{ 相容}
\quad\Longleftrightarrow\quad
b\in\operatorname{Im}(L_A).
$$



你目前尚未正式学习像和列空间，所以现在可以只用高斯消元理解。

---

# 四、用高斯消元完成第 (iii) 问

固定

$$
k=-1.
$$

设任意候选常数项为

$$
\widetilde b=
\begin{pmatrix}
\alpha\
\beta\
\gamma
\end{pmatrix}
\in\mathbb Q^3.
$$

新的完全矩阵是

$$
\left(A_{-1}\mid\widetilde b\right)
===================================

\begin{pmatrix}
1&1&1&\alpha\
1&-1&1&\beta\
1&-1&1&\gamma
\end{pmatrix}.
$$

作行变换

$$
R_2\leftarrow R_2-R_1,
\qquad
R_3\leftarrow R_3-R_1,
$$

得到

$$
\begin{pmatrix}
1&1&1&\alpha\
0&-2&0&\beta-\alpha\
0&-2&0&\gamma-\alpha
\end{pmatrix}.
$$

再作

$$
R_3\leftarrow R_3-R_2,
$$

得到

$$
\begin{pmatrix}
1&1&1&\alpha\
0&-2&0&\beta-\alpha\
0&0&0&\gamma-\beta
\end{pmatrix}.
$$

最后一行表示

$$
0=\gamma-\beta.
$$

因此系统相容当且仅当

$$
\gamma-\beta=0,
$$

也就是

$$
\boxed{\beta=\gamma}.
$$

所以所有且仅有的相容常数项是

$$
\boxed{
\widetilde b=
\begin{pmatrix}
\alpha\
\beta\
\beta
\end{pmatrix},
\qquad
\alpha,\beta\in\mathbb Q.
}
$$

这已经是完整答案。

---

# 五、为什么参考答案写成另一种形式

试卷第4页的参考解写成

$$
\begin{pmatrix}
s+t\
s-t\
s-t
\end{pmatrix},
\qquad s,t\in\mathbb Q.
$$



它与

$$
\begin{pmatrix}
\alpha\
\beta\
\beta
\end{pmatrix}
$$

描述的是同一个集合。

一方面，令

$$
\alpha=s+t,\qquad \beta=s-t,
$$

就得到后者。

反过来，给定任意 (\alpha,\beta\in\mathbb Q)，令

$$
s=\frac{\alpha+\beta}{2},
\qquad
t=\frac{\alpha-\beta}{2},
$$

就有

$$
s+t=\alpha,\qquad s-t=\beta.
$$

所以两种写法完全等价。

---

# 六、另一个更直接的方法

取任意未知向量

$$
\begin{pmatrix}
x\
y\
z
\end{pmatrix}.
$$

计算：

$$
A_{-1}
\begin{pmatrix}
x\
y\
z
\end{pmatrix}
=============

\begin{pmatrix}
x+y+z\
x-y+z\
x-y+z
\end{pmatrix}.
$$

因此，(A_{-1}x) 的第二个坐标和第三个坐标永远相等。

所以能写成 (A_{-1}x) 的常数项必定具有形式

$$
\begin{pmatrix}
\alpha\
\beta\
\beta
\end{pmatrix}.
$$

反过来，对任意这样的向量，我们也能找到 (x,y,z)。例如令

$$
y=\frac{\alpha-\beta}{2},
\qquad
x=\frac{\alpha+\beta}{2},
\qquad
z=0,
$$

便有

$$
A_{-1}
\begin{pmatrix}
x\
y\
0
\end{pmatrix}
=============

\begin{pmatrix}
\alpha\
\beta\
\beta
\end{pmatrix}.
$$

这同时证明了“所有”和“仅有”两个方向。

---

# 七、精修后的完整考试答案

## (i)

```markdown
La matrice dei coefficienti è

$$
A_k=
\begin{pmatrix}
1&1&1\\
1&k&1\\
1&-1&-k
\end{pmatrix}.
$$

Sviluppando il determinante lungo la prima colonna, si ottiene

$$
\begin{aligned}
\det(A_k)
&=
\begin{vmatrix}
k&1\\
-1&-k
\end{vmatrix}
-
\begin{vmatrix}
1&1\\
-1&-k
\end{vmatrix}
+
\begin{vmatrix}
1&1\\
k&1
\end{vmatrix}\\
&=1-k^2.
\end{aligned}
$$

Se $k\notin\{-1,1\}$, allora $\det(A_k)\neq0$ e il sistema
ammette un’unica soluzione. Restano da esaminare i valori critici
$k=1$ e $k=-1$.

Per $k=1$,

$$
(A_1\mid b_1)
=
\begin{pmatrix}
1&1&1&1\\
1&1&1&1\\
1&-1&-1&1
\end{pmatrix}
\sim
\begin{pmatrix}
1&1&1&1\\
0&-2&-2&0\\
0&0&0&0
\end{pmatrix}.
$$

Pertanto

$$
\operatorname{rank}(A_1)
=
\operatorname{rank}(A_1\mid b_1)
=
2.
$$

Per il teorema di Rouché-Capelli, il sistema è compatibile e,
poiché $2<3$, ammette più di una soluzione.

Per $k=-1$,

$$
(A_{-1}\mid b_{-1})
=
\begin{pmatrix}
1&1&1&1\\
1&-1&1&1\\
1&-1&1&-1
\end{pmatrix}
\sim
\begin{pmatrix}
1&1&1&1\\
0&-2&0&0\\
0&0&0&-2
\end{pmatrix}.
$$

Quindi

$$
\operatorname{rank}(A_{-1})=2
<
3=\operatorname{rank}(A_{-1}\mid b_{-1}),
$$

e il sistema è incompatibile.

In conclusione, il sistema è incompatibile se e solo se

$$
\boxed{k=-1}.
$$
```

题目第 (i) 问问的是“不相容的 (k)”，因此最后写

> *il sistema è incompatibile se e solo se (k=-1)*

比写“相容当且仅当 (k\neq-1)”更直接。

---

## (ii)

```markdown
Per $k=1$, il sistema ridotto è

$$
\begin{cases}
x+y+z=1,\\
y+z=0.
\end{cases}
$$

Ponendo $z=t$, con $t\in\mathbb Q$, si ottiene

$$
x=1,\qquad y=-t,\qquad z=t.
$$

Pertanto

$$
S_1=
\left\{
\begin{pmatrix}
1\\
0\\
0
\end{pmatrix}
+
t
\begin{pmatrix}
0\\
-1\\
1
\end{pmatrix}
\;\middle|\;
t\in\mathbb Q
\right\}.
$$

Se $k\neq\pm1$, dalle operazioni

$$
R_2\leftarrow R_2-R_1,
\qquad
R_3\leftarrow R_3-R_1
$$

si ottiene

$$
\begin{pmatrix}
1&1&1&1\\
0&k-1&0&0\\
0&-2&-(k+1)&k-1
\end{pmatrix}.
$$

Poiché $k\neq1$, la seconda riga implica $y=0$. La terza riga
fornisce

$$
z=\frac{1-k}{1+k},
$$

e quindi

$$
x=1-z=\frac{2k}{1+k}.
$$

Il sistema ammette dunque l’unica soluzione

$$
\boxed{
\begin{pmatrix}
x\\
y\\
z
\end{pmatrix}
=
\begin{pmatrix}
\dfrac{2k}{1+k}\\
0\\
\dfrac{1-k}{1+k}
\end{pmatrix}
}.
$$
```

---

## (iii)

```markdown
L’unico valore di $k$ per cui il sistema originario è incompatibile
è $k=-1$.

Sia

$$
\widetilde b=
\begin{pmatrix}
\alpha\\
\beta\\
\gamma
\end{pmatrix}
\in\mathbb Q^3
$$

un termine noto arbitrario. La matrice completa del nuovo sistema è

$$
(A_{-1}\mid\widetilde b)
=
\begin{pmatrix}
1&1&1&\alpha\\
1&-1&1&\beta\\
1&-1&1&\gamma
\end{pmatrix}
\sim
\begin{pmatrix}
1&1&1&\alpha\\
0&-2&0&\beta-\alpha\\
0&0&0&\gamma-\beta
\end{pmatrix}.
$$

Per il teorema di Rouché-Capelli, il sistema è compatibile se e
solo se

$$
\gamma-\beta=0,
$$

ossia se e solo se $\gamma=\beta$.

Pertanto tutti e soli i termini noti che rendono compatibile il
sistema sono

$$
\boxed{
\left\{
\begin{pmatrix}
\alpha\\
\beta\\
\beta
\end{pmatrix}
\;\middle|\;
\alpha,\beta\in\mathbb Q
\right\}.
}
$$
```

## 当前学习状态

第 (i)、(ii) 问已经通过。第 (iii) 问暴露的不是高斯消元问题，而是一个新的阅读障碍：

> 还不熟悉“给定系数矩阵，分类所有相容常数项”这一外层问题。

请暂时记住这条识别信号：

$$
\boxed{
\text{“确定使系统相容的所有常数项”}
\Longrightarrow
\text{设一般 }b\text{，研究 }Ax=b\text{ 的相容条件。}
}
$$

这正是之后“列空间／像”的入口。


