实际上，**像 `\ell` 这样的命令并不少**，只是 LaTeX 没有把它们集中放在一起介绍。

可以把数学中"看起来还是英文字母，但换了一种数学字体"的符号分成几大类：

1. **单独设计的字母（symbol letters）** —— 例如 `\ell`。
2. **数学罗马体（Roman）** —— `\mathrm`
3. **数学斜体（默认）**
4. **粗体（Bold）**
5. **黑板粗体（Blackboard Bold）**
6. **花体（Calligraphic）**
7. **Euler Script（欧拉花体）**
8. **哥特体（Fraktur）**
9. **Sans Serif**
10. **Typewriter 等其它字体**

其中真正像 **`\ell` 这样专门提供命令** 的其实很少，大多数都是**整个字母表切换字体**。

下面按照实际数学论文（AMS、Springer、IEEE、SIAM、Annals 等）中的使用频率整理。

---

# 一、真正"特殊"的英文字母（不是换字体）

这些都有自己独立命令。

| LaTeX           | 显示       | 常见用途                 | 是否AMS推荐 |
| --------------- | -------- | -------------------- | ------- |
| `\ell`          | $\ell$   | length、序列编号、避免与数字1混淆 | ⭐⭐⭐⭐⭐   |
| `\imath`        | $\imath$ | 去掉点的 i               | ⭐⭐⭐⭐    |
| `\jmath`        | $\jmath$ | 去掉点的 j               | ⭐⭐⭐⭐    |
| `\wp`           | $\wp$    | Weierstrass p 函数     | ⭐⭐⭐     |
| `\eth`（amssymb） | $\eth$   | 微分几何、冰岛字母            | ⭐       |
| `\mho`          | $\mho$   | 电导单位（欧姆倒数）           | ⭐       |
| `\Game`         | $\Game$  | 博弈论、集合论              | ⭐       |

其中真正最常见的其实只有：

```latex
\ell
\imath
\jmath
```

---

# 二、默认数学斜体（所有变量默认）

例如

```latex
a,b,c,\ldots,z
A,B,C,\ldots,Z
```

显示：

$$
x,;y,;z,;A,;B,;C
$$

这是数学里使用最多的字体。

---

# 三、Roman（直立体）

```latex
\mathrm{A}
```

得到

$$
\mathrm{A}
$$

通常表示：

| 用途          | 例子                    |
| ----------- | --------------------- |
| 常数          | $\mathrm e,\mathrm i$ |
| 微分          | $\mathrm d x$         |
| 单位          | $\mathrm{kg}$         |
| operator 名称 | $\mathrm{rank}$       |

---

# 四、粗体（Bold）

```latex
\mathbf{x}
```

得到

$$
\mathbf{x}
$$

用途：

| 字母          | 含义   |
| ----------- | ---- |
| $\mathbf x$ | 向量   |
| $\mathbf A$ | 矩阵   |
| $\mathbf I$ | 单位矩阵 |

---

# 五、Blackboard Bold（黑板粗体）

需要 amsfonts 或 amssymb。

```latex
\mathbb{R}
```

得到

$$
\mathbb R
$$

完整字母：

| 命令           | 显示          |
| ------------ | ----------- |
| `\mathbb{A}` | $\mathbb A$ |
| `\mathbb{B}` | $\mathbb B$ |
| `\mathbb{C}` | $\mathbb C$ |
| ...          | ...         |
| `\mathbb{Z}` | $\mathbb Z$ |

其中最常用：

| 字母          | 含义      |
| ----------- | ------- |
| $\mathbb N$ | 自然数     |
| $\mathbb Z$ | 整数      |
| $\mathbb Q$ | 有理数     |
| $\mathbb R$ | 实数      |
| $\mathbb C$ | 复数      |
| $\mathbb P$ | 概率/射影空间 |
| $\mathbb F$ | 有限域     |

---

# 六、Calligraphic（花体）

```latex
\mathcal{A}
```

得到

$$
\mathcal A
$$

只能大写。

全部：

```text
\mathcal{A}
...
\mathcal{Z}
```

显示：

$$
\mathcal A,\mathcal B,\ldots,\mathcal Z
$$

常见用途：

| 字母           | 含义        |
| ------------ | --------- |
| $\mathcal L$ | 拉格朗日、线性算子 |
| $\mathcal H$ | 希尔伯特空间    |
| $\mathcal F$ | 傅里叶变换     |
| $\mathcal O$ | Big-O     |
| $\mathcal P$ | 幂集        |
| $\mathcal B$ | σ代数       |

---

