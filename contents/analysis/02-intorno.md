# Knowledge Proficiency

## L'intorno
* Beginner (x)
* Understanding ()
* Intermediate ()
* Mastery ()

## Punto di accumulazione
* Beginner (x)
* Understanding ()
* Intermediate ()
* Mastery ()

---

# Definition (What is it?)

## L'intorno

以$x_0$为中心、允许距离小于某个正数$\delta$的的所有的实数集合.

L’intorno di $x_0\in\mathbb R$ di ampiezza $\delta>0$ è l’intervallo aperto $(x_0-\delta, x_0+\delta)$.

## Punto di accumulazione

聚点（Punto di accumulazione; accumulation point）

Sia $A\subseteq\mathbb R$. Diremo che $x_0\in\mathbb R$ è un punto di accumulazione di $A$ se ogni intorno di $x_0$ contiene punti di $A$ distinti da $x_0$ stesso. $$\forall \delta > 0,\quad \left[ ( x_0 - \delta, x_0 + \delta ) \setminus \{ x_0 \} \right] \cap A \neq \emptyset$$
Equivalente $$\forall \delta > 0, \exists x \in A, \text{tale che} \quad 0<\left|x-x_0\right|<\delta$$

## Logical chain

要证明 $x_0$ 是 $A$ 的聚点：

1. 任取 $\delta>0$
2. 看清楚 $x\in A$ 强迫 $x$ 具有什么形式
3. 看清楚 $0 < |x-x_0| < \delta$ 对 $x$ 提出什么要求
4. 根据这些要求构造 $x$
5. 验证：
   - $x \in A$；
   - $x \neq x_0$；
   - $0 < |x-x_0| < \delta$。

要证明 $x_0$ 不是 $A$ 的聚点：

1. 找到一个 $\delta > 0$
2. 证明这个去心邻域与 $A$ 的交集为空

---

# Intuition (Why is it needed?)

## observe

### L'intorno

Semplicemente l'intorno sinsitro $(x_0-\delta, x_0)$, l'intorno destro $(x_0, x_0+\delta)$.

Sono equivalenti a $x\in(x_0-\delta, x_0+\delta),\quad 0<\left|x-x_0\right|<\delta$.

但我们注意到，sinistro intorno和destro intorno包含$x_0$，但是完整的intorno不包含$x_0$.

Quindi, abbiamo $(x_0-\delta, x_0+\delta)\setminus\{x_0\}$ senza il centro.

### Punto di accumulazione

定义的量词顺序是：

$\forall \delta > 0, \exists x \in A$

意思是：

1. 别人可以任意指定一个很小的 $\delta>0$；
2. 我们都必须能在 $A$ 中找到一个点 $x$；
3. 这个 $x$ 与 $x_0$ 不同；
4. 但它与 $x_0$ 的距离小于 $\delta$。

这里找到的 $x$ **可以依赖于 $\delta$**。

## conterexample

### 定义中的 $A$ 到底是什么？

你目前的理解需要修正一个关键点：

> **聚点不是邻域中任意选出的那个 $x$。聚点是正在被检查的中心 $x_0$。**

定义是：

$$
x_0\text{ 是 }A\text{ 的聚点}
$$

当且仅当

$$
\forall\delta>0\ \exists x\in A:
0<|x-x_0|<\delta.
$$

教材的原始表述是：$x_0$ 是 $A$ 的聚点，当且仅当 $x_0$ 的每一个邻域都包含某个属于 $A$ 且不同于 $x_0$ 的点。

这里四个对象的职责不同：

| 对象       | 作用                     |
| -------- | ---------------------- |
| $A$      | 我们正在研究的集合              |
| $x_0$    | 候选聚点，即被检查的中心           |
| $\delta$ | 邻域的大小，可以任意小            |
| $x$      | 在 $A$ 中找到的、靠近 $x_0$ 的点 |

### 邻域和 $A$ 分别控制什么？

邻域

$$
(x_0-\delta,x_0+\delta)
$$

告诉我们：

> **到哪里寻找。**

集合 $A$ 告诉我们：

> **哪些点才算有效。**

所以定义实际是在问：

