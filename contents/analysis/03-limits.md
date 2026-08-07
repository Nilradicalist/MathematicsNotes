## Table of Contents

```text
analysis/
└── 03-limits.md/
    ├── 03.1-concetti-base.md (基础概念)
    │   ├── Punti di accumulazione (聚点)[cite: 2]
    │   ├── Definizione generale di limite (极限的一般定义)[cite: 2]
    │   ├── Teorema di unicità del limite (极限唯一性定理)[cite: 2]
    │   └── Non esistenza del limite: sin(1/x) (极限不存在的反例)[cite: 2]
    ├── 03.2-teoremi-fondamentali.md (核心定理)
    │   ├── Teorema della permanenza del segno (保号性定理)[cite: 2]
    │   ├── Teorema del confronto / due carabinieri (夹逼定理)[cite: 2]
    │   └── Operazioni sui limiti (极限的四则运算)[cite: 2]
    ├── 03.3-infiniti-e-infinitesimi.md (无穷大与无穷小)
    │   ├── Confronto e principio di sostituzione (比较与替换原则)[cite: 2]
    │   ├── Limiti notevoli e numero di Nepero (重要极限与自然对数底)[cite: 2]
    │   └── Gerarchia degli infiniti (无穷大阶的比较)[cite: 2]
    └── 03.4-strumenti-avanzati.md (计算工具)
        ├── Caratterizzazione sequenziale dei limiti (极限的数列特征)[cite: 2]
        ├── Teorema di de l'Hôpital (洛必达法则)[cite: 2]
        └── Formula di Taylor per i limiti (用泰勒展开求极限)[cite: 2]

```

### 1. Definition

#### 邻域、聚点和极限定义小结

现在我简要总结前面学过的内容（只写数学符号），就当是自己给自己的简短复习：

邻域Intorno的定义：

$x_0\in \mathbb{R} \quad \delta>0 \quad U_{\delta}(x_0):=(x_0-\delta, x_0+\delta) = \left\{x\in \mathbb{R}: |x-x_0|<\delta \right\}$

聚点Punto di accumulazione的定义：

$\forall \delta>0 , \quad \left((x_0-\delta, x_0+\delta)\setminus\{x_0\}\right) \cap A \ne \emptyset \iff \forall \delta>0 \quad \exists x\in A \quad \text{tale che} \quad 0<|x-x_0|<\delta$

以函数 $f(x)$ 的自变量 $x$ 为锚点，总结函数极限的所有定义：

Caso 1: $x\to x_0$
$$
\begin{aligned}
\lim_{x\to x_0}f(x)=\ell \quad \forall \varepsilon>0 \quad \exists \delta>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta \implies |f(x)-\ell|<\varepsilon
\\
\\
\lim_{x\to x_{0}^{+}} f(x)=\ell \quad \forall \varepsilon > 0 \quad \exists \delta > 0 \quad \forall x \in A, \quad 0 < x - x_0 < \delta \implies |f(x) - \ell| < \varepsilon
\\
\\
\lim_{x\to x_{0}^{-}} f(x)=\ell \quad \forall \varepsilon > 0 \quad \exists \delta > 0 \quad \forall x \in A, \quad -\delta < x - x_0 <0 \implies |f(x) - \ell| < \varepsilon
\\
\\
\lim_{x\to x_0}f(x)=+\infty \quad \forall M>0 \quad \exists \delta>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta \implies f(x)>M
\\
\\
\lim_{x\to x_0}f(x)=-\infty \quad \forall M>0 \quad \exists \delta>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta \implies f(x)<-M
\end{aligned}
$$
Caso 2: $x\to \infty$
$$
\begin{aligned}
\lim_{x\to +\infty}f(x)=\ell \quad \forall \varepsilon>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x>K \implies |f(x)-\ell|<\varepsilon
\\
\\
\lim_{x\to -\infty}f(x)=\ell \quad \forall \varepsilon>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x<K \implies |f(x)-\ell|<\varepsilon
\\
\\
\lim_{x\to +\infty}f(x)=+\infty \quad \forall M>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x>K \implies f(x)>M
\\
\\
\lim_{x\to -\infty}f(x)=-\infty \quad \forall M>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x<K \implies f(x)<-M
\\
\\
\lim_{x\to +\infty}f(x)=-\infty \quad \forall M>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x>K \implies f(x)<-M
\\
\\
\lim_{x\to -\infty}f(x)=+\infty \quad \forall M>0 \quad \exists K\in\mathbb{R} \quad \forall x\in A , \quad x<K \implies f(x)>M
\end{aligned}
$$

#### 极限存在判定定理（双侧极限存在的左右极限判别准则）

La definizione:

Limite destro esempio:
$$
\lim_{x\to 0^+}\frac{1}{x}=+\infty
$$

$\forall M>0 \quad \exists \delta>0 \quad \forall x\in A,\quad 0<x-x_0<\delta \implies f(x)>M$ 

Limite sinistro esempio:
$$
\lim_{x\to 0^-}\frac{1}{x}=-\infty
$$

$\forall M>0 \quad \exists \delta>0 \quad \forall x\in A ,\quad -\delta<x-x_0<0 \implies f(x)<-M$ 

La mia dimostrazione:

Primo esercizio:

Sia $M>0$ arbitrario e scegliamo
$$
\delta=\frac{1}{M}>0
$$
Sia $x\in \mathbb{R}\setminus\{0\}$ tale che $0<x-0<\delta$, allora
$$
0<x<\delta=\frac{1}{M}
$$
quindi
$$
\frac{1}{x}>M
$$
Pertanto, per definizione,
$$
\lim_{x\to 0^+}\frac{1}{x}=+\infty
$$

Secondo esercizio:

Sia $M>0$ arbitrario e scegliamo
$$
\delta=\frac{1}{M}>0
$$
Sia $x\in \mathbb{R}\setminus\{0\}$ tale che $-\delta<x-0<0$, allora
$$
-\delta<x<0 \implies
0<-x<\delta=\frac{1}{M}
$$
quindi
$$
\frac{1}{x}<-M
$$
Pertanto, per definizione,
$$
\lim_{x\to 0^-}\frac{1}{x}=-\infty
$$
Poiché, i due limiti laterali esistono in $\overline{\mathbb R}$, ma sono diversi.

Pertanto, per il criterio di esistenza del limite bilatero,
$$
\lim_{x\to 0}\frac{1}{x}
$$
non esiste, neppure in $\overline{\mathbb R}$. $\blacksquare$

### 2. Theorem

#### 2.1 极限的唯一性定理 **(Teorema di unicità del limite)** 及其证明

利用反证法证明极限的唯一性：

Sia $f:A\to\mathbb R$ e sia $x_0$ un punto di accumulazione di $A$. Supponiamo che
$$
\lim_{x\to x_0}f(x)=\ell_1 \qquad \text{e} \qquad \lim_{x\to x_0}f(x)=\ell_2
$$
Supponiamo per assurdo che $\ell_1\neq\ell_2$ e, senza perdita di generalità, che $\ell_1>\ell_2$.
Poniamo
$$
\varepsilon=\frac{|\ell_1-\ell_2|}{2} > 0
$$
Per definizione di limite esistono $\delta_1,\delta_2>0$ tali che
$$
\begin{aligned}
\forall x\in A , \quad 0<|x-x_0|<\delta_1 \implies |f(x)-\ell_1| < \varepsilon
\\
\\
\forall x\in A , \quad 0<|x-x_0|<\delta_2 \implies |f(x)-\ell_2| < \varepsilon
\end{aligned}
$$
Poniamo $\delta=\operatorname{min}\{\delta_1, \delta_2\}$

Poiché $x_0$ è un punto di accumulazione di $A$, esiste $x\in A$ tale che
 $0<|x-x_0|<\delta$

Per tale $x$ si ha contemporaneamente
$$
\ell_1 - \varepsilon < f(x) < \ell_1 + \varepsilon
$$
$$
\ell_2 - \varepsilon < f(x) < \ell_2 + \varepsilon
$$
si ottiene
$$
\ell_2 + \varepsilon = \ell_2 + \frac{|\ell_1-\ell_2|}{2} = \frac{\ell_1+\ell_2}{2}
$$
$$
\ell_1 - \varepsilon = \ell_1 - \frac{|\ell_1-\ell_2|}{2} = \frac{\ell_1+\ell_2}{2}
$$
quindi
$$
\ell_1 - \varepsilon = \ell_2 + \varepsilon = \frac{\ell_1+\ell_2}{2}
$$
si ottiene
$$
\ell_1 - \varepsilon = \frac{\ell_1+\ell_2}{2} < f(x) < \ell_2 + \varepsilon = \frac{\ell_1+\ell_2}{2}
$$
Pertanto, otteniamo una contraddizione, che è impossibile.

Pertanto l’ipotesi $\ell_1\neq\ell_2$ è falsa e dunque $\ell_1 = \ell_2$

Questo conclude la dimostrazione del teorema di unicità del limite. $\blacksquare$

#### 2.2 保号性定理 **(Teorema della permanenza del segno)** 及其证明

证明极限的保号性定理teorema及其推论corollario：

Sia $f:A\to\mathbb R$ e sia $x_0\in \operatorname{Acc}(A)$,  $A\subseteq \mathbb{R}$. Supponiamo che
$$
\lim_{x\to x_0}f(x)=\ell
$$
Allora:
1. Se $\ell > 0$ , esiste un intorno puntato di $x_0$ nel quale $f(x) > 0$
2. Se $\ell < 0$ , esiste un intorno puntato di $x_0$ nel quale $f(x) < 0$