# 七、Euler Script（欧拉花体）

需要

```latex
\usepackage{euscript}
```

然后

```latex
\EuScript{A}
```

显示：

$$
\mathscr A
$$

（不同宏包名字略有区别，例如 `mathrsfs` 中使用 `\mathscr`。）

---

# 八、mathrsfs（最漂亮的 Script）

```latex
\mathscr{A}
```

得到

$$
\mathscr A
$$

很多顶刊喜欢。

例如：

$$
\mathscr L,\mathscr F,\mathscr H
$$

---

# 九、Fraktur（哥特体）

```latex
\mathfrak{g}
```

得到

$$
\mathfrak g
$$

全部：

```text
\mathfrak{A}
...
\mathfrak{Z}

\mathfrak{a}
...
\mathfrak{z}
```

用途：

| 字母            | 含义          |
| ------------- | ----------- |
| $\mathfrak g$ | Lie Algebra |
| $\mathfrak h$ | 子代数         |
| $\mathfrak m$ | 极大理想        |
| $\mathfrak p$ | 素理想         |

---

# 十、Sans Serif

```latex
\mathsf{x}
```

得到

$$
\mathsf x
$$

用途：

随机变量、算法状态等。

---

# 十一、Typewriter

```latex
\mathtt{x}
```

得到

$$
\mathtt x
$$

表示代码、机器变量。

---

# 十二、Bold Italic

```latex
\boldsymbol{x}
```

得到

$$
\boldsymbol x
$$

比 `\mathbf` 更常用于希腊字母和数学变量。

---

# 十三、bm（推荐）

```latex
\bm{x}
```

效果：

$$
\bm x
$$

几乎所有粗数学变量都推荐使用。

---

# 十四、数学中最常见的"字体变量"

下面这张表几乎涵盖论文中所有常见的数学英文字母字体。

| 命令            | 显示              | 大写 | 小写                        | 典型用途         |
| ------------- | --------------- | -- | ------------------------- | ------------ |
| 默认            | $A,a$           | ✔  | ✔                         | 普通变量         |
| `\mathrm`     | $\mathrm A$     | ✔  | ✔                         | 常数、单位、算子     |
| `\mathbf`     | $\mathbf A$     | ✔  | ✔                         | 向量、矩阵        |
| `\mathit`     | $\mathit A$     | ✔  | ✔                         | 强制斜体         |
| `\mathsf`     | $\mathsf A$     | ✔  | ✔                         | Sans Serif   |
| `\mathtt`     | $\mathtt A$     | ✔  | ✔                         | 代码变量         |
| `\mathbb`     | $\mathbb A$     | ✔  | ✘（传统 Computer Modern 不支持） | 数域、集合        |
| `\mathcal`    | $\mathcal A$    | ✔  | ✘                         | 花体           |
| `\mathscr`    | $\mathscr A$    | ✔  | ✘                         | Script       |
| `\EuScript`   | $\mathscr A$    | ✔  | ✘                         | Euler Script |
| `\mathfrak`   | $\mathfrak A$   | ✔  | ✔                         | Lie 代数、理想    |
| `\boldsymbol` | $\boldsymbol A$ | ✔  | ✔                         | 粗数学符号        |
| `\bm`         | $\bm A$         | ✔  | ✔                         | 推荐的粗数学字体     |

---

# 十五、真正值得记住的高频命令（★★★★★）

如果按数学论文（AMS、SIAM、Springer、Elsevier 等）的出现频率排序，可以优先掌握下面这些：

| 命令            | 显示            | 推荐指数  |
| ------------- | ------------- | ----- |
| `\ell`        | $\ell$        | ⭐⭐⭐⭐⭐ |
| `\imath`      | $\imath$      | ⭐⭐⭐⭐  |
| `\jmath`      | $\jmath$      | ⭐⭐⭐⭐  |
| `\mathbb{R}`  | $\mathbb R$   | ⭐⭐⭐⭐⭐ |
| `\mathbb{N}`  | $\mathbb N$   | ⭐⭐⭐⭐⭐ |
| `\mathbb{Z}`  | $\mathbb Z$   | ⭐⭐⭐⭐⭐ |
| `\mathbb{Q}`  | $\mathbb Q$   | ⭐⭐⭐⭐  |
| `\mathbb{C}`  | $\mathbb C$   | ⭐⭐⭐⭐⭐ |
| `\mathcal{L}` | $\mathcal L$  | ⭐⭐⭐⭐⭐ |
| `\mathcal{F}` | $\mathcal F$  | ⭐⭐⭐⭐⭐ |
| `\mathcal{H}` | $\mathcal H$  | ⭐⭐⭐⭐⭐ |
| `\mathcal{P}` | $\mathcal P$  | ⭐⭐⭐⭐  |
| `\mathscr{L}` | $\mathscr L$  | ⭐⭐⭐⭐  |
| `\mathfrak g` | $\mathfrak g$ | ⭐⭐⭐⭐  |
| `\mathfrak h` | $\mathfrak h$ | ⭐⭐⭐⭐  |
| `\mathbf x`   | $\mathbf x$   | ⭐⭐⭐⭐⭐ |
| `\bm x`       | $\bm x$       | ⭐⭐⭐⭐⭐ |