> 无论把以 $x_0$ 为中心的观察窗口缩得多小，窗口中是否总能找到一个属于 $A$、并且不同于 $x_0$ 的点？

数学式就是：

$$
\underbrace{
\bigl[(x_0-\delta,x_0+\delta)\setminus{x_0}\bigr]
}*{\text{寻找的区域}}
\cap
\underbrace{A}*{\text{允许使用的点}}
\neq\varnothing.
$$

---

### 为什么不能删掉 $A$？

假如没有 $A$，只要求：

> 每个 $x_0$ 的邻域里都有一个不同于 $x_0$ 的实数。

那么这对每个实数 $x_0$ 都显然成立。例如在任意 $\delta>0$ 下，总可以选

$$
x=x_0+\frac{\delta}{2}.
$$

这样“聚点”就无法区分不同的集合，概念也就失去了作用。

真正有意义的问题是：

> $x_0$ 附近是否有 **集合 $A$ 的点**？

例如都检查 $x_0=0$。

#### 情形一

$$
A=\mathbb R.
$$

任意小的邻域里都有大量属于 $\mathbb R$ 的非零点，所以 $0$ 是 $\mathbb R$ 的聚点。
#### 情形二

$$
A={0}.
$$

邻域中虽然有大量实数，但这些非零实数都不属于 $A$。去掉 $0$ 后，

$$
\bigl[(-\delta,\delta)\setminus{0}\bigr]\cap A=\varnothing.
$$

因此 $0$ 不是 $A$ 的聚点。

#### 情形三

$$
A=(0,1).
$$

虽然

$$
0\notin A,
$$

但是任意小的 $0$ 的邻域中，都存在属于 $(0,1)$ 的正数。因此 $0$ 是 $A$ 的聚点。

这说明：

> $x_0$ 是否属于 $A$，和 $x_0$ 是否是 $A$ 的聚点，是两个不同的问题。

---

### 还要修正“任意取一个 $x$”

你说：

> 在邻域里面任意取一个值 $x$，但 $x\neq x_0$。

这会被理解成：

$$
\forall x
$$

都满足要求，但定义实际上只要求：

$$
\exists x.
$$

准确说法是：

> 对每一个 $\delta>0$，都能够在 $A$ 中找到至少一个点 $x$，使得 $x\neq x_0$ 且 $|x-x_0|<\delta$。

量词是：

$$
\boxed{\forall\delta>0\ \exists x\in A}
$$

而且这个 $x$ 可以随着 $\delta$ 改变。

---

### 关于字母 $A$ 的重复使用

练习 1.20 中，$A$ 被定义为一个具体邻域：

$$
A=(-1,3).
$$

聚点定义中的

$$
\text{Sia }A\subseteq\mathbb R
$$

则表示“任取一个实数子集 $A$”。

这两个 $A$ 不一定是同一个集合。字母只是局部使用的名称，类似于 C 函数中的参数：

```c
is_accumulation_point(A, x0)
```

换成 $E$、$S$ 或 $D$，定义完全不变：

$$
\forall\delta>0\ \exists x\in E:
0<|x-x_0|<\delta.
$$

### 目前可以记住的一句话

> **Intorno 是以 $x_0$ 为中心的观察区域；punto di accumulazione 是点 $x_0$ 相对于集合 $A$ 所具有的一种性质。**

---

# Results (What are the most important facts and results?)

## Idea behind the Demostration

证明 $x_0$ 是 $A$ 的聚点时：

1. 任取 $\delta>0$，此时 $x_0$ 与 $\delta$ 都已经固定。
2. 观察集合 $A$ 在 $x_0$ 的左边、右边还是两边都有点。
3. 从 $x_0$ 向集合内部移动一段距离 $r$：
   $x=x_0+r$ 或 $x=x_0-r$。
4. 选择 $r$，使得：
   - $0<r<\delta$；
   - 移动后的点仍属于 $A$。
5. 验证 $x\in A$ 以及 $0<|x-x_0|<\delta$。

---

## Facts

### Punto di aacumulazione

第一，$x_0$ **不一定属于** $A$。

例如：

A=(0,1),x0​=0.

虽然 $0\notin A$，但任意 $\delta>0$ 的邻域都包含某个足够小的正数，因此 $0$ 是 $A$ 的聚点。