Il corollario:
1. Se $f(x) \geq 0$, $\forall x\in A$ allora $\ell \geq 0$

La mia dimostrazione di teorema:

Per caso  $\ell>0$

Poniamo
$$
\varepsilon=\frac{\ell}{2} > 0
$$
Per definizione di limite esiste un $\delta>0$ tale che
$$
\forall x\in A , \quad 0<|x-x_0|<\delta \implies |f(x)-\ell| < \frac{\ell}{2}
$$
Dalla disuaguaglianza $|f(x)-\ell| < \frac{\ell}{2}$ si ottiene
$$
-\frac{\ell}{2} < f(x)-\ell < \frac{\ell}{2}
\implies
\frac{\ell}{2} < f(x) < \frac{3\ell}{2}
$$
Poiché $\frac{\ell}{2} > 0$

inoltre $f(x)>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta$

Pertanto esiste un intorno puntato di $x_0$ nel quale la funzione mantiene segno positivo.

Per caso $\ell < 0$

Poniamo
$$
\varepsilon=\frac{|\ell|}{2} > 0
$$
si ottiene analogamente
$$
\frac{3\ell}{2} < f(x) < \frac{\ell}{2} < 0
$$
contemporamente $f(x)<0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta$

Pertanto esiste un intorno puntato di $x_0$ nel quale la funzione mantiene segno negativo.

La mia dimostrazione di corollario:

Supponiamo che esista un intorno $U_1$ di $x_0$ tale che
$$
f(x) \geq 0 ,\quad \forall x\in [U_1 \setminus \{x_0\}]\cap A
$$

e che $\lim_{x\to x_0}f(x)=\ell$ 

Supponiamo per assurdo che $\ell<0$. Per il il Teorema della permanenza del segno, esiste un intorno $U_2$ di $x_0$ tale che
$$
f(x) < 0 ,\quad \forall x\in [U_2 \setminus \{x_0\}]\cap A
$$
Poniamo $U=U_1\cap U_2$. Poiché $U$ è un intorno di $x_0$ e $x_0$ è un punto di accumulazione di $A$ , $\exists x\in [U \setminus \{x_0\}]\cap A$

Per tale $x$ si ha contemporaneamente
$$
f(x) \geq 0 \quad \text{e} \quad f(x) < 0
$$
che è impossibile. Pertanto $\ell\geq0$.

$\blacksquare$

极限的保号性定理证明自我Logic Chain整理：

有的时候即使写出了证明，也不代表自己完全理解了，在此写出自己证明过程中的思路。

所谓极限的保号性定理，我自己的理解就是当函数的极限值大于或者小于0的时候，在某一个邻域范围内的函数的自变量$x$，会始终令函数值保持在正数或者负数的状态，函数值的正负和极限值的正负保持同一个状态。

当然，我想我现在已经明白，只有自变量 $x$ 能决定函数 $f(x)$ 的值是多少，所以这个定理只是说明函数值的正负符号和极限值的正负符号**保持**同一状态，不代表极限值决定函数值。这也就是为什么一定要表明 $x_0\in \operatorname{Acc}(A) \quad x\in A \quad \exists \delta>0 \quad 0<|x-x_0|<\delta$（这些条件只是我随手罗列的，不代表我认为正式证明的过程的量词顺序如此，这只是思路的草稿） ，严格确定 $x$ 的取值范围。

正确的量词顺序：$\ell > 0 \implies \exists \delta >0 \quad \forall x\in A, \quad 0<|x-x_0|<\delta \implies f(x) > 0$

首先，考虑一个满足下列假设的函数：
Sia $f:A\to\mathbb R$ e sia $x_0\in \operatorname{Acc}(A)$,  $A\subseteq \mathbb{R}$. Supponiamo che
$$
\lim_{x\to x_0}f(x)=\ell
$$
其次，讨论 $\ell > 0 \quad f(x) > 0$的情况，也是在草稿纸上从假设从结果逆推，我们要怎样找到一个合适的条件满足 $f(x) > 0$

于是我们注意到 $\forall \varepsilon > 0$ 以及 $\ell > 0$之间的联系，不妨令 $\varepsilon=\frac{\ell}{2} > 0$ 成为我们理想中的选定值。

但是，这一步由于是你给出的提示，其实我现在还是不明白为什么要设 $\varepsilon=\frac{\ell}{2} > 0$ ？仅仅是为了让 $0<\varepsilon<\ell$ 这样吗？特意让 $\varepsilon<\ell$ 是为了用 $\ell$ 表示 $\varepsilon$ 构成 $\varepsilon(\ell)$ 方便代入吗？在逻辑推理上有什么具体的意义吗？和我们之前做过的证明极限的题目是不是有一些相似？

然后，根据极限定义正向推导，很容易就得到结果发现 $f(x)>0$，这里就不再赘述。

当 $\ell < 0 \quad f(x) < 0$ 时，推导情况与上面相似，这里也不再赘述。

最后，关于推论，我的疑问仅仅在于，为什么可以只假设 $\ell<0$ ？ 这样符合逻辑命题的推理吗？不应该同时也假设 $f(x)<0$ 吗？毕竟原题就是 $f(x) \ge 0 \implies \ell \ge 0$ ，如果要假设不应该都反过来写成$\ell < 0 \implies f(x) < 0$吗？当然，我知道这是错的，直接推导会显而易见，我只是在这个逻辑层面没有完全理清楚。

总结，真正困难的过程仍然是开始要选取一个合适 $\varepsilon$ 取值，接下来的正向推导过程并不难。我的理解正确吗？我记得在证明极限的题目中，我们通常把 $\varepsilon$ 看成是已经默认给定的值，通常不能由我们控制，这里为什么又可以尝试改造 $\varepsilon$ 了？我对此找不到答案。


#### 2.3 具有有限极限的函数的局部有界性 **(Locale limitatezza di funzioni con limite finito)**

有限极限函数的局部有界性证明：

La mia dimostrazione:

Sia $f:A\to\mathbb R$, sia $x_0\in\operatorname{Acc}(A)$ e supponiamo che
$$
\lim_{x\to x_0}f(x)=\ell \in \mathbb{R}
$$
Poniamo $\varepsilon = 1$

Per definizione di limite esiste $\delta>0$ tale che, per ogni $x\in A$,
$$
0<|x-x_0|<\delta \implies |f(x)-\ell| < \varepsilon = 1
$$
in contemporaneamente, per la disuguaglianza triangolare, da $|f(x)-\ell| < \varepsilon = 1$ si ottiene
$$
|f(x)| = \left| \left(f(x)-\ell\right) + \ell \right| \leq |f(x)-\ell|+|\ell| < 1 + |\ell|
$$
Poniamo $M=1+|\ell|>0$

poichè
$$
|f(x)|<M
$$
per ogni $x\in A$ tale che
$$
0<|x-x_0|<\delta
$$
Pertanto $f$ è limitata in un opportuno intorno puntato di $x_0$, relativamente ad $A$.

$\blacksquare$

我对证明思路的疑问：

首先，看来其核心思路还是在草稿纸上逆推 $|f(x)|<M$ 判断合适的 $\varepsilon$ 条件，也正如你之前所说，现在我们学习的三个定理都是在讨论极限值 $\varepsilon$ 还没确定的时候的性质，因此我们可以选定一个合适的 $\varepsilon$ 

然后，由于你的提示，我已经知道选择 $\varepsilon = 1$ 和运用三角不等式最合适。这样虽然我只需要正向推断写出过程即可，但是我发现我无法从 $|f(x)|<M \implies -M < f(x) < M$ 逆推出任何有用的条件，你是如何知道 $\varepsilon = 1$ 的？ 而且我发现之前在证明极限学会的构造法在这三个定理中似乎都不怎么有用，没有明显可构造的条件。

最后，虽然在你的提示下尝试用三角不等式构造了 $M$ 但是我的证明在逻辑上显然有缺陷，帮我指出在哪些地方。

#### 2.4 比较定理 **(Teorema del confronto)**包括其在无穷极限上的推广及证明

##### 2.4.1 有限极限的比较定理

Teorema:

Siano $f,g,h: A \to \mathbb{R}$

sia $x_0$ un punto di accumulazione di A.

Supponiamo che esista un intorno puntato di $x_0$ tale che
$$
f(x) \le g(x) \le h(x)
$$
e che
$$
\lim_{x \to x_0} f(x) = \lim_{x \to x_0} h(x) = \ell
$$
Allora $\lim_{x \to x_0} g(x) = \ell$

La mia dimostrazione:

Sia $\varepsilon > 0$ arbitrario

Per ipotesi esiste $\delta_0>0$ tale che
$$
0 < |x - x_0| < \delta_0 \implies f(x) \le g(x) \le h(x)
$$
poiché $\lim_{x \to x_0} f(x) = \lim_{x \to x_0} h(x) = \ell$

esiste $\delta_1, \delta_2 > 0$ , tali che

$\forall x\in A, \quad 0 < |x - x_0| < \delta_1 \implies \ell - \varepsilon < f(x) < \ell + \varepsilon$

$\forall x\in A, \quad 0 < |x - x_0| < \delta_2 \implies \ell - \varepsilon < h(x) < \ell + \varepsilon$