---

## 关于「除了 `\ell` 还有没有很多这种单独命令？」

答案是：**并没有很多。** LaTeX 中像 `\ell` 这样**不是通过 `\math...{}` 改变整套字体，而是单独为某个拉丁字母提供专用字形**的命令屈指可数，主要就是：

| 命令       | 字形       | 说明                                         |
| -------- | -------- | ------------------------------------------ |
| `\ell`   | $\ell$   | 小写字母 l 的专用数学字形，避免与数字 1 或大写 I 混淆。           |
| `\imath` | $\imath$ | 无点小写 i，便于加重音、箭头、帽子等，如 `\hat{\imath}`。      |
| `\jmath` | $\jmath$ | 无点小写 j，作用同上。                               |
| `\wp`    | $\wp$    | Weierstrass p 的专用符号，虽然来源于字母 p，但通常视为独立数学符号。 |

除此之外，大多数"长得像英文字母但风格不同"的数学符号，都是通过 `\mathcal`、`\mathbb`、`\mathfrak`、`\mathscr`、`\mathbf`、`\mathsf` 等**整套数学字体命令**生成的，而不是像 `\ell` 那样为某一个字母专门定义的特殊命令。



### 1. 取整函数 (Floor & Ceiling)

你提到的 $[x]$ 通常指高斯取整函数，但在现代数学中，为了消除歧义，我们会明确区分“向下取整”和“向上取整”。它们在 LaTeX 中的写法如下：

* **向下取整 (Floor, 取小于等于 $x$ 的最大整数):** 使用 `\lfloor x \rfloor`，渲染结果为 $\lfloor x \rfloor$
* **向上取整 (Ceiling, 取大于等于 $x$ 的最小整数):** 使用 `\lceil x \rceil`，渲染结果为 $\lceil x \rceil$

### 2. 二项式展开与自动缩放括号（组合数）

那个“上面一个 $n$，下面一个 $k$”的大括号，叫做组合数（二项式系数）。
在 LaTeX 中，千万不要试图用括号和分数去拼凑，它有专门的命令 `\binom{上}{下}`：

* **代码：** `\binom{n}{k}`
* **渲染：** $\binom{n}{k}$
* 如果是行内公式，它会自动缩小：$\binom{n}{k}$；如果是独立成行，它会自动放大：

$$\binom{n}{k} = \frac{n!}{k!(n-k)!}$$

### 3.带有分数和根号的大括号（自动匹配高度）

如果你直接打 `( \frac{\sqrt{a}}{b} )`，括号会很小，包不住里面的分数，显得极丑：( $\frac{\sqrt{a}}{b}$ )。
**终极秘诀：在括号前面加上 `\left` 和 `\right`。**

* **代码：** `\left( \frac{\sqrt{a}}{b} \right)`
* **渲染：** $\left( \frac{\sqrt{a}}{b} \right)$

你可以把它用在基本不等式（AM-GM）里：

* **代码：** `\frac{x+y}{2} \ge \sqrt{xy} \implies \left( \frac{x+y}{2} \right)^2 \ge xy`
* **渲染：** $\frac{x+y}{2} \ge \sqrt{xy} \implies \left( \frac{x+y}{2} \right)^2 \ge xy$

> **💡 核心法则：** `\left` 和 `\right` 必须成对出现。除了圆括号 `\left( \right)`，也可以用方括号 `\left[ \right]`，或者绝对值/范数 `\left| \right|`。

---

# 数学专业 LaTeX 核心速查表

## 一、 希腊字母 (Greek Letters)
大写字母只需将命令首字母大写（注：有些大写字母与拉丁字母相同，如 A, B, T，故无特殊 LaTeX 命令）。

