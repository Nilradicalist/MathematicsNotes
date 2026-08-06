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

### 01-definizioni-e-fondamenti.md (定义与基础)

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
\lim_{x\to x_0}f(x)=+\infty \quad \forall M>0 \quad \exists \delta>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta \implies f(x)>M
\\
\\
\lim_{x\to x_0}f(x)=-\infty \quad \forall M>0 \quad \exists \delta>0 \quad \forall x\in A , \quad 0<|x-x_0|<\delta \implies f(x)<-M
\end{aligned}
$$
Cas0 2: $x\to \infty$
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

### 02-teoremi-sui-limiti.md (极限定理)

* 极限的唯一性定理 **(Teorema di unicità del limite)** 及其证明。

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

Questo conclude la dimostrazione del teorema di unicità del limite.


* 保号性定理 **(Teorema della permanenza del segno)** 及其证明。

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


* 具有有限极限的函数的局部有界性 **(Locale limitatezza di funzioni con limite finito)**。

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


我对证明思路的疑问：

首先，看来其核心思路还是在草稿纸上逆推 $|f(x)|<M$ 判断合适的 $\varepsilon$ 条件，也正如你之前所说，现在我们学习的三个定理都是在讨论极限值 $\varepsilon$ 还没确定的时候的性质，因此我们可以选定一个合适的 $\varepsilon$ 

然后，由于你的提示，我已经知道选择 $\varepsilon = 1$ 和运用三角不等式最合适。这样虽然我只需要正向推断写出过程即可，但是我发现我无法从 $|f(x)|<M \implies -M < f(x) < M$ 逆推出任何有用的条件，你是如何知道 $\varepsilon = 1$ 的？ 而且我发现之前在证明极限学会的构造法在这三个定理中似乎都不怎么有用，没有明显可构造的条件。

最后，虽然在你的提示下尝试用三角不等式构造了 $M$ 但是我的证明在逻辑上显然有缺陷，帮我指出在哪些地方。

* 夹逼定理 / 比较定理 **(Teorema del confronto)**，包括其在无穷极限上的推广及证明。


* 有限极限的四则运算 **(Operazioni sui limiti finiti)** 及其证明。


* 单调函数的极限 **(Limiti di funzioni monotone)** 及其证明。



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

## 1.4 左右极限 (Limiti Destro e Sinistro)

### 严谨数学定义 (Definizione Rigorosa)

设函数 $f: A \to \mathbb{R}$，且 $x_0$ 是定义域 $A$ 的聚点。

**右极限 (Limite Destro):** 我们称 $L \in \mathbb{R}$ 是 $x$ 从右侧趋近于 $x_0$ 时 $f(x)$ 的极限，记作 $\lim_{x \to x_0^+} f(x) = L$，当且仅当：

$$\forall \varepsilon > 0, \exists \delta > 0 \text{ tale che } \forall x \in A, 0 < x - x_0 < \delta \implies |f(x) - L| < \varepsilon$$

_(注意：这里是 $0 < x - x_0$ 而不是绝对值，表示 $x$ 严格大于 $x_0$)_

**左极限 (Limite Sinistro):** 同理，记作 $\lim_{x \to x_0^-} f(x) = L$，当且仅当：

$$\forall \varepsilon > 0, \exists \delta > 0 \text{ tale che } \forall x \in A, -\delta < x - x_0 < 0 \implies |f(x) - L| < \varepsilon$$

---

## 1.5 拓广实数系与无穷大极限 (Limiti all'infinito e Limiti infiniti)

### 严谨数学定义 (Definizione Rigorosa)