Poniamo $\delta = \min\{\delta_0, \delta_1, \delta_2\}$ , allora $\forall x \in A , \quad 0<|x-x_0|<\delta$ , contemporaneamente si ha
$$
\ell - \varepsilon < f(x)  \qquad  h(x) < \ell + \varepsilon
$$
Poiché per ipotesi $f(x) \le g(x) \le h(x)$ si ottiene
$$
\ell - \varepsilon < f(x) \leq g(x) \leq h(x) < \ell + \varepsilon
$$
Quindi
$$
\ell - \varepsilon < g(x) < \ell + \varepsilon \implies |g(x)-\ell|<\varepsilon \quad (\varepsilon>0)
$$
Pertanto, per definizione di limite $\lim_{x \to x_0} g(x) = \ell$

$\blacksquare$

我对证明中的一些疑问（包括其它学习过的定理证明）：

这个定理由于教授上课讲的很详细，因此我的疑问不多，唯一的疑问就在于 $f(x),h(x)$ 的取值范围。无论是唯一性定理还是这个比较定理为什都可以只取不等式一边的值？举例：

在证明唯一性定理的时候我们发现：
Per tale $x$ si ha contemporaneamente
$$
\ell_1 - \varepsilon < f(x) < \ell_1 + \varepsilon
$$
$$
\ell_2 - \varepsilon < f(x) < \ell_2 + \varepsilon
$$
然后，分别只取出两个不等式的一边：
si ottiene
$$
\ell_1 - \varepsilon = \frac{\ell_1+\ell_2}{2} < f(x) < \ell_2 + \varepsilon = \frac{\ell_1+\ell_2}{2}
$$
在证明比较定理的时候我们也是：
esiste $\delta_1, \delta_2 > 0$ , tali che

$0 < |x - x_0| < \delta_1$ , $\ell - \varepsilon < f(x) < \ell + \varepsilon$

$0 < |x - x_0| < \delta_2$ , $\ell - \varepsilon < h(x) < \ell + \varepsilon$

然后，分别只取出两个不等式的一边：
$$
\ell - \varepsilon < f(x)  \qquad  h(x) < \ell + \varepsilon
$$
这样取值在逻辑上有什么依据吗？数学依据在哪里？唯一性定理里面至少是同一个 $f(x)$ 的不同取值范围，但是比较定理里面是不同的两个函数有同一个取值范围，为什么可以这样取值？当然，你可能会说，这是ipotesi里面就假设好的 $f(x) \le g(x) \le h(x)$ ，所以这样；那么我如果反过来假设 $h(x) \le g(x) \le f(x)$ ，那么我是不还是也要改变取值范围，变为$\ell - \varepsilon < h(x)  \qquad  f(x) < \ell + \varepsilon$ ？是因为仅仅是由ipotesi决定的吗？那么唯一性定理里面又是怎么回事？更换不等式两边的式子的依据在哪里？

##### 2.4.2 无限极限的比较定理

Teorema:

Siano $f,g: A \to \mathbb{R}$

sia $x_0$ un punto di accumulazione di A.

Supponiamo che esista un intorno puntato di $x_0$ tale che
$$
f(x) \le g(x)
$$
e che
$$
\lim_{x \to x_0} f(x) = +\infty
$$
Allora $\lim_{x \to x_0} g(x) = +\infty$

La mia dimostrazione:

Sia $M > 0$ arbitrario

Per ipotesi esiste $\delta_0>0$ tale che
$$
0 < |x - x_0| < \delta_0 \implies f(x) \le g(x)
$$
poiché $\lim_{x \to x_0} f(x) = +\infty$

esiste $\delta_1 > 0$ , tale che

$\forall x \in A \quad 0 < |x - x_0| < \delta_1 \implies f(x) > M$

Poniamo $\delta = \min\{\delta_0, \delta_1\}$ , allora $\forall x \in A , \quad 0<|x-x_0|<\delta$ , contemporaneamente si ha
$$
f(x)>M
$$
Poiché per ipotesi $f(x) \le g(x)$ si ottiene
$$
g(x) \geq f(x) > M
$$
Pertanto
$$
\forall x \in A , \quad 0<|x-x_0|<\delta \implies g(x)>M
$$
Poiché $M>0$ è arbitrario, per definizione di limite infinito $\lim_{x \to x_0} g(x) = +\infty$

$\blacksquare$

我对目前这些极限定理证明的疑问：
为什么无论是唯一性定理、保号性定理、局部有界性定理、比较定理全都只是在讨论 $x\to x_0$ 时 $f(x)\to \ell$ 的情况？难道这些定理在 $x\to \infty$ 时 $f(x)\to \infty$ 的时候无法成立吗？因此就没有讨论的意义吗？不过我自己已经在草稿纸上推导过，只要正确地将输入条件和输出目标替换，定理依然成立。当然，对于有限极限函数的局部有界性，如果把输出端改为 $f(x)\to \infty$ 可能要特别注意。我只是好奇为什么教授一般不再展开讨论的原因。

#### 2.5 有限极限的四则运算 **(Operazioni sui limiti finiti)** 及其证明

##### 2.5.1 有瑕疵的证明和一些初步思路

Teorema:

Titolo:

Allora esistono in $x_0$ anche i limiti di $f+g$ ed $f \cdot g$ e si ha
$$
\lim_{x \to x_0} [f(x) + g(x)] = \ell + m \qquad \text{e} \qquad \lim_{x \to x_0} [f(x) \cdot g(x)] = \ell \cdot m
$$
se inoltre $m \neq 0$ , allora esiste anche il limite
$$
\lim_{x \to x_0} \left[\frac{f(x)}{g(x)}\right] = \frac{\ell}{m}
$$
Ipotesi:

Siano $f,g: A \to \mathbb{R}$

sia $x_0$ un punto di accumulazione di A.

Supponiamo che esistano i limiti un intorno puntato di $x_0$ tale che
$$
\lim_{x \to x_0} f(x) = \ell \in \mathbb{R} \qquad \lim_{x \to x_0} g(x) = m\in \mathbb{R}
$$

La mia dimostrazione:

Dimostrazione di addizione:

Sia $\varepsilon > 0$ arbitrario