| 小写代码 | 渲染 | 大写代码 | 渲染 |
| --- | --- | --- | --- |
| `\alpha` | $\alpha$ | `A` | $A$ |
| `\beta` | $\beta$ | `B` | $B$ |
| `\gamma` | $\gamma$ | `\Gamma` | $\Gamma$ |
| `\delta` | $\delta$ | `\Delta` | $\Delta$ |
| `\epsilon`, `\varepsilon`| $\epsilon$, $\varepsilon$| `E` | $E$ |
| `\zeta` | $\zeta$ | `Z` | $Z$ |
| `\eta` | $\eta$ | `H` | $H$ |
| `\theta`, `\vartheta`| $\theta$, $\vartheta$| `\Theta` | $\Theta$ |
| `\iota` | $\iota$ | `I` | $I$ |
| `\kappa` | $\kappa$ | `K` | $K$ |
| `\lambda` | $\lambda$ | `\Lambda` | $\Lambda$ |
| `\mu` | $\mu$ | `M` | $M$ |
| `\nu` | $\nu$ | `N` | $N$ |
| `\xi` | $\xi$ | `\Xi` | $\Xi$ |
| `\pi`, `\varpi` | $\pi$, $\varpi$ | `\Pi` | $\Pi$ |
| `\rho`, `\varrho` | $\rho$, $\varrho$ | `P` | $P$ |
| `\sigma`, `\varsigma`| $\sigma$, $\varsigma$| `\Sigma` | $\Sigma$ |
| `\tau` | $\tau$ | `T` | $T$ |
| `\upsilon` | $\upsilon$ | `\Upsilon` | $\Upsilon$ |
| `\phi`, `\varphi` | $\phi$, $\varphi$ | `\Phi` | $\Phi$ |
| `\chi` | $\chi$ | `X` | $X$ |
| `\psi` | $\psi$ | `\Psi` | $\Psi$ |
| `\omega` | $\omega$ | `\Omega` | $\Omega$ |

## 二、 逻辑与集合论 (Logic & Set Theory)

| 意义 | 代码 | 渲染 |
| --- | --- | --- |
| 任意 / 存在 | `\forall`, `\exists` | $\forall$, $\exists$ |
| 属于 / 不属于 | `\in`, `\notin` | $\in$, $\notin$ |
| 子集 / 真子集 | `\subseteq`, `\subsetneq` | $\subseteq$, $\subsetneq$ |
| 交集 / 并集 | `\cap`, `\cup` | $\cap$, $\cup$ |
| 空集 | `\emptyset` 或 `\varnothing`| $\emptyset$, $\varnothing$ |
| 推出 / 等价 | `\implies`, `\iff` | $\implies$, $\iff$ |
| 映射 | `f: A \to B` | $f: A \to B$ |
| 组合 / 复合 | `f \circ g` | $f \circ g$ |

## 三、 数系与代数 (Algebra & Number Systems)

| 意义 | 代码 | 渲染 |
| --- | --- | --- |
| 自然数/实数/复数 | `\mathbb{N}`, `\mathbb{R}`, `\mathbb{C}` | $\mathbb{N}$, $\mathbb{R}$, $\mathbb{C}$ |
| 有理数/整数 | `\mathbb{Q}`, `\mathbb{Z}` | $\mathbb{Q}$, $\mathbb{Z}$ |
| 同构 / 等价 | `\cong`, `\sim` | $\cong$, $\sim$ |
| 向量 (粗体/箭头) | `\mathbf{v}`, `\vec{v}` | $\mathbf{v}$, $\vec{v}$ |
| 范数 (双竖线) | `\left\| x \right\|` | $\left\| x \right\|$ |
| 内积 / 尖括号 | `\langle u, v \rangle` | $\langle u, v \rangle$ |
| 叉乘 / 点乘 | `\times`, `\cdot` | $\times$, $\cdot$ |
| 正比于 | `\propto` | $\propto$ |

## 四、 微积分与分析 (Calculus & Analysis)

| 意义 | 代码 | 渲染 |
| --- | --- | --- |
| 极限 | `\lim_{x \to \infty} f(x)` | $\lim_{x \to \infty} f(x)$ |
| 积分 (定积分) | `\int_{a}^{b} f(x) dx` | $\int_{a}^{b} f(x) dx$ |
| 多重积分 | `\iint`, `\iiint` | $\iint$, $\iiint$ |
| 偏导数 | `\frac{\partial f}{\partial x}` | $\frac{\partial f}{\partial x}$ |
| 梯度 / 倒三角 | `\nabla f` | $\nabla f$ |
| 级数求和 | `\sum_{i=1}^{n} i^2` | $\sum_{i=1}^{n} i^2$ |
| 连乘积 | `\prod_{i=1}^{n} p_i` | $\prod_{i=1}^{n} p_i$ |
| 趋于无穷大 | `\to \infty` | $\to \infty$ |