**自变量趋于无穷 (Limite all'infinito):** $\lim_{x \to +\infty} f(x) = L$

当且仅当：

$$\forall \varepsilon > 0, \exists M > 0 \text{ tale che } \forall x > M \implies |f(x) - L| < \varepsilon$$

_(这里不再用极其微小的 $\delta$ 来约束自变量，而是用一个极大的阈值 $M$)_

**函数值趋于无穷 (Limite infinito):** $\lim_{x \to x_0} f(x) = +\infty$

当且仅当：

$$\forall N > 0, \exists \delta > 0 \text{ tale che } \forall x \in A, 0 < |x - x_0| < \delta \implies f(x) > N$$

### 通俗解释 (Spiegazione Intuitiva)

如果说之前的极限是在研究显微镜下的世界（用极其微小的 $\delta$ 逼近一个确定的点），那么这里的极限就是在研究宇宙的边缘（无穷大 $\infty$）。

-   **$x \to \infty$：** 就像我们在写代码时评估算法的“时间复杂度”。我们不在乎程序处理 10 条数据需要几秒，我们在乎的是，如果数据量爆炸到 1 个亿（越过了某个巨大的阈值 $M$），程序的运行时间是否会稳定在某个固定值 $L$ 附近。
    
-   **$f(x) \to \infty$：** 就像我们探索黑洞。当我们离黑洞中心（奇点 $x_0$）越来越近时（距离小于 $\delta$），引力（函数值）会变得无比巨大，超过我们能想象的任何上限 $N$。

---

## 1.6 极限的几个核心定理 (Teoremi sui Limiti)

### 严谨数学定理 (Teoremi Rigorosi)

1.  **唯一性定理 (Unicità del Limite):**
    
    如果 $\lim_{x \to x_0} f(x) = L_1$ 且 $\lim_{x \to x_0} f(x) = L_2$，则必然有 $L_1 = L_2$。
    
2.  **保号性定理 (Permanenza del Segno):**
    
    如果 $\lim_{x \to x_0} f(x) = L > 0$，那么存在一个 $x_0$ 的去心邻域，使得在这个邻域内，对于所有的 $x$，都有 $f(x) > 0$。
    
3.  **夹逼定理 (Teorema dei Due Carabinieri / Teorema del Confronto):**
    
    设在 $x_0$ 的某个去心邻域内，始终有 $h(x) \le f(x) \le g(x)$。
    
    如果 $\lim_{x \to x_0} h(x) = L$ 且 $\lim_{x \to x_0} g(x) = L$，那么 $\lim_{x \to x_0} f(x) = L$。
    

### 通俗解释 (Spiegazione Intuitiva)

这三个定理是我们做复杂计算时的“免死金牌”。

-   **唯一性：** 一个人不可能在同一时刻既在北京又在罗马。极限是一个确定的目标，如果存在，必然唯一。
    
-   **保号性：** 如果你最终到达的目的地是在赤道以北（大于0），那么在你即将到达终点的那一小段路上，你一定也已经在北半球了。
    
-   **夹逼定理：** 这个在意大利语里叫“两个警察定理”（Due Carabinieri）。想象你是一个嫌疑犯 $f(x)$，你的左边和右边各有一个警察（$h(x)$ 和 $g(x)$）死死夹住你。如果这两个警察都在往警察局大门（目标 $L$）走，那么就算你不愿意，你也绝对会被“夹”进警察局。
    
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

## 1.4 极限的核心定理 (Teoremi Fondamentali sui Limiti)

经历了上一节 $\varepsilon-\delta$ 证明的痛苦后，你可能会想：难道以后算任何极限，都要这么从头推导一次误差界限吗？当然不是。数学家们早就用 $\varepsilon-\delta$ 证明了一系列强大的通用定理。在编程里，这就叫**接口封装 (Encapsulation)**：底层的代码已经写好了，以后遇到复杂的系统，直接调用定理即可。

### 1.4.1 唯一性定理 (Teorema di Unicità del Limite)

**严格数学定义：**

设 $f(x)$ 满足在聚点 $x_0$ 处存在极限。如果 $\lim_{x \to x_0} f(x) = L_1$，且 $\lim_{x \to x_0} f(x) = L_2$，那么必定有 $L_1 = L_2$。

**给父母的通俗解释：**

想象一个人沿着一条唯一的马路一直往前走。如果到了终点，有人说他到了北京，又有人说他到了罗马，那只有一种可能——他在两个平行的宇宙里。在我们的现实数学宇宙里，一个确定的运动趋势，只能指向**唯一**的一个目的地。

**严格形式化证明 (反证法)：**

假设存在两个不同的极限 $L_1 \neq L_2$，且不妨设 $L_1 < L_2$。

我们取一个极小的误差值 $\varepsilon = \frac{L_2 - L_1}{2} > 0$。

根据极限定义，存在 $\delta_1 > 0$ 和 $\delta_2 > 0$，使得在 $0 < |x - x_0| < \delta = \min(\delta_1, \delta_2)$ 时，同时满足：

$$L_1 - \varepsilon < f(x) < L_1 + \varepsilon$$

$$L_2 - \varepsilon < f(x) < L_2 + \varepsilon$$

我们将 $\varepsilon$ 代入，会发现 $L_1 + \varepsilon = L_1 + \frac{L_2 - L_1}{2} = \frac{L_1 + L_2}{2}$。

同时 $L_2 - \varepsilon = \frac{L_1 + L_2}{2}$。

这要求 $f(x) < \frac{L_1 + L_2}{2}$ 且 $f(x) > \frac{L_1 + L_2}{2}$，产生逻辑矛盾！因此假设不成立，极限必须唯一。

### 1.4.2 保号性定理 (Teorema della Permanenza del Segno)

**严格数学定义：**

如果 $\lim_{x \to x_0} f(x) = L$，且 $L > 0$（或 $L < 0$），那么必定存在一个 $x_0$ 的去心邻域，使得在这个邻域内的所有 $x$，都有 $f(x) > 0$（或 $f(x) < 0$）。

**给父母的通俗解释：**

如果一列火车的终点站是炎热的热带（极限值 $L > 0$），那么在它即将到达终点站的前几站（去心邻域），窗外的气温肯定已经高于零度了。

### 1.4.3 夹逼定理 (Teorema dei Due Carabinieri / del Confronto)

**严格数学定义：**

设在 $x_0$ 的某个去心邻域内，始终有 $h(x) \le f(x) \le g(x)$ 成立。

如果 $\lim_{x \to x_0} h(x) = L$，且 $\lim_{x \to x_0} g(x) = L$，那么必定有 $\lim_{x \to x_0} f(x) = L$。

**给父母的通俗解释：**

这是意大利学生最喜欢的一个定理，被称为“两个警察定理（Due Carabinieri）”。想象嫌疑人 $f(x)$ 被两个警察 $h(x)$ 和 $g(x)$ 一左一右夹在中间。如果这两个警察最终都走进了警察局（极限都是 $L$），那么中间那个无论怎么挣扎，最终必定也被押进同一个警察局。

**严格形式化证明：**

已知任意 $\varepsilon > 0$，存在 $\delta_1, \delta_2 > 0$，使得：

当 $0 < |x - x_0| < \delta_1$ 时，$L - \varepsilon < h(x) < L + \varepsilon$；

当 $0 < |x - x_0| < \delta_2$ 时，$L - \varepsilon < g(x) < L + \varepsilon$。

取 $\delta = \min(\delta_1, \delta_2)$，此时不等式 $h(x) \le f(x) \le g(x)$ 也成立。我们把它们拼起来：

$$L - \varepsilon < h(x) \le f(x) \le g(x) < L + \varepsilon$$

忽略首尾的警察，只看中间：$L - \varepsilon < f(x) < L + \varepsilon$，即 $|f(x) - L| < \varepsilon$。根据定义，$\lim f(x) = L$ 得证。

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

\[\
x\_0\in\operatorname{Acc}(A).\
]

预先固定的是：

\[\
f,\quad A,\quad x\_0,\quad \ell.\
]

其中 (\ell) 是题目要求我们验证的候选极限值，不是已经证明的极限。

#### 2. 任取 (\varepsilon>0)

正确。必须明确：

\[\
\text{Sia }\varepsilon>0\text{ arbitrario}.\
]

然后研究目标误差：

\[\
|f(x)-\ell|.\
]

#### 3. 逆向分析目标

你的思想正确，但表述需要改成：

> 对 (|f(x)-\ell|) 进行代数变形或估计，寻找一个关于 (|x-x\_0|) 的**充分条件**，使目标不等式成立。

这不一定只能写在草稿纸上。只要使用条件性语言，完全可以严谨地写在答卷上：

> Per ottenere\
> \[\
> |f(x)-\ell|<\varepsilon,\
> ]\
> è sufficiente richiedere che…

不能写成无条件事实：

\[\
|f(x)-\ell|<\varepsilon,\
]

但可以把它明确标记为**目标**。

另外，“大概得出”不够准确。数学上应当是：

* 得到等价条件；或

* 得到充分条件；或

* 得到一个上界估计。

#### 4. 区分发现过程和正式验证

你写的第 4 步目前不完整。不是简单写：

\[\
\Longrightarrow |f(x)-\ell|<\varepsilon.\
]

而应当先完成构造，再重新从定义的左侧开始：

\[\
0<|x-x\_0|<\delta\
\Longrightarrow\
|f(x)-\ell|<\varepsilon.\
]

#### 5. 选择 (\delta)

正确，但需补充：

\[\
\delta=\delta(\varepsilon)>0.\
]

(\delta) 可以依赖：

* (\varepsilon)；

* 已经固定的 (f,A,x\_0,\ell)；

* 证明中预先选定的常数。

但不能依赖随后任取的 (x)。

有多个限制时，通常使用：

\[\
\delta=\min{\delta\_1,\delta\_2,\ldots}.\
]

#### 6. 任取满足条件的 (x)

“代入 (0<|x-x\_0|<\delta)”不够准确。应该写：

> 在选择 (\delta) 之后，任取 (x\in A)，并假设\
> \[\
> 0<|x-x\_0|<\delta.\
> ]

即：

\[\
\forall x\in A\
]

并不是说任意实数都满足这个距离条件，而是说：

\[\
\text{对所有满足该条件的 }x\in A\
]

都要证明输出误差小于 (\varepsilon)。

#### 7. 正向推出目标

正确：

\[\
0<|x-x\_0|<\delta\
\Longrightarrow\
|f(x)-\ell|<\varepsilon.\
]

每一步不等式都应注明依据：

* 使用了哪个代数恒等式；

* 使用了哪个局部估计；

* 使用了 (|x-x\_0|<\delta)；

* 使用了 (\delta) 的具体选择。

#### 8. 调用定义

正确。量词要求全部满足以后，才能写：

\[\
\lim\_{x\to x\_0}f(x)=\ell.\
]

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

# 二、复习任务进度核对

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

***

# 三、教授讲义中的练习是否足够

## 1. 代表性

教授自己的教材和讲义具有很高的**教学代表性**，因为它们反映：

* 定义和记号；

* 定理顺序；

* 教授期望掌握的前置关系；

* 从基础例题到章节练习的递进方式。

课程日志显示，在讲授聚点与有限极限后，教授立即布置了 Esercizio 3.1–3.2，说明这些题主要承担“定义入口训练”的作用。

教材第 3 章的练习从聚点、定义验证，逐步覆盖基本极限、变量替换、运算法则、比较定理、不存在性和数列等内容，范围是比较完整的。

## 2. 数量是否足够

需要区分两个目标。

### 对理解课程结构：基本足够

教授教材足以帮助你：

* 学习正式定义；

* 理解定理用途；

* 完成每类题的初次训练；

* 保持与课程记号一致。

### 对考试熟练度：单独使用不够

例如，教材 Esercizio 3.2 中直接使用定义验证极限的题只有两个基础模型：

\[\
\lim\_{x\to-1}(9-2x)=11,\
\qquad\
\lim\_{x\to2}(x^2+4)=8.\
]

它们足以介绍构造方法，但不足以让你仅靠这两题稳定掌握所有 (\varepsilon)-(\delta) 构造。

另一方面，正式试卷中的极限通常表现为计算题、含参数题或与 Taylor、连续性、反常积分相连的题，而不是大量要求从定义证明简单极限。

因此资源优先级应当是：

\[\
\boxed{\
\text{本教授教材}\
\rightarrow\
\text{本教授正式试卷}\
\rightarrow\
\text{其他教授的补充题}\
}\
]


当前的下一题就是 Malusa 教材 Esercizio 3.2 的第二个模型，正好训练你刚刚讨论的构造问题：

\[\
\boxed{\lim\_{x\to2}(x^2+4)=8}.\
]

请分成两部分提交：

### Ricerca di (\delta)

从

\[\
|(x^2+4)-8|=|x-2||x+2|\
]

开始，回答：

1. 哪个因子已经是我们想控制的距离？

2. 哪个因子目前无法直接控制？

3. 怎样通过先要求 (|x-2|<1) 来控制该因子？

4. 最终应当选择怎样的 (\delta)？

### Verifica

重新从

\[\
0<|x-2|<\delta\
]

出发，写出完整的正向意大利语证明。

---

# Connections (How does it connect with other concepts?)

## 各种极限之间的对比

| 输入            | 输出               | 定义骨架                                           |
| ------------- | ---------------- | ---------------------------------------------- |
| $x\to x_0$    | $f(x)\to\ell$    | $\forall\varepsilon\ \exists\delta\ \forall x$ |
| $x\to+\infty$ | $f(x)\to\ell$    | $\forall\varepsilon\ \exists K\ \forall x$     |
| $x\to x_0$    | $f(x)\to+\infty$ | $\forall M\ \exists\delta\ \forall x$          |
| $x\to+\infty$ | $f(x)\to+\infty$ | $\forall M\ \exists K\ \forall x$              |

---

# Exercises (Have I genuinely learnt how to apply it?)

- classic ex

## mistake ex

### Esercizio 3.2

Dimostrare $\lim_{x\to2}(x^2+4)=8$

La mia risposta:

Abbiamo bisogno della condizione $\delta\leq1$ per controllare il fattore $|x+2|$. Infatti, se $|x-2|<\delta\leq1$, allora
$$
|x+2|=|(x-2)+4|\leq|x-2|+4<5.
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
\varepsilon.
$$

Sia $\varepsilon>0$ arbitrario e poniamo

$$
\delta=\min\left\{2,\frac{\varepsilon}{6}\right\}>0.
$$

Sia $x\in\mathbb R$ tale che

$$
0<|x-2|<\delta.
$$

Poiché $\delta\leq2$, si ha

$$
|x+2|
=
|(x-2)+4|
\leq
|x-2|+4
<
6.
$$

Inoltre, poiché $\delta\leq\frac{\varepsilon}{6}$, si ha

$$
|x-2|<\frac{\varepsilon}{6}.
$$

Pertanto,

$$
\begin{aligned}
|(x^2+4)-8|
&=|x^2-4|\\
&=|x-2||x+2|\\
&<\frac{\varepsilon}{6}\cdot6\\
&=\varepsilon.
\end{aligned}
$$

Quindi, per definizione,

$$
\lim_{x\to2}(x^2+4)=8.
$$