第二，$x_0\in A$ **也不保证**它是聚点。

例如：

A={3}.

虽然 $3\in A$，但去掉中心以后，可以找到足够小的邻域，使其中没有任何 $A$ 的点。因此 $3$ 不是聚点。

第三，定义要求的是集合中**不同于 $x_0$ 的点**。

因此必须保留： $\setminus \{ x_0 ​\}$ 或等价条件$\left| x-x_0 \right| < 0$.

第四，聚点不是邻域中任意选出的那个 $x$。聚点是正在被检查的中心 $x_0$。

例如：

x0​ 是 A 的聚点 当且仅当 ∀δ>0 ∃x∈A:0<∣x−x0​∣<δ.

寻找的区域： $\left[ ( x_0 - \delta, x_0 + \delta ) \setminus \{ x_0 \} \right]$

允许使用的点的集合： $A$

总结： Intorno 是以 $x_0$ 为中心的观察区域；punto di accumulazione 是点 $x_0$ 相对于集合 $A$ 所具有的一种性质。

| 对象       | 作用                     |
| -------- | ---------------------- |
| $A$      | 我们正在研究的集合              |
| $x_0$    | 候选聚点，即被检查的中心           |
| $\delta$ | 邻域的大小，可以任意小            |
| $x$      | 在 $A$ 中找到的、靠近 $x_0$ 的点 |

---

# Connections (How does it connect with other concepts?)

---

# Exercises (Have I genuinely learnt how to apply it?)

## mistake ex

1. Sia $A$ l’intorno di $x_0=1$ di ampiezza $\delta=2$ e sia $B$ l’intorno destro di $x_0=0$ di ampiezza $\delta=1$. Determinare $$A \cup B, A \cap B, A \setminus B, B \setminus A$$
Answer: $A \cup B = (-1, 3)$, $A \cap B = (-1, 1)$, $A \setminus B = (1, 3)$, $B \setminus A = \emptyset$.

Correct: 注意审题！集合$B$是l’intorno destro！

完整答案：

$$
\boxed{
\begin{aligned}
A\cup B&=(-1,3),\
A\cap B&=(0,1),\
A\setminus B&=(-1,0]\cup[1,3),\
B\setminus A&=\varnothing.
\end{aligned}}
$$

2. 判断 $0$ 是否分别是以下集合的聚点，并用定义说明理由： $$A_1=(0,1), \qquad A_2=\{0\}, \qquad A_3= \left\{ \frac{1}{n}:n \in \mathbb{N}^{+} \right\}$$
Answer: 根据定义$\forall \delta > 0,\quad \exists x\in A \quad \text{con} \quad \left[ ( x_0 - \delta, x_0 + \delta ) \setminus \{ x_0 \} \right] \cap A \neq \emptyset$. 
而$0 \notin A_1$，所以$0$不是$A_1$的聚点；
而$0 \in A_2$，所以$0$是$A_2$的聚点；
而$0 \notin A_3$，所以$0$不是$A_3$的聚点。

Correct: 首先，用交集定义不需要说明$\exists x\in A$；其次，完全没有用到聚点的定义，$x\in A$只是定义的一部分，不能直接用来判断是否为聚点！判断全部依赖于$0\in A\quad\text{或者}\quad 0\notin A,$但聚点定义检查的不是这一条件。

完整答案：

根据定义$\forall \delta > 0,\quad \left[ ( x_0 - \delta, x_0 + \delta ) \setminus \{ x_0 \} \right] \cap A \neq \emptyset$. 
对于$A_1$，我们任取$\delta > 0$，令$x=\min\left\{\frac{\delta}{2}, \frac{1}{2} \right\}$，那么$0<x<1$，所以$x\in A_1$，同时$\left[ ( 0 - \delta, 0 + \delta ) \setminus \{ 0 \} \right] \cap A_1 \neq \emptyset$，因此$0$是$A_1$的聚点；
对于$A_2$，我们取$\delta=1$，则$\left[ (-1, 1)\setminus \{0\} \right]\cap A_2 = \emptyset$，不符合聚点的定义，因此$0$不是$A_2$的聚点；
对于$A_3$，我们任取$\delta > 0$，由于自然数的阿基米德性质，$\exists n\in\mathbb{N}^{+}$ 得到$n>\frac{1}{\delta}$，又因为$n,\delta > 0$，取不等号反向得到$0<\frac{1}{n}<\delta$，我们令$x=\frac{1}{n}$，则$x\in A_3$，而且$0<|x-0|=\frac{1}{n}<\delta$，所以$\left[ ( x_0 - \delta, x_0 + \delta ) \setminus \{ x_0 \} \right] \cap A_3 \neq \emptyset$，因此$0$是$A_3$的聚点。