## 五、 排版与常用技巧 (Formatting & Tricks)

**1. 上标与下标：**
`x_i^2` 渲染为 $x_i^2$。如果上下标超过一个字符，必须用大括号包起来：`x_{i+1}^{2n}` 渲染为 $x_{i+1}^{2n}$。

**2. 根号与分数：**
* 根号：`\sqrt{x}` $\implies \sqrt{x}$ ； n次方根：`\sqrt[n]{x}` $\implies \sqrt[n]{x}$
* 分数：`\frac{分子}{分母}` $\implies \frac{a}{b}$

**3. 空格：**
在数学公式中，空格默认被忽略。需要加空格时：
* 窄空格：`\,` （如：$dx \, dy$）
* 中空格：`\quad` （如：$x=1 \quad y=2$）
* 宽空格：`\qquad` （如：$x=1 \qquad y=2$）

**4. 方程组/分段函数 (Cases环境)：**
```latex
f(x) = 
\begin{cases} 
x^2 & \text{if } x \ge 0 \\
-x & \text{if } x < 0 
\end{cases}

渲染为：
$$ f(x) = \begin{cases} x^2 & \text{if } x \ge 0 \ -x & \text{if } x < 0 \end{cases} $$
*(注：`\text{}` 用于在数学公式中输入普通纯文本，防止变斜体)*

```


---

## 2. 数理逻辑与集合论 (Logic & Set Theory)

| 符号 | LaTeX 代码 | 含义/说明 |
| :--- | :--- | :--- |
| $\forall$ | `\forall` | 任意 (For all) |
| $\exists$ | `\exists` | 存在 (Exists) |
| $\nexists$ | `\nexists` | 不存在 (Does not exist) |
| $\implies$ | `\implies` | 推出 (Implies) |
| $\impliedby$ | `\impliedby` | 被推出 |
| $\iff$ | `\iff` | 当且仅当 (If and only if) |
| $\land$ / $\lor$ | `\land` / `\lor` | 逻辑与 / 逻辑或 |
| $\neg$ | `\neg` | 逻辑非 |
| $\in$ / $\notin$ | `\in` / `\notin` | 属于 / 不属于 |
| $\subset$ / $\subseteq$ | `\subset` / `\subseteq` | 真包含于 / 包含于 |
| $\subsetneq$ | `\subsetneq` | 真子集 |
| $\cup$ / $\cap$ | `\cup` / `\cap` | 并集 / 交集 |
| $\bigcup_{i=1}^n$ | `\bigcup_{i=1}^n` | 大并集 |
| $\bigcap_{i=1}^n$ | `\bigcap_{i=1}^n` | 大交集 |
| $\setminus$ | `\setminus` | 集合差 (Set difference) |
| $\emptyset$ | `\emptyset` 或 `\varnothing` | 空集 |
| $\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}$ | `\mathbb{N, Z, Q, R, C}` | 数集（自然数、整数、有理数、实数、复数） |
| $\aleph_0$ | `\aleph_0` | 阿列夫零（基数） |

---

## 3. 分析学与微积分 (Analysis, Calculus & Measure Theory)

| 符号/公式 | LaTeX 代码 | 含义/说明 |
| :--- | :--- | :--- |
| $\lim_{x \to \infty}$ | `\lim_{x \to \infty}` | 极限 |
| $\limsup_{n \to \infty}$ | `\limsup_{n \to \infty}` | 上极限 |
| $\liminf_{n \to \infty}$ | `\liminf_{n \to \infty}` | 下极限 |
| $\sup$ / $\inf$ | `\sup` / `\inf` | 上确界 / 下确界 |
| $\sum_{n=1}^{\infty}$ | `\sum_{n=1}^{\infty}` | 求和 |
| $\prod_{k=1}^{n}$ | `\prod_{k=1}^{n}` | 连乘 |
| $\int_a^b$ | `\int_a^b` | 定积分 |
| $\iint_D$ / $\iiint_V$ | `\iint_D` / `\iiint_V` | 二重 / 三重积分 |
| $\oint_C$ | `\oint_C` | 曲线/路径积分 |
| $\frac{\mathrm{d}y}{\mathrm{d}x}$ | `\frac{\mathrm{d}y}{\mathrm{d}x}` | 全导数（`\mathrm{d}` 保持正体） |
| $\frac{\partial f}{\partial x}$ | `\frac{\partial f}{\partial x}` | 偏导数 |
| $\nabla f$ | `\nabla f` | 梯度 (Gradient) |
| $\Delta f$ | `\Delta f` | 拉普拉斯算子 |
| $\mu(E)$ | `\mu(E)` | 测度 (Measure) |
| $\text{a.e.}$ | `\text{a.e.}` | 几乎处处 (Almost everywhere) |
| $L^p(\Omega)$ | `L^p(\Omega)` | $L^p$ 空间 |
| $f \ast g$ | `f \ast g` | 卷积 (Convolution) |