Per ipotesi $\lim_{x \to x_0} f(x) = \ell \in \mathbb{R} \qquad \lim_{x \to x_0} g(x) = m\in \mathbb{R}$ esiste $\delta_0>0$ tale che
$$
\forall x\in A, \quad 0 < |x - x_0| < \delta_0 \implies \left|\left(f(x)+g(x)\right) - (\ell + m)\right| < \varepsilon
$$
si ottiene
$$
\left|\left(f(x)+g(x)\right) - (\ell + m)\right| = |((f(x) - \ell) + g(x) - m))| = |f(x) - \ell| + |g((x) - m| < \varepsilon
$$
poiché $\lim_{x \to x_0} f(x) = \ell \in \mathbb{R} \qquad \lim_{x \to x_0} g(x) = m \in \mathbb{R}$

esistono $\delta_1, \delta_2 > 0$ , tali che

$\forall x\in A, \quad 0 < |x - x_0| < \delta_1 \implies \ell - \frac{\varepsilon}{2} < f(x) < \ell + \frac{\varepsilon}{2}$

$\forall x\in A, \quad 0 < |x - x_0| < \delta_2 \implies  m - \frac{\varepsilon}{2} < g(x) < m + \frac{\varepsilon}{2}$

Poniamo $\delta = \min\{\delta_0, \delta_1, \delta_2\}$ , allora $\forall x \in A , \quad 0<|x-x_0|<\delta$ , contemporaneamente si ha
$$
\ell + m - (\frac{\varepsilon}{2} + \frac{\varepsilon}{2}) < f(x) + g(x) < \ell + m + (\frac{\varepsilon}{2} + \frac{\varepsilon}{2}) \implies \left|\left(f(x)+g(x)\right) - (\ell + m)\right| < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon
$$
Poiché per ipotesi si ottiene
$$
\lim_{x \to x_0} [f(x) + g(x)] = \ell + m \impliedby \left|\left(f(x)+g(x)\right) - (\ell + m)\right| < \varepsilon
$$
Pertanto, per definizione di limite $\lim_{x \to x_0} [f(x) + g(x)] = \ell + m$

Dimostrazione di moltiplicazione:

Sia $\varepsilon > 0$ arbitrario

Per ipotesi $\lim_{x \to x_0} f(x) = \ell \in \mathbb{R} \qquad \lim_{x \to x_0} g(x) = m\in \mathbb{R}$ esiste $\delta_0>0$ tale che
$$
\forall x\in A, \quad 0 < |x - x_0| < \delta_0 \implies |f(x) \cdot g(x) - \ell \cdot m| < \varepsilon
$$
si ottiene
$$
\left|[f(x) \cdot g(x)] - (\ell \cdot m)\right| = \left|[f(x) \cdot g(x)] - \ell g(x) + \ell g(x) - (\ell \cdot m)\right|
$$
allora
$$
\left|[f(x) \cdot g(x)] - \ell g(x) + \ell g(x) - (\ell \cdot m)\right|
= |g(x)||f(x) - \ell| + |\ell||g(x) - m|
$$
applicando la disuguaglianza triangolare,
$$
\left|[f(x) \cdot g(x)] - (\ell \cdot m)\right| \leq |g(x)||f(x) - \ell| + |\ell||g(x) - m|
$$
Poiché $g(x) \to m$ , scegliamo $\varepsilon=1$

quindi esiste $\delta_1>0$ tale che
$$
\forall x\in A, \quad 0 < |x - x_0| < \delta_1 \implies |g(x) - m| < \varepsilon = 1
$$
si ottiene $|g(x)| \leq |m| + 1$

allora
$$
\left|[f(x) \cdot g(x)] - (\ell \cdot m)\right| \leq (|m|+1)\cdot|f(x) - \ell| + |\ell||g(x) - m|
$$
quindi esiste $\delta_2, \delta_3>0$ tale che
$$
\begin{aligned}
\forall x\in A, \quad 0 < |x - x_0| < \delta_2 \implies |f(x) - \ell| < \frac{\varepsilon}{2(|m|+1)}
\\
\\
\forall x\in A, \quad 0 < |x - x_0| < \delta_3 \implies |g(x) - m| < \frac{\varepsilon}{2(|\ell|+1)}
\end{aligned}
$$
osserviamo che $|\ell| \leq |\ell| + 1$

quindi
$$
|\ell| \cdot \frac{\varepsilon}{2(|\ell|+1)} < \frac{\varepsilon}{2}
$$
poniamo $\delta=\min \{\delta_0,\delta_1,\delta_2,\delta_3\}$

Per $0<|x-x_0|<\delta$

segue
$$
\left|[f(x) \cdot g(x)] - (\ell \cdot m)\right| \leq (|m| + 1) \cdot \left(\frac{\varepsilon}{2(|m|+1)}\right) + |\ell| \cdot \left(\frac{\varepsilon}{2(|\ell|+1)}\right) < \frac{\varepsilon}{2} + \frac{\varepsilon}{2} = \varepsilon
$$
Pertanto
$$
\lim_{x \to x_0} [f(x) \cdot g(x)] = \ell \cdot m
$$

Dimostrazione di reciproco:

Se $\lim_{x \to x_0} g(x) =  m$ con $m \in \mathbb{R}\setminus\{0\}$

allora $\lim_{x \to x_0} \frac{1}{g(x)} =  \frac{1}{m}$

Poiché $m \in \mathbb{R}\setminus\{0\}$ , scegliamo $\varepsilon = \frac{|m|}{2}$

allora esiste $\delta_1 > 0$ tale che
$$
|g(x) - m| < \varepsilon = \frac{|m|}{2}
$$
cioè
$$
|g(x)| > |m| - \frac{|m|}{2} = \frac{|m|}{2}
$$
infatti $g(x)$ non può annullarsi vicino a $x_0$

quinid
$$
\left| \frac{1}{g(x)} - \frac{1}{m} \right| = \frac{|g(x) - m|}{|g(x)||m|}
$$
poiché $|g(x)|>\frac{|m|}{2} \implies |g(x)||m|>\frac{|m|^2}{2}$

quindi
$$
\left| \frac{1}{g(x)} - \frac{1}{m} \right| < \frac{2}{|m|^2}|g(x) - m|
$$
ora scegliamo $\delta_2>0$ tale che
$$
|g(x) - m| < \frac{|m|^2}{2} \varepsilon
$$
allora
$$
\left| \frac{1}{g(x)} - \frac{1}{m} \right| < \varepsilon
$$
Pertanto
$$
\lim_{x \to x_0} \frac{1}{g(x)} =  \frac{1}{m}
$$

Dimostrazione di quoziente:

combiamo il prodotto e reciproco, si ottiene
$$
\lim_{x \to x_0} \left[\frac{f(x)}{g(x)}\right] = \frac{\ell}{m}
$$

我对这个证明的疑问：
1. 我还是不明白，为什么在有限极限的四则运算证明中还是可以自由选择 $\varepsilon$ ，这和前面的几个定理都有什么相同之处和不同之处？
2. 在证明乘法和除法的时候是不是必须借用三角不等式进行构造然后利用有限极限函数的有界性定理判断取值范围？这一步证明十分繁琐，我也不确定有没有出错。
3. 由于证明过程过于繁琐，我希望这次你直接判断我如果没有最根本的逻辑思路上的错误的话，就直接给出一个逻辑严密、结构清晰的有限极限函数的加法、乘法和倒数（除法）的意大利语证明，然后紧接着进入下一个任务。因为我们这个月的复习备考计划重点在于，要在有限的时间内尽可能提高考试分数。这个证明的理解需要较长的时间，而我们不必把一天甚至数天的时间放在理解一个证明上面。
4. 最后，帮助我数理清楚证明有限极限函数的四则运算的Logic Chain，尤其是乘法和倒数（除法）。

##### 2.5.2 正式的证明

Siano $f,g:A\to\mathbb R$ e sia $x_0\in\operatorname{Acc}(A)$. Supponiamo che
 $$
 \lim_{x\to x_0}f(x)=\ell\in\mathbb R,
 \qquad
 \lim_{x\to x_0}g(x)=m\in\mathbb R.
 $$
 Allora
 $$
 \lim_{x\to x_0}(f(x)+g(x))=\ell+m
 $$
 $$
 \lim_{x\to x_0}f(x)g(x)=\ell m
 $$
 Se inoltre $m\neq0$, allora
 $$
 \lim_{x\to x_0}\frac{f(x)}{g(x)}=
 \frac{\ell}{m}
 $$

 ###### 1.Somma

 Sia $\varepsilon_0$ arbitrario.

 Poiché $f(x)\to\ell$, esiste $\delta_1>0$ tale che
 $$
 0<|x-x_0|<\delta_1
 \implies
 |f(x)-\ell|<\frac{\varepsilon}{2}
 $$

 Analogamente, poiché $g(x)\to m$, esiste $\delta_2>0$ tale che
 $$
 0<|x-x_0|<\delta_2
 \implies
 |g(x)-m|<\frac{\varepsilon}{2}
 $$
 Poniamo
 $$
 \delta=\min\{\delta_1,\delta_2\}
 $$
 Per ogni $x\in A$ tale che $0<|x-x_0|<\delta$, per la disuguaglianza triangolare,
 $$
 \begin{aligned}
 |(f(x)+g(x))-(\ell+m)| 
 &=
 |(f(x)-\ell)+(g(x)-m)| \\
 &\leq |f(x)-\ell|+|g(x)-m| \\
 &<
 \frac{\varepsilon}{2} 
 +
 \frac{\varepsilon}{2} 
 =\varepsilon
 \end{aligned}
 $$
 Pertanto
 $$
 \lim_{x\to x_0}(f(x)+g(x))=\ell+m
 $$
 
 ###### 2.Prodotto

 Sia $\varepsilon > 0$ arbitrario.

 Poiché $f(x)\to\ell\in\mathbb R$, per la locale limitatezza esistono $B$ e $\delta_0>0$ tali che
 $$
 0<|x-x_0|<\delta_0
 \implies
 |f(x)|<B
 $$
 Inoltre, poiché $g(x)\to m$, esiste $\delta_1>0$ tale che
 $$
 0<|x-x_0|<\delta_1
 \implies
 |g(x)-m|<\frac{\varepsilon}{2B}
 $$
 Poiché $f(x)\to\ell$, esiste $\delta_2>0$ tale che
 $$
 0<|x-x_0|<\delta_2
 \implies
 |f(x)-\ell|
 <
 \frac{\varepsilon}{2(|m|+1)}
 $$
 Poniamo
 $$
 \delta=\min\{\delta_0,\delta_1,\delta_2\}
 $$
 
 Per ogni $x\in A$ tale che $0<|x-x_0|<\delta$,
 $$
 \begin{aligned}
 |f(x)g(x)-\ell m|
 &=
 |f(x)(g(x)-m)+m(f(x)-\ell)| \\
 &\leq
 |f(x)||g(x)-m|
 +
 |m||f(x)-\ell| \\
 &<
 B\frac{\varepsilon}{2B}
 +
 |m|\frac{\varepsilon}{2(|m|+1)}\\
 &<
 \frac{\varepsilon}{2}
 +
 \frac{\varepsilon}{2}=
 \varepsilon
 \end{aligned}
 $$

 Pertanto
 $$
 \lim_{x\to x_0}f(x)g(x)=\ell m
 $$
 
 ###### 3.Reciproco

 Supponiamo ora che $m\neq0$ e dimostriamo che
 $$
 \lim_{x\to x_0}\frac1{g(x)}=\frac1m
 $$
 
 Sia $\varepsilon>0$ arbitrario.

 Poiché $g(x)\to m$, esiste $\delta_0>0$ tale che
 $$
 0<|x-x_0|<\delta_0
 \implies
 |g(x)-m|<\frac{|m|}{2}
 $$

 Dalla disuguaglianza triangolare inversa segue
 $$
 |g(x)|
 \geq
 |m|-|g(x)-m|>
 \frac{|m|}{2}
 $$

 In particolare $g(x)\neq0$ in tale intorno puntato.

 Inoltre, poiché $g(x)\to m$, esiste $\delta_1>0$ tale che
 $$
 0<|x-x_0|<\delta_1
 \implies
 |g(x)-m|
 <\
 \frac{\varepsilon |m|^2}{2}
 $$
 Poniamo
 $$
 \delta=\min\{\delta_0, \delta_1\}
 $$
 
 Allora, per $0<|x-x_0|<\delta$,
 $$
 \begin{aligned}
 \left|\frac1{g(x)}-\frac1m\right|
 &=
 \frac{|g(x)-m|}{|g(x)||m|}\\
 &<
 \frac{2}{|m|^2}|g(x)-m| \\
 &<
 \frac{2}{|m|^2}\
 \frac{\varepsilon|m|^2}{2}\\
 &=\varepsilon
 \end{aligned}
 $$

 Pertanto
 $$
 \lim_{x\to x_0}\frac1{g(x)}=\frac1m
 $$
 
 ###### 4.Quoziente

 Poiché
 $$
 \frac{f(x)}{g(x)}=
 f(x)\frac1{g(x)}
 $$

 applicando il risultato sul prodotto otteniamo
 $$
 \lim_{x\to x_0}\frac{f(x)}{g(x)}=
 \ell\frac1m=
 \frac{\ell}{m}
 $$

 Questo conclude la dimostrazione.

#### 2.6 多项式极限的证明

计算 $\lim_{x\to0}\frac{1-\cos x}{x^2}$ 以及用有限极限函数的四则运算证明多项式的极限：

Sappiamo che
$$
\lim_{x\to0}\frac{\sin x}{x} = 1 \qquad
\lim_{x\to0}\cos x = 1
$$
quindi
$$
\begin{aligned}
\lim_{x\to0}\frac{1-\cos x}{x^2}
&=
\lim_{x\to0}\frac{(1-\cos x)(1+\cos x)}{x^2(1+\cos x)} \\
&=
\lim_{x\to0}\frac{(1-\cos^2 x)}{x^2(1+\cos x)} \\
&=
\lim_{x\to0}\frac{\sin^2 x}{x^2(1+\cos x)} \\
&=
\lim_{x\to0}\frac{\sin x}{x} \cdot \lim_{x\to0}\frac{\sin x}{x} \cdot \frac{1}{1+\lim_{x\to0}\cos x} \\
&=
1 \cdot 1 \cdot \frac{1}{1+1} \\
&=
\frac{1}{2}
\end{aligned}
$$

证明多项式极限：

Poiché
$$
\lim_{x\to x_0}x^k=x_0^k \ (k=0,\ldots,n)
$$
e $a_k$ è costante, si ha
$$
\lim_{x\to x_0}(a_kx^k)=a_kx_0^k
$$
Per le regole della somma e del prodotto dei limiti finiti,
$$
\lim_{x\to x_0}P(x)
=\sum_{k=0}^{n}\lim_{x\to x_0}(a_kx^k)
=\sum_{k=0}^{n}a_kx_0^k
$$
Poiché
$$
\sum_{k=0}^{n}a_kx_0^k=P(x_0),
$$
Pertanto
$$
\lim_{x\to x_0}P(x)=P(x_0)
$$
$\blacksquare$

我对多项式极限证明的疑问：

这个证明不难，多我而言最难的是如何从 $P(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0$ 转化为 $\lim_{x\to x_0}x^k=x_0^k \ (k=0,\ldots,n)$ 再得到
$$
\lim_{x\to x_0}P(x)
=\sum_{k=0}^{n}\lim_{x\to x_0}(a_kx^k)
=\sum_{k=0}^{n}a_kx_0^k
$$
的这整个过程。因为，第一眼看到 $P(x)=a_nx^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0$ 肯定是无从下手，因为多项式的定义虽然说多项式是“有限”的，但是对于人的笔和纸张来说是“无限”的，不可能写完。如果没有提示的话，我完全想不到要用求和符号来简化运算表达。那么这一步的转化到底是如何思考的？是依据哪些已有的知识？整个逻辑推导的过程是怎样的？

#### 2.7 有限极限函数乘无穷

有限极限函数乘无穷大或者无穷小的一般性证明：

Caso 1: Limite finito non nullo moltiplicato per un infinito

Sia
$$
\lim_{x\to x_0}f(x)=l,\qquad l\in\mathbb{R}.
$$
Se

$$
\lim_{x\to x_0}f(x)=l\neq0,
$$

e
$$
\lim_{x\to x_0}g(x)=+\infty,
$$
allora

$$
\lim_{x\to x_0}f(x)g(x)=
\begin{cases}
+\infty,& l>0,\\
-\infty,& l<0.
\end{cases}
$$

##### Dimostrazione:

Poiché
$$
\lim_{x\to x_0}f(x)=l\neq0,
$$
esiste un intorno di $x_0$ tale che
$$
\frac{|l|}{2}<|f(x)|<\frac{3|l|}{2}.
$$
Inoltre il segno di $f(x)$ coincide con quello di $l$.

Caso $l>0$ , 

Per $x$ sufficientemente vicino a $x_0$,
$$
\frac{l}{2}<f(x)<\frac{3l}{2}.
$$
Poiché
$$
g(x)\longrightarrow+\infty,
$$
si ha anche
$$
g(x)>0
$$
eventualmente.

Moltiplicando membro a membro,
$$
\frac{l}{2}g(x)
<
f(x)g(x)
<
\frac{3l}{2}g(x).
$$
Ora
$$
\lim_{x\to x_0}\frac{l}{2}g(x)=+\infty,
$$
e
$$
\lim_{x\to x_0}\frac{3l}{2}g(x)=+\infty.
$$
Per il Teorema di Confronto,

$$
\lim_{x\to x_0}f(x)g(x)=+\infty
$$

---

Caso $l<0$ , 

Per $x$ sufficientemente vicino a $x_0$,
$$
\frac{3l}{2}<f(x)<\frac{l}{2}<0.
$$
Moltiplicando per $g(x)>0$,
$$
\frac{3l}{2}g(x)
<
f(x)g(x)
<
\frac{l}{2}g(x).
$$

Poiché entrambi gli estremi tendono a $-\infty$,
$$
\lim_{x\to x_0}f(x)g(x)=-\infty
$$

---

Caso 2: Limite finito moltiplicato per un infinitesimo

Sia
$$
\lim_{x\to x_0}f(x)=l\in\mathbb{R},
$$
e
$$
\lim_{x\to x_0}g(x)=0,
$$
allora
$$
\lim_{x\to x_0}f(x)g(x)=0
$$

Dimostrazione: 

Poiché
$$
\lim_{x\to x_0}f(x)=l,
$$
la funzione è limitata in un intorno di $x_0$.

Esiste quindi una costante $M>0$ tale che
$$
|f(x)|\le M.
$$
Da questa disuguaglianza segue
$$
|f(x)g(x)|
\le
M|g(x)|
$$
Inoltre,
$$
0
\le
|f(x)g(x)|
\le
M|g(x)|.
$$
Poiché

$$
\lim_{x\to x_0}M|g(x)|=
M\cdot0=0
$$

per il Teorema di Confronto otteniamo
$$
\lim_{x\to x_0}|f(x)g(x)|=0
$$

Infine,
$$
-|f(x)g(x)|
\le
f(x)g(x)
\le
|f(x)g(x)|
$$

Entrambi gli estremi tendono a $0$; applicando nuovamente il Teorema di Confronto,
$$
\lim_{x\to x_0}f(x)g(x)=0
$$
$\blacksquare$

我对这个证明的疑问：
很明显，使用有限极限函数的四则运算法则会有更简洁的证明，为什么你要求我只使用比较定理来证明呢？是因为分析学中其实有未定式这样的存在，例如 $0 \cdot \infty$ 这样的未定式是无法计算的，所以无法使用四则运算。是这样的吗？那这样的未定式总共有多少种类型？遇到它们又该如何处理呢？如果这些内容在之后的复习备考任务中，现在我们就暂时不讨论，不必打乱复习顺序，一切按照计划来。

#### 单调函数的极限 **(Limiti di funzioni monotone)** 及其证明



### 03-calcolo-dei-limiti-e-forme-indeterminate.md (极限计算与不定式)

* 无穷的部分算术化与不定式 **(Aritmetizzazione parziale di infinito e forme indeterminate)**。


* 分母为零时的比值极限计算，特别是分子收敛于非零有限值的情况以及有理函数 **(funzioni razionali)** 的极限。


* 极限中的变量代换 **(Cambiamento di variabili nei limiti)** 及其证明。


* 重要极限的应用，例如 $\sin(x)$、$\cos(x)$ 在 0 处的极限，以及 $\frac{\sin(x)}{x}$ 和 $\frac{1-\cos(x)}{x^2}$ 在 0 处的极限。


* 无穷小与无穷大 **(Infinitesimi e infiniti)** 的比较与阶层 **(Gerarchia degli infiniti)**。


* 无穷小与无穷大的等价替换原则 **(Principio di sostituzione degli infinitesimi/infiniti)**。


* 有理函数在无穷远处的极限 **(Limiti all'infinito di funzioni razionali)**。


* 包含指数函数和对数函数的极限计算 **(Limiti con esponenziali e logaritmi)**。



### 04-limiti-di-successioni.md (数列极限)

* 数值数列 **(Successioni numeriche)** 的收敛与发散 **(convergenti o divergenti)**。


* 极限的序列特征 **(Caratterizzazione sequenziale dei limiti)** 及其在证明极限不存在时的应用。


* 单调数列的极限 **(Limite di successioni monotone)**。


* 自然对数的底数，即纳皮尔数 **(Il numero di Nepero)**。


* 收敛数列的有界性 **(Limitatezza delle successioni convergenti)** 及其证明。



### 05-strumenti-avanzati.md (进阶计算工具：洛必达与泰勒)

* 导数的极限定理 **(Teorema sui limiti di derivate)** 及其证明。


* 渐近线 **(Asintoti)**：垂直、水平和斜渐近线的求解。


* 洛必达法则 **(Teorema di de l'Hôpital)**，教授特别要求掌握“有限到有限”情况下的证明。


* 带有皮亚诺余项的泰勒公式 **(Formula di Taylor con resto di Peano)** 及其证明。


* 利用多项式近似计算极限 **(Calcolo dei limiti con l'approssimazione polinomiale)** 与无穷小的代数运算 **(Algebra degli infinitesimi)**。

---

## 1.7 连续性 (Continuità)

### 严谨数学定义 (Definizione Rigorosa)

设函数 $f: A \to \mathbb{R}$，且 $x_0 \in A$。我们称函数 $f$ 在 $x_0$ 点是**连续的 (Continua)**，当且仅当：

$$\lim_{x \to x_0} f(x) = f(x_0)$$

用 $\varepsilon-\delta$ 语言等价描述为：

$$\forall \varepsilon > 0, \exists \delta > 0 \text{ tale che } \forall x \in A, |x - x_0| < \delta \implies |f(x) - f(x_0)| < \varepsilon$$

_(注意：这里取消了极限定义中 $0 < |x - x_0|$ 的限制，允许 $x = x_0$)_

### 通俗解释 (Spiegazione Intuitiva)

**连续性是极限通往导数的最重要的一座桥！**

用大白话说，什么叫连续？就是在纸上画一条线，笔尖不离开纸面。

极限 $\lim_{x \to x_0} f(x)$ 代表了我们的“预期”**（根据周围的趋势，我猜这个点的值应该是多少），而 $f(x_0)$ 代表了**“现实”（这个点实际的值是多少）。

“连续”的本质就是：**预期完全符合现实**。没有突兀的跳跃，没有被挖空的陷阱。只有在连续的大地上，我们才能进一步去讨论坡度（导数）。

---

## 1.8 重要极限 (Limiti Notevoli)

### 严谨数学公式 (Formule Rigorose)

在分析学中，有几个经过严格证明的基础极限，我们称之为“重要极限”。最经典的两个是：

1.  **三角函数重要极限:**
    
    $$\lim_{x \to 0} \frac{\sin x}{x} = 1$$
    
2.  **指数/对数重要极限 (欧拉数 $e$ 的定义衍生):**
    
    $$\lim_{x \to \infty} \left(1 + \frac{1}{x}\right)^x = e \quad \text{或者} \quad \lim_{x \to 0} \frac{\ln(1+x)}{x} = 1$$

---

## 1.5 连续性 (Continuità)

极限讨论的是“靠近 $x_0$ 时的趋势”，而它完全不在乎 $x_0$ 那个点**真正的值**是多少（记得定义里有个 $0 < |x - x_0|$ 吗？这就是“去心”，也就是允许那个点是个空洞）。但为了通向微积分的下一步，我们需要把这个洞补上。

### 1.5.1 严谨定义

**严格数学定义：**

设函数 $f(x)$ 在 $x_0$ 的某个邻域内有定义。如果满足：

$$\lim_{x \to x_0} f(x) = f(x_0)$$

我们就称函数 $f(x)$ 在 $x_0$ 点处是**连续的 (Continua)**。

用 $\varepsilon-\delta$ 语言重写就是（注意去掉了 $0 < $ 的限制）：

$$\forall \varepsilon > 0, \exists \delta > 0 \text{ tale che } \forall x, |x - x_0| < \delta \implies |f(x) - f(x_0)| < \varepsilon$$

**给父母的通俗解释：**

什么是连续？第一，你有目的地（极限存在）；第二，目的地那里有路面（函数在这个点有定义）；第三，你的目的地正好踩在路面上（极限值 = 函数值）。直观来说，就是你能在纸上**一笔画出这条线，中间不需要抬起笔**。

---

## 1.6 重要极限 (Limiti Notevoli)

在写 C/C++ 的时候，如果每次求平方根你都要自己写牛顿迭代法，你会疯掉的。所以有了 `#include <math.h>` 里的 `sqrt()` 函数。

在数学分析中，**重要极限 (Limiti Notevoli)** 就是你的标准库。教授要求你遇到它们时，直接背出结果，甚至作为已知条件来化简更复杂的问题。

### 1.6.1 黄金一号库函数：正弦极限

**定理：**

$$\lim_{x \to 0} \frac{\sin x}{x} = 1$$

_(注意：此处的 $x$ 必须是弧度制)_

**给父母的通俗解释：**

当一个角（$x$）变得无限小无限小的时候，代表高度的直线（$\sin x$）和代表弧度的曲线（$x$）会变得几乎一模一样。就好像如果你只看地球表面一平米的地方，它是平的，直线和曲线在这里融为一体了。

**证明思路 (利用夹逼定理)：**

在单位圆（半径 $R=1$）中，画一个极小的角度 $x$（假设 $x \in (0, \pi/2)$）。

根据几何面积比较：

内接三角形面积 $\le$ 扇形面积 $\le$ 外切三角形面积

$$\frac{1}{2} \cdot 1 \cdot \sin x \le \frac{1}{2} \cdot 1^2 \cdot x \le \frac{1}{2} \cdot 1 \cdot \tan x$$

化简得到：$\sin x \le x \le \frac{\sin x}{\cos x}$。

各边同除以 $\sin x$ (因为 $x$ 为极小正数，$\sin x > 0$)：

$$1 \le \frac{x}{\sin x} \le \frac{1}{\cos x}$$

取倒数（不等号反向）：

$$\cos x \le \frac{\sin x}{x} \le 1$$

因为 $\lim_{x \to 0} \cos x = 1$，且 $\lim_{x \to 0} 1 = 1$。根据我们刚刚学的**夹逼定理**，两边的警察都去向了 $1$，所以中间的 $\frac{\sin x}{x}$ 的极限也是 $1$。

---

## 1.7 综合实战：5个代表性例题与解析

对于你来说，到了考试这一步，不再是写文绉绉的定理，而是要动用上面所有的工具来进行代数变形。

### 例题 1：利用夹逼定理对付“震荡恶魔”

**题目：** 计算 $\lim_{x \to 0} x^2 \sin(\frac{1}{x})$

**解析：** $\sin(1/x)$ 在 $x \to 0$ 时会无限疯狂地在 $-1$ 和 $1$ 之间震荡，直接算极限不存在。但我们用**夹逼定理**！

因为 $-1 \le \sin(1/x) \le 1$，我们在不等式各边同乘 $x^2$（因为 $x^2 \ge 0$，不等号方向不变）：

$$-x^2 \le x^2 \sin(\frac{1}{x}) \le x^2$$

因为 $\lim_{x \to 0} (-x^2) = 0$ 且 $\lim_{x \to 0} x^2 = 0$。两边的“警察”都走向了 0，因此极限为 0。

### 例题 2：使用重要极限求代换

**题目：** 计算 $\lim_{x \to 0} \frac{1 - \cos x}{x^2}$

**解析：** 这是一个标准的 $0/0$ 型。我们利用三角恒等式 $1 - \cos x = 2 \sin^2(\frac{x}{2})$ 来变形：

$$\lim_{x \to 0} \frac{2 \sin^2(x/2)}{x^2} = \lim_{x \to 0} 2 \cdot \left(\frac{\sin(x/2)}{x}\right)^2$$

为了凑出 $\lim_{t \to 0} \frac{\sin t}{t} = 1$ 这个标准库（令 $t = x/2$），我们在分母里强行造一个 $2$：

$$= \lim_{x \to 0} 2 \cdot \left(\frac{\sin(x/2)}{2 \cdot (x/2)}\right)^2 = 2 \cdot \frac{1}{4} \cdot \lim_{x \to 0} \left(\frac{\sin(x/2)}{x/2}\right)^2 = \frac{1}{2} \cdot 1^2 = \frac{1}{2}$$

### 例题 3：连续性的判断 (分段函数)

**题目：** 判断函数是否在 $x=0$ 处连续。

$$f(x) = \begin{cases} \frac{\sin(3x)}{x}, & \text{se } x > 0 \\ 3, & \text{se } x = 0 \\ x^2 + 3, & \text{se } x < 0 \end{cases}$$

**解析：** 连续性要求左极限 = 右极限 = 函数值。

右极限：$\lim_{x \to 0^+} \frac{\sin(3x)}{x} = \lim_{x \to 0^+} 3 \cdot \frac{\sin(3x)}{3x} = 3 \cdot 1 = 3$。

左极限：$\lim_{x \to 0^-} (x^2 + 3) = 0 + 3 = 3$。

函数值：$f(0) = 3$。

三者相等，所以函数在 $x=0$ 处**连续**。

### 例题 4：指数型重要极限

**题目：** 计算 $\lim_{x \to \infty} (1 + \frac{2}{x})^{3x}$

**解析：** 看到 $(1 + \dots)^\dots$ 形式，立刻想到另一个黄金标准库：$\lim_{n \to \infty} (1 + \frac{1}{n})^n = e$。

令 $\frac{1}{t} = \frac{2}{x}$，即 $x = 2t$。当 $x \to \infty$ 时，$t \to \infty$。

代入原式：$\lim_{t \to \infty} (1 + \frac{1}{t})^{3(2t)} = \lim_{t \to \infty} \left[ (1 + \frac{1}{t})^t \right]^6$。

括号内部的极限正是自然底数 $e$，所以结果为 $e^6$。

### 例题 5：结合多项式的极限分解

**题目：** 计算 $\lim_{x \to 1} \frac{\sin(x-1)}{x^2 - 1}$

**解析：** 当 $x \to 1$ 时，设变量 $t = x - 1$，此时 $t \to 0$。

原式变为：$\lim_{t \to 0} \frac{\sin t}{(t+1)^2 - 1} = \lim_{t \to 0} \frac{\sin t}{t^2 + 2t} = \lim_{t \to 0} \frac{\sin t}{t(t + 2)}$。

我们可以将其拆分为两部分相乘：

$$= \lim_{t \to 0} \left( \frac{\sin t}{t} \cdot \frac{1}{t+2} \right)$$

第一部分是我们熟悉的黄金库函数，极限为 1。第二部分直接代入 $t=0$，极限为 $1/2$。

所以最终结果为 $1 \cdot \frac{1}{2} = \frac{1}{2}$。

现在，从底层的 C 语言思维（$\varepsilon-\delta$）跳到调用成熟 API（Limiti Notevoli 和核心定理）去解题，你觉得这种抽象层级的提升，会让你的直觉在面对罗马大学那些“令人发指”的代数计算时更轻松一些吗？



# Knowledge Proficiency

* Beginner ()
* Understanding ()
* Intermediate ()
* Mastery ()

---

# Definition (What is it?)

Definition: $\forall \varepsilon>0 \quad \exists \delta>0 \quad \forall x\in \mathbb{R}$, 

## Logical chain/Logical flow

证明思路和Logic Chain：

情况1: $x\to x_0$

寻找阶段：

先观察 $|f(x)-\ell|<\varepsilon$ ，在草稿纸上通过代数方法变形或者估计，一般会得出为一个 $|x-x_0|<H(\varepsilon)$ 的不等式，利用这个不等式寻找一个关于*输入距离*的**充分条件**，即 $$|x-x_0|<H(\varepsilon) \implies |f(x)-\ell|<\varepsilon$$
有时不那么直观，还需要引入辅助变量 $0<\delta\le r$ 进行局部控制， 利用 $0<|x-x_0|<\delta \implies 0<|x-x_0|<r$ .

然后根据前面推测的 $x$ 和 $\varepsilon$ 的关系再次推测在 $0<|x-x_0|<\delta$ 中，$\delta$ 的取值要怎样才能让 $x$ 符合 $|f(x)-\ell|<\varepsilon$ . 

然后合并所有限制条件，选定一个 $\delta=\operatorname{min}\{r, H(\varepsilon), \dots\}$ .

证明阶段：

由于我们已经选定了 $\delta=\operatorname{min}\{r, H(\varepsilon), \dots\}$ 或者其它视情况而定的 $\delta= \dots$

这个时候任取满足条件的 $x\in A$ ,

使用假设的不等式 $0<|x-x_0|<\delta$ ， 展开这个不等式推测 $\delta$ 的具体选择，尝试 $\implies$ $|f(x)-\ell|<\varepsilon$

如果能够正向推出结论（输出误差），那么调用极限的定义，得证。

情况2:$x\to \pm\infty$

寻找阶段：

先观察 $|f(x)-\ell|<\varepsilon$ ，在草稿纸上通过代数方法变形或者估计，一般会得出为一个  $x<G(\varepsilon)$ 或者 $x>G(\varepsilon)$ 的不等式，利用这个不等式寻找一个关于*输入尾部的所在位置*的**充分条件**，即
$$\begin{aligned}
x\to +\infty: \quad x>G(\varepsilon) \implies |f(x)-\ell|<\varepsilon \\
x\to -\infty: \quad x<G(\varepsilon) \implies |f(x)-\ell|<\varepsilon
\end{aligned}
$$
解这个不等式，推测 $x$ 和 $\varepsilon$ 的关系。

然后根据前面推测的 $x$ 和 $\varepsilon$ 的关系再次推测在 $x>K$ 或者 $x<K$ 中，$K$ 的取值要怎样才能让 $x$ 符合 $|f(x)-\ell|<\varepsilon$ . 

有的时候可能推测有多个候选值：

$x\to +\infty, \quad x>G_{1}(\varepsilon), \quad x>G_{2}(\varepsilon)$

$x\to -\infty, \quad x<G_{1}(\varepsilon), \quad x<G_{2}(\varepsilon)$

选定一个 $K=\operatorname{max}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}$

或者 $K=\operatorname{min}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}$

证明阶段：

由于我们已经选定了 $K=\operatorname{max}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}$

或者 $K=\operatorname{min}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}$

这个时候任取满足条件的 $x\in A$ , 

得到
$$\begin{aligned}
x>K=\operatorname{max}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}
\implies
|f(x)-\ell|<\varepsilon \\
x<K=\operatorname{min}\{G_{1}(\varepsilon), G_{2}(\varepsilon), \dots\}
\implies
|f(x)-\ell|<\varepsilon
\end{aligned}
$$

