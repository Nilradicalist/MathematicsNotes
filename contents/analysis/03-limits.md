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

* **聚点 (Punti di accumulazione)** 在实数轴和扩展实数轴上的定义。


* 极限的一般定义，包括有限到有限的极限 **(limite finito al finito)**。


* **右极限 (limite destro)**、**左极限 (limite sinistro)** 以及极限存在的判定准则。


* 极限不存在的情况证明，例如符号函数和 $\sin(1/x)$ 在 0 处的行为。



### 02-teoremi-sui-limiti.md (极限定理)

* 极限的唯一性定理 **(Teorema di unicità del limite)** 及其证明。


* 保号性定理 **(Teorema della permanenza del segno)** 及其证明。


* 具有有限极限的函数的局部有界性 **(Locale limitatezza di funzioni con limite finito)**。


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