---

## 4. 线性代数与抽象代数 (Linear & Abstract Algebra)

| 符号/公式 | LaTeX 代码 | 含义/说明 |
| :--- | :--- | :--- |
| $\ker(f)$ | `\ker(f)` | 核 (Kernel) |
| $\text{im}(f)$ | `\text{im}(f)` | 象 (Image) |
| $\text{span}(V)$ | `\text{span}(V)` | 张成空间 |
| $\text{rank}(A)$ | `\text{rank}(A)` | 矩阵的秩 |
| $\det(A)$ | `\det(A)` | 行列式 |
| $\text{Tr}(A)$ | `\text{Tr}(A)` | 矩阵的迹 (Trace) |
| $\mathbf{A}^T$ / $\mathbf{A}^*$ | `\mathbf{A}^T` / `\mathbf{A}^*` | 转置 / 共轭转置 |
| $\langle u, v \rangle$ | `\langle u, v \rangle` | 内积 (Inner product) |
| $\| v \|$ | `\| v \|` | 范数 (Norm) |
| $\otimes$ | `\otimes` | 张量积 (Tensor product) |
| $\oplus$ | `\oplus` | 直和 (Direct sum) |
| $\cong$ | `\cong` | 同构 (Isomorphic) |
| $\lhd$ / $\unlhd$ | `\lhd` / `\unlhd` | 正规子群 (Normal subgroup) |
| $\rtimes$ | `\rtimes` | 半直积 |
| $\text{Aut}(G)$ / $\text{Hom}(V, W)$ | `\text{Aut}(G)` / `\text{Hom}(V, W)` | 自同构群 / 同态空间 |

---

## 5. 拓扑学、度量空间与微分几何 (Topology & Differential Geometry)

| 符号/公式 | LaTeX 代码 | 含义/说明 |
| :--- | :--- | :--- |
| $\mathcal{T}$ | `\mathcal{T}` | 拓扑 (Topology) |
| $B_r(x)$ | `B_r(x)` | 开球 (Open ball) |
| $\bar{A}$ | `\bar{A}` 或 `\overline{A}` | 闭包 (Closure) |
| $A^\circ$ | `A^\circ` 或 `\mathring{A}` | 内部 (Interior) |
| $\partial A$ | `\partial A` | 边界 (Boundary) |
| $\pi_1(X, x_0)$ | `\pi_1(X, x_0)` | 基本群 (Fundamental group) |
| $\mathrm{d}\omega$ | `\mathrm{d}\omega` | 外微分 (Exterior derivative) |
| $\wedge$ | `\wedge` | 外积/楔积 (Wedge product) |
| $g_{ij}$ | `g_{ij}` | 度量张量 (Metric tensor) |
| $\Gamma^k_{ij}$ | `\Gamma^k_{ij}` | 克里斯托费尔符号 |

---

## 6. 概率论与数理统计 (Probability & Statistics)

| 符号/公式 | LaTeX 代码 | 含义/说明 |
| :--- | :--- | :--- |
| $\mathbb{P}(A)$ / $\mathbb{E}[X]$ | `\mathbb{P}(A)` / `\mathbb{E}[X]` | 概率 / 期望 |
| $\text{Var}(X)$ / $\text{Cov}(X, Y)$ | `\text{Var}(X)` / `\text{Cov}(X, Y)` | 方差 / 协方差 |
| $\sim$ | `\sim` | 服从分布 |
| $\mathcal{N}(\mu, \sigma^2)$ | `\mathcal{N}(\mu, \sigma^2)` | 正态分布 |
| $\mathbf{1}_A$ | `\mathbf{1}_A` 或 `\mathbb{1}_A` | 示性函数 (Indicator function) |
| $\xrightarrow{d}$ / $\xrightarrow{p}$ | `\xrightarrow{d}` / `\xrightarrow{p}` | 依分布收敛 / 依概率收敛 |

---

## 7. 常用排版与矩阵结构 (Environments & Formats)