如果能够正向推出结论，那么根据极限的定义，得证。

---

# Intuition (Why is it needed?)

- observe

- examples

- counterexamples

---

# Results (What are the most important facts and results?)

## The Idea Behind the Demonstration (Idea della Dimostrazione)

How to use definition to proof limits?

### 对你八个步骤的逐项修正

#### 1. 识别固定数据

基本正确。还应补充前提：
$$
x_0\in\operatorname{Acc}(A)
$$
预先固定的是：
$$
f,\quad A,\quad x_0,\quad \ell
$$
其中 $\ell$ 是题目要求我们验证的候选极限值，不是已经证明的极限。

#### 2. 任取 (\varepsilon>0)

正确。必须明确：
$$
\text{Sia }\varepsilon>0\text{ arbitrario}
$$
然后研究目标误差：
$$
|f(x)-\ell|
$$

#### 3. 逆向分析目标

你的思想正确，但表述需要改成：

> 对 $|f(x)-\ell|$ 进行代数变形或估计，寻找一个关于 $|x-x_0|$ 的**充分条件**，使目标不等式成立。

这不一定只能写在草稿纸上。只要使用条件性语言，完全可以严谨地写在答卷上：

Per ottenere
$$
|f(x)-\ell|<\varepsilon
$$
è sufficiente richiedere che…