## classical ex

1. 设
$$
E=\left\{2n:n\in\mathbb{N}^{+}\right\}.
$$
只使用聚点定义，写出一个简短证明，说明 $0$ 不是 $E$ 的聚点。必须明确写出你选择的 $\delta>0$，并区分 $x_0$ 与 $x$。

---

证明：

取
$$
\delta=1.
$$
设 $x_0=0$。假设存在
$$
x\in
\left[
(-1,1)\setminus{0}
\right]\cap E.
$$
因为 $x\in E$，存在 $n\in\mathbb{N}^{+}$，使得
$$\
x=2n.\
$$
于是
$$
x=2n\geq 2.
$$
但是，因为
$$
x\in(-1,1)
$$
又必须有
$$
-1<x<1.
$$
这与 $x\geq2$ 矛盾。因此不存在这样的 $x$，所以
$$
\left[
(-1,1)\setminus\{0\}
\right]\cap E = \emptyset.
$$
因此存在一个 $0$ 的去心邻域不包含任何 $E$ 中的点，故 $0$ 不是 $E$ 的聚点。

---

### 更简短的标准证明

取 $\delta=1$，并令 $x_0=0$。由于对每个 $x\in E$，均存在 $n\in\mathbb{N}^{+}$ 使得 $x=2n\geq2$，所以 $x\notin(-1,1)$。因此
$$
\left[(-1,1)\setminus\{0\}\right]\cap E=\emptyset.
$$
故 $0$ 不是 $E$ 的聚点。

#### Versione per l’esame

以下是意大利数学本科考试中通常采用的规范表达：

Poniamo $x_0=0$ e scegliamo $\delta=1$. Per ogni $x\in E$ esiste $n\in\mathbb{N}^{+}$ tale che $x=2n\geq2$. Pertanto $x\notin(-1,1)$ e quindi
$$
\left[(-1,1)\setminus\{0\}\right]\cap E=\emptyset.
$$
Ne segue che $0$ non è un punto di accumulazione di $E$.

---

2. Esercizio 3.1

Dimostrare che l’insieme dei punti di accumulazione dell’insieme
$$
A=(0,1)\cup(1,2)
$$
è l’intervallo chiuso $[0,2]$.

也就是：

> 证明集合 $A=(0,1)\cup(1,2)$ 的所有聚点恰好组成闭区间 $[0,2]$。

---

证明：

第一方向：

a. 证明 $x_0=1$ 是 $A$ 的聚点：

任取 $\delta>0$

情况一：若 $0<\delta\leq1$，选择
$$
x=\frac{\delta}{2}
$$

验证： 由 $0<\delta \le 1$ 可知 $0 < \frac{\delta}{2} < \delta \le 1$， 所以 $x\in A$

以及
$$
0<|x-1|<\delta
$$
代入可得 $0<|\frac{\delta}{2}-1|<\delta$， 解不等式可得 $\frac{2}{3}<\delta<2$

因此，对于 $x_0=1$， 有 $\left[(1-\delta, 1+\delta)\setminus\{1\}\right]\cap A \neq \emptyset$， $x_0=1$ 是 $A$ 的聚点得证。

情况二：若 $\delta>1$，选择
$$
x=\frac{1}{\delta}
$$
验证： 由 $\delta>1$ 可知 $0<\frac{1}{\delta}<1$， 所以 $x\in A$.

以及
$$
0<|x-1|<\delta
$$
代入可得 $0<|\frac{1}{\delta}-1|<\delta$， 解不等式可得 $\delta>1$

因此，对于 $x_0=1$, 有 $\left[(1-\delta, 1+\delta)\setminus\{1\}\right]\cap A \neq \emptyset$， $x_0=1$ 是 $A$ 的聚点得证。