### (1) 分段函数 (Cases)
$$
f(x) = 
\begin{cases} 
x^2 & \text{if } x \ge 0 \\
0 & \text{if } x < 0 
\end{cases}
$$
```latex
f(x) = 
\begin{cases} 
x^2 & \text{if } x \ge 0 \\
0 & \text{if } x < 0 
\end{cases}
```

### (2) 多行对齐公式 (Aligned Equations)
$$
\begin{aligned}
(a+b)^2 &= (a+b)(a+b) \\
&= a^2 + ab + ba + b^2 \\
&= a^2 + 2ab + b^2
\end{aligned}
$$
```latex
\begin{aligned}
(a+b)^2 &= (a+b)(a+b) \\
&= a^2 + ab + ba + b^2 \\
&= a^2 + 2ab + b^2
\end{aligned}
```

### (3) 常用矩阵 (Matrices)
$$
\begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad 
\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}, \quad
\begin{vmatrix} x & y \\ z & w \end{vmatrix}
$$
```latex
\begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad 
\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}, \quad
\begin{vmatrix} x & y \\ z & w \end{vmatrix}
```

### (4) 空格控制 (Spacing Controls)
*   小空格：`\,` （如 $\int f(x) \, \mathrm{d}x$）
*   中空格：`\quad`
*   大空格：`\qquad`



## 2. 数学专业本科 LaTeX 核心速查表 (Cheat Sheet)

不要去背厚厚的 LaTeX 手册。罗马大学（Sapienza）本科阶段的代数、几何（Geometria）和分析（Analisi），掌握以下核心符号足以覆盖 95% 的推导需求。遇到极个别生僻符号，再去 Google。

你可以直接复制以下表格到你的 Markdown 软件中。

### 希腊字母 (Greek Letters)

> ⚠️ **重要提示：** 许多 LaTeX 新手会到处找大写的 Alpha (`\Alpha`)。在 LaTeX 中，与拉丁字母长得一样的大写希腊字母（如 A, B, E, Z, H, K, M, N, O, P, T, X）**没有专属代码**，直接输入对应的英文大写字母即可！

| 小写符号 | 小写代码 | 大写符号 | 大写代码 |
| --- | --- | --- | --- |
| $\alpha$ | `\alpha` | $A$ | `A` |
| $\beta$ | `\beta` | $B$ | `B` |
| $\gamma$ | `\gamma` | $\Gamma$ | `\Gamma` |
| $\delta$ | `\delta` | $\Delta$ | `\Delta` |
| $\epsilon$ | `\epsilon` | $E$ | `E` |
| $\varepsilon$ | `\varepsilon` (变体) | $E$ | `E` |
| $\zeta$ | `\zeta` | $Z$ | `Z` |
| $\eta$ | `\eta` | $H$ | `H` |
| $\theta$ | `\theta` | $\Theta$ | `\Theta` |
| $\vartheta$ | `\vartheta` (变体) | $\Theta$ | `\Theta` |
| $\iota$ | `\iota` | $I$ | `I` |
| $\kappa$ | `\kappa` | $K$ | `K` |
| $\lambda$ | `\lambda` | $\Lambda$ | `\Lambda` |
| $\mu$ | `\mu` | $M$ | `M` |
| $\nu$ | `\nu` | $N$ | `N` |
| $\xi$ | `\xi` | $\Xi$ | `\Xi` |
| $o$ | `o` | $O$ | `O` |
| $\pi$ | `\pi` | $\Pi$ | `\Pi` |
| $\rho$ | `\rho` | $P$ | `P` |
| $\sigma$ | `\sigma` | $\Sigma$ | `\Sigma` |
| $\tau$ | `\tau` | $T$ | `T` |
| $\upsilon$ | `\upsilon` | $\Upsilon$ | `\Upsilon` |
| $\phi$ | `\phi` | $\Phi$ | `\Phi` |
| $\varphi$ | `\varphi` (变体) | $\Phi$ | `\Phi` |
| $\chi$ | `\chi` | $X$ | `X` |
| $\psi$ | `\psi` | $\Psi$ | `\Psi` |
| $\omega$ | `\omega` | $\Omega$ | `\Omega` |

### 逻辑与集合论 (Logic & Set Theory)

| 符号 | LaTeX代码 | 含义 / 场景 |
| --- | --- | --- |
| $\forall$ | `\forall` | 对所有 (For all) |
| $\exists$ | `\exists` | 存在 (Exists) |
| $\nexists$ | `\nexists` | 不存在 |
| $\implies$ | `\implies` | 蕴含/推导 |
| $\iff$ | `\iff` | 当且仅当 (if and only if) |
| $\in$ / $\notin$ | `\in` / `\notin` | 属于 / 不属于 |
| $\subset$ / $\subseteq$ | `\subset` / `\subseteq` | 真子集 / 子集 |
| $\cup$ / $\cap$ | `\cup` / `\cap` | 并集 / 交集 |
| $\setminus$ | `\setminus` | 集合差 (A \ B) |
| $\times$ | `\times` | 笛卡尔积 |
| $\emptyset$ / $\varnothing$ | `\emptyset` / `\varnothing` | 空集 |