不能写成无条件事实：
$$
|f(x)-\ell|<\varepsilon
$$

但可以把它明确标记为**目标**。

另外，“大概得出”不够准确。数学上应当是：

* 得到等价条件；或

* 得到充分条件；或

* 得到一个上界估计。

#### 4. 区分发现过程和正式验证

你写的第 4 步目前不完整。不是简单写：
$$
\Longrightarrow |f(x)-\ell|<\varepsilon
$$
而应当先完成构造，再重新从定义的左侧开始：
$$
0<|x-x_0|<\delta
\Longrightarrow
|f(x)-\ell|<\varepsilon
$$

#### 5. 选择 $\delta$

正确，但需补充：
$$
\delta=\delta(\varepsilon)>0
$$

$\delta$ 可以依赖：

* $\varepsilon$；

* 已经固定的 $f,A,x_0,\ell$；

* 证明中预先选定的常数。

但不能依赖随后任取的 $x$

有多个限制时，通常使用：
$$
\delta=\min{\delta_1,\delta_2,\ldots}
$$

#### 6. 任取满足条件的 $x$

“代入 $0<|x-x_0|<\delta$”不够准确。应该写：

> 在选择 $\delta$ 之后，任取 $x\in A$，并假设
> 
> $0<|x-x_0|<\delta$
> 