b. 证明 $x_0=0$ 是 $A$ 的聚点：

任取 $\delta>0$

情况一：若 $0<\delta\leq1$，选择
$$
x=\frac{\delta}{2}
$$

验证： 由 $0<\delta \le 1$ 可知 $0 < \frac{\delta}{2} < \delta \le 1$， 所以 $x\in A$

以及
$$
0<|x-0|<\delta
$$
代入可得 $0<|\frac{\delta}{2}-0|<\delta$， 解不等式可得 $\delta>0$

因此，对于 $x_0=0$， 有 $\left[(0-\delta, 0+\delta)\setminus\{0\}\right]\cap A \neq \emptyset$， $x_0=0$ 是 $A$ 的聚点得证。

情况二：若 $\delta>1$，选择
$$
x=\frac{1}{\delta}
$$
验证： 由 $\delta>1$ 可知 $0<\frac{1}{\delta}<1$， 所以 $x\in A$.

以及
$$
0<|x-0|<\delta
$$
代入可得 $0<|\frac{1}{\delta}-0|<\delta$， 解不等式可得 $0<\delta<1$， 这与 $\delta>1$ 矛盾。

因此，对于 $x_0=0$, 若 $\delta=2$， 则有 $\left[(0-\delta, 0+\delta)\setminus\{0\}\right]\cap A \neq \emptyset$， $x_0=0$ 是 $A$ 的聚点得证。

c. 证明 $x_0=2$ 是 $A$ 的聚点：

任取 $\delta>0$

情况一：若 $0<\delta\leq1$，选择
$$
x=\frac{\delta}{2}
$$

验证： 由 $0<\delta \le 1$ 可知 $0 < \frac{\delta}{2} < \delta \le 1$， 所以 $x\in A$

以及
$$
0<|x-2|<\delta
$$
代入可得 $0<|\frac{\delta}{2}-2|<\delta$， 解不等式可得 $\frac{4}{3}<\delta<4$

因此，对于 $x_0=2$， 有 $\left[(2-\delta, 2+\delta)\setminus\{2\}\right]\cap A \neq \emptyset$， $x_0=2$ 是 $A$ 的聚点得证。

情况二：若 $\delta>1$，选择
$$
x=\frac{1}{\delta}
$$
验证： 由 $\delta>1$ 可知 $0<\frac{1}{\delta}<1$， 所以 $x\in A$.

以及
$$
0<|x-2|<\delta
$$
代入可得 $0<|\frac{1}{\delta}-2|<\delta$， 解不等式可得 $\delta>\frac{1}{2}$

因此，对于 $x_0=2$, 有 $\left[(2-\delta, 2+\delta)\setminus\{2\}\right]\cap A \neq \emptyset$， $x_0=2$ 是 $A$ 的聚点得证。

d. 证明 $x_0\in(0, 1)$ 是 $A$ 的聚点：

任取 $\delta>0$

情况一：若 $0<\delta\leq1$，选择
$$
x=\frac{\delta}{2}
$$

验证： 由 $0<\delta \le 1$ 可知 $0 < \frac{\delta}{2} < \delta \le 1$， 所以 $x\in A$

以及
$$
0<|x-1|<\delta
$$
代入可得 $0<|\frac{\delta}{2}-1|<\delta$， 解不等式可得 $\frac{2}{3}<\delta<2$

因此，对于 $x_0=1$， 有 $\left[(1-\delta, 1+\delta)\setminus\{1\}\right]\cap A \neq \emptyset$， $x_0=1$ 是 $A$ 的聚点得证。

情况二：若 $\delta>1$，选择
$$
x=\frac{1}{\delta}
$$
验证： 由 $\delta>1$ 可知 $0<\frac{1}{\delta}<1$， 所以 $x\in A$.

以及
$$
0<|x-1|<\delta
$$
代入可得 $0<|\frac{1}{\delta}-1|<\delta$， 解不等式可得 $\delta>1$

因此，对于 $x_0=1$, 有 $\left[(1-\delta, 1+\delta)\setminus\{1\}\right]\cap A \neq \emptyset$， $x_0=1$ 是 $A$ 的聚点得证。