### 代数、映射与常用数集 (Algebra & Maps)

欧洲大学特别喜欢用 $\mathbb{K}$ 来指代任意域（Campo，实数或复数），请牢记 `\mathbb` 环境。

| 符号 | LaTeX代码 | 含义 / 场景 |
| --- | --- | --- |
| $\mathbb{N}, \mathbb{Z}, \mathbb{Q}$ | `\mathbb{N}, \mathbb{Z}, \mathbb{Q}` | 自然数, 整数, 有理数 |
| $\mathbb{R}, \mathbb{C}, \mathbb{K}$ | `\mathbb{R}, \mathbb{C}, \mathbb{K}` | 实数, 复数, 任意域 |
| $\mapsto$ | `\mapsto` | 映射到 (元素层面: $x \mapsto x^2$) |
| $\to$ | `\to` | 趋于/映射 (函数层面: $f: A \to B$) |
| $\hookrightarrow$ | `\hookrightarrow` | 包含映射 / 单射 |
| $\circ$ | `\circ` | 复合函数 ($f \circ g$) |
| $\oplus$ / $\otimes$ | `\oplus` / `\otimes` | 直和 / 张量积 (Geometria核心) |
| $\cong$ / $\simeq$ | `\cong` / `\simeq` | 同构 / 同伦等价 |
| $\langle x, y \rangle$ | `\langle x, y \rangle` | 内积 / 生成空间 |
| $\dim$ / $\ker$ | `\dim` / `\ker` | 维度 / 核 (直接用代码) |

### 分析与微积分 (Analysis & Calculus)

| 符号 | LaTeX代码 | 含义 / 场景 |
| --- | --- | --- |
| $\infty$ | `\infty` | 无穷大 |
| $\partial$ | `\partial` | 偏导数 ($\partial f / \partial x$) |
| $\nabla$ | `\nabla` | 梯度 (Nabla算子) |
| $\int, \iint, \oint$ | `\int, \iint, \oint` | 积分, 双重积分, 环路积分 |
| $\sum_{i=1}^n$ | `\sum_{i=1}^n` | 求和符号 |
| $\prod$ | `\prod` | 连乘符号 |
| $\lim_{n \to \infty}$ | `\lim_{n \to \infty}` | 极限 |
| $\Vert{}x\Vert{}$ / $\vert{}x\vert{}$ | `|x|` / ` | x |
| $x_n^{(k)}$ | `x_n^{(k)}` | 下标与上标带括号的常见格式 |

### 其他进阶符号与修饰 (Modifiers)

| 符号 | LaTeX代码 | 含义 / 场景 |
| --- | --- | --- |
| $\dots$ / $\cdots$ | `\dots` / `\cdots` | 底端省略号 / 居中省略号 |
| $\vdots$ / $\ddots$ | `\vdots` / `\ddots` | 竖向省略号 / 对角省略号 (矩阵用) |
| $\hat{x}, \tilde{x}, \bar{x}$ | `\hat{x}, \tilde{x}, \bar{x}` | 帽子, 波浪号, 上划线 (复共轭或闭包) |
| $\vec{v}$ / $\mathbf{v}$ | `\vec{v}` / `\mathbf{v}` | 向量 (粗体形式更好看用 mathbf) |
| $\equiv$ / $\approx$ | `\equiv` / `\approx` | 恒等(同余) / 约等于 |

### 环境结构 (Environments) - 复制直接用

**1. 矩阵 (Matrix)：**
线性代数（Geometria）中天天要写。推荐使用 `pmatrix`（带圆括号）或 `bmatrix`（带方括号）。

```latex
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}

```

**2. 分段函数 (Cases)：**
分析（Analisi）中证明经常用到。

```latex
f(x) = \begin{cases} 
x^2 & \text{if } x \ge 0 \\
-x & \text{if } x < 0 
\end{cases}

```

**3. 对齐方程组 (Aligned Equations)：**
推导步骤需要等号对齐时，必须学会这个。

```latex
\begin{aligned}
(x+y)^2 &= x^2 + 2xy + y^2 \\
&\ge 4xy
\end{aligned}

```