即：
$$
\forall x\in A
$$
并不是说任意实数都满足这个距离条件，而是说：
$$
\text{对所有满足该条件的 }x\in A
$$
都要证明输出误差小于 $\varepsilon$

#### 7. 正向推出目标

正确：
$$
0<|x-x_0|<\delta
\Longrightarrow
|f(x)-\ell|<\varepsilon
$$

每一步不等式都应注明依据：

* 使用了哪个代数恒等式；

* 使用了哪个局部估计；

* 使用了 $|x-x_0|<\delta$；

* 使用了 $\delta$ 的具体选择。

#### 8. 调用定义

正确。量词要求全部满足以后，才能写：
$$
\lim_{x\to x_0}f(x)=\ell
$$

***

## 修正后的完整逻辑链

### A. 寻找构造：Ricerca di (\delta)

1. 识别固定对象 $f,A,x_0,\ell$ ，并确认 $x_0$ 是 $A$ 的聚点。

2. 任取 $\varepsilon>0$

3. 把 $|f(x)-\ell|$ 改写或估计为含有 $|x-x_0|$ 的表达式：Per ottenere $|f(x)-\ell|<\varepsilon$ è sufficiente richiedere che...

4. 寻找一个充分条件：$|x-x_0|<g(\varepsilon)\Longrightarrow|f(x)-\ell|<\varepsilon$ .

5. 若还需要控制其他因子，增加局部限制，并把所有限制合并为$\delta=\min\{\delta_1,\ldots,g(\varepsilon)\}>0$ .

### B. 正式证明：Verifica

6. 任取 $x\in A$ ，满足 $0<|x-x_0|<\delta$ .

7. 利用这个假设以及 $\delta$ 的选择，正向证明 $|f(x)-\ell|<\varepsilon$ .

8. 因为这对任意 $\varepsilon>0$ 都成立，所以根据定义：$\lim\_{x\to x\_0}f(x)=\ell$ .

这条逻辑链现在是严密的。

***

## 二、复习任务进度核对

## `02-intorno` 的通过条件

**已经达成。**

你完成了：

* 四类邻域；

* 聚点定义和精确否定；

* 量词与变量依赖；

* (\operatorname{Acc}((1,2))=\[1,2]) 的完整证明；

* 意大利语定义压缩。

虽然完整证明经过多次修正，但按照原定停止规则，已经足够结束 `02-intorno`，进入 `[[03-limits]]`。

## 是否完成全部 8 月 3 日任务

**没有。**

计划没有把 8 月 3 日和 8 月 4 日分别规定成两个完全独立的章节，而是把 **8 月 2 日至 6 日**作为“极限与数列”阶段，把 **8 月 3 日至 6 日**统一写为“极限与数列”。阶段范围还包括：

* 有限点处有限极限；

* 广义极限；

* 单侧极限；

* 极限唯一性、保号性、比较定理；

* 四则运算和基本极限；

* 变量替换；

* 无穷小与无穷大的比较；

* 数列及单调数列。

目前只完成了这一阶段的入口：

* 有限极限的定义；

* 量词顺序；

* 一个线性函数的直接验证；

* (\delta) 构造法的初步理解。

因此不能说“8 月 3 日的全部任务已完成”。计划还要求 8 月 3 日至 9 日每天安排约 120 分钟核心知识、90 分钟独立题与批改，以及30分钟 A1 回忆；当前对话也无法确认你的实际净学习时间。

## 能否开始 8 月 4 日任务

今天已经是 **2026 年 8 月 4 日**，但这里不需要机械地把内容分成“补 8 月 3 日”和“开始 8 月 4 日”。

正确处理是：

> 继续执行 8 月 3—6 日的同一个“极限与数列”阶段，从当前断点继续。

所以结论是：

* `intorno`：通过，可以结束；

* `limits`：已经开始；

* 第一阶段：尚未完成；

* 当前继续 limits，不回到邻域反复训练，也不提前跳到连续性。

---

# Connections (How does it connect with other concepts?)

## 各种极限之间的对比

---

# Exercises (Have I genuinely learnt how to apply it?)

## classic ex

对上一题的回顾：
虽然上一题我独立做出来了，且你判断我的证明正确。但是，我不能仅仅追求结果，当我再次回顾上一题的时候，我发现如果没有你的提示告诉我要控制 $|x|<1 \implies x<1$ ，我就很难理清思路。那么，假设在你没有给我任何提示的情况下，我该如何思考才能达到“想到要控制 $|x|<1 \implies x<1$”这一条件呢？在没有你给出的提示下，我只能这样在草稿纸（注意是在草稿纸上的假设逆推、寻找特定值的阶段，不是正式的证明）上推断，以下是我的草稿思路：
$$
x-\frac{1}{x^2}<-M \implies
M>x+\frac{1}{x^2}
$$
无法用 $M$ 来表示 $x$ ，也就是说无法像 $2x+1>M$ 那样简单直接地获得一个解。

所以，这个时候我会开始观察 $0<|x-x_0|<\delta \implies 0<|x-0|<\delta \implies 0<|x|<\delta$

紧接着可以继续得到 $0<x^2<\delta^2 \implies -\frac{1}{x^2}<-\frac{1}{\delta^2}<0$

这个时候我会把两个不等式相加得到 $x-\frac{1}{x^2}<\delta-\frac{1}{\delta^2}<0$

于是我会进一步推断 $\delta-\frac{1}{\delta^2} \le -M <0$

尝试利用 $\delta-\frac{1}{\delta^2}=-M \implies \delta=-M+\frac{1}{\delta^2}$

但是这样还是不行，因为无法得出一个 $\delta(M)$  表达式，$\delta=-M+\frac{1}{\delta^2}$ 里面还混杂着 $M$ 和 $\delta$ 

如果没有你的提示，那么我在草稿纸上的思路到这里就断开了。

所以我觉得，这是我的思维困境，是不是我的思路本身就错了？从这一步继续根本就无法推断出正确答案？要么是我从这一步开始就不知道该如何往后思考了，要么就是我一开始就错了。

---

以下是记录了思路的草稿阶段和按标准书写的证明阶段：

先回答1~4这几个问题：
1. 容易得知 $-\frac{2}{x^2}$ 是主导项，因为当 $x\to 0$ 时，分母会变得很小而分子不变，$(\frac{2}{x^2})$分数数值变大再乘以负号，是一个负数；而附加项 $x^3$ 的影响很小，因为当 $x\to 0$ 时，$x^3$ 会变得非常微小。
2. 我给附加项 $x^3$ 设定固定上界为常数8
3. 主导项因此必须低于 $-(M+8)$
4. 最终选择的 $\delta=\operatorname{min}\left\{2, \sqrt\frac{2}{M+8}\right\} >0$

草稿阶段 Ricerca:

由于你在上文的对话中帮助我知道了如何顺着自己的思路使用构造法，我突然发现面对
$$
x^3-\frac{2}{x^2}<-M 
$$
实际上可以直接跳过观察 $0<|x-x_0|<\delta \implies 0<|x-0|<\delta \implies 0<|x|<\delta$ 的阶段。当然我在草稿纸上仍然对这个过程进行了演算，注意到因为有一个立方项 $x^3$ 和一个分子不为1的分母平方 $-\frac{2}{x^2}$ 项，所以导致试图使用 $0<|x-x_0|<\delta \implies 0<|x-0|<\delta \implies 0<|x|<\delta$ 构造出两个次数不同的项变得十分困难。

例如，如果我继续之前那道题那样

$$
x^3-\frac{2}{x^2}<-M \implies
M<-x^3+\frac{2}{x^2}
$$
无法用 $M$ 来表示 $x$

观察 $0<|x-x_0|<\delta \implies 0<|x-0|<\delta \implies 0<x^2<\delta^2$ 得到 $-\frac{1}{x^2}<-\frac{1}{\delta^2}<0 \implies -\frac{2}{x^2}<-\frac{2}{\delta^2}<0$

然后试图构造一个 $x^3$ , 发现使用 $0<|x-x_0|<\delta \implies 0<|x-0|<\delta \implies 0<x^2<\delta^2$ 无法构造出 $0<x^3<\delta^3$

此时总而言之，无法使用输入距离来构造 $\delta(M)$ . 

看似两边都无法构造，此时我重新回过头来看 $x^3-\frac{2}{x^2}<-M$

我注意到一件事
$$
x^3-\frac{2}{x^2}<8-(M+8)
$$
因此发现了可以使用构造法的条件
$$
x^3 \le 8\quad, \quad
-\frac{2}{x^2} \le -(M+8)
$$
解这个不等式组
$$
\begin{cases}
x^3 \le 8 \\
\\
-\frac{2}{x^2} \le -(M+8)
\end{cases}
$$
可得
$$
\begin{cases}
x \le 2\\
\\
|x| \le \sqrt\frac{2}{M+8}
\end{cases}
$$
于是可以令 $\delta=\operatorname{min}\left\{2, \sqrt\frac{2}{M+8}\right\}$

草稿阶段结束。

证明阶段 Verificare：

Sia $M>0$ arbitrario e scegliamo
$$
\delta=\operatorname{min}\left\{2, \sqrt\frac{2}{M+8}\right\} >0
$$
Sia $x\in \mathbb{R}\setminus\{0\}$ tale che $0<|x-0|<\delta$, allora
$$
0<|x|<\delta=\operatorname{min}\left\{2, \sqrt\frac{2}{M+8}\right\}
$$
quindi
$$
|x|<\sqrt\frac{2}{M+8} \implies
x^2<\frac{2}{M+8} \implies
-\frac{2}{x^2} < -(M+8)
$$
inoltre, poichè $\delta=\operatorname{min}\left\{2, \sqrt\frac{2}{M+8}\right\}$ si ottiene
$$
|x|<2 \implies
|x^3|=|x|^3 < 8 \implies
x^3 < 8 \quad
$$
quindi
$$
x^3-\frac{2}{x^2} < 8-(M+8) \implies x^3-\frac{2}{x^2} < -M
$$
Pertanto, per definizione,
$$
\lim_{x\to 0}\left(x^3-\frac{2}{x^2}\right)=-\infty
$$


## mistake ex

### Esercizio 3.2

Dimostrare $\lim_{x\to2}(x^2+4)=8$

La mia risposta:

Abbiamo bisogno della condizione $\delta\leq1$ per controllare il fattore $|x+2|$. Infatti, se $|x-2|<\delta\leq1$, allora
$$
|x+2|=|(x-2)+4|\leq|x-2|+4<5
$$
Pertanto il fattore $|x+2|$ è limitato superiormente da una costante indipendente da $x$.

我们想证明$|x+2|<5$，经过观察我们发现可以使用$|x-2|<1$进行变换， $|x-2|<1 \implies -1<x-2<1 \implies 3<x+2<5 \implies |x+2|<5$，这样就能得到$|x+2|<5$ 。回过头来，我们最终需要的是$|x-2|<\delta$，所以，为了满足这两个不等式我们需要$\delta\leq1$ 。

Abbiamo inoltre bisogno della condizione
$$
\delta\leq\frac{\varepsilon}{5}
$$
per ottenere la precisione richiesta. Infatti,
$$\
|x-2|<\delta\leq\frac{\varepsilon}{5}\
$$
e $|x+2|<5$, quindi
$$
|x-2||x+2|
<
\frac{\varepsilon}{5}\cdot5
\varepsilon
$$

Sia $\varepsilon>0$ arbitrario e poniamo

$$
\delta=\min\left\{2,\frac{\varepsilon}{6}\right\}>0
$$

Sia $x\in\mathbb R$ tale che

$$
0<|x-2|<\delta
$$

Poiché $\delta\leq2$, si ha

$$
|x+2|
=
|(x-2)+4|
\leq
|x-2|+4
<
6
$$

Inoltre, poiché $\delta\leq\frac{\varepsilon}{6}$, si ha

$$
|x-2|<\frac{\varepsilon}{6}
$$

Pertanto,

$$
\begin{aligned}
|(x^2+4)-8|
&=|x^2-4| \\
&=|x-2||x+2| \\
&<\frac{\varepsilon}{6}\cdot6 \\
&=\varepsilon
\end{aligned}
$$

Quindi, per definizione,

$$
\lim_{x\to2}(x^2+4)=8
$$


