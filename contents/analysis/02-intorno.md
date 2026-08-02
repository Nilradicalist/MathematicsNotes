---
topic: "邻域与聚点"
course: "Analisi Matematica 1"
file: "02-intorno.md"
status: "stage-b-refined"
version: "1.0"
created: ""
updated: "2026-08-02"
prerequisites:
  - "[[01-real-number-theory]]"
next_topics:
  - "[[03-limits]]"
stage_a_status: "frozen"
---

# Knowledge Proficiency

## Current Evaluation

| Knowledge Unit | Current Level | Evidence | Main Blocker | Next Target |
|---|---|---|---|---|
| 邻域、左右邻域与去心邻域 | Understanding | 能写出完整邻域并完成 Esercizio 1.20；原稿仍混淆中心是否包含 | 稳定区分完整邻域、左右邻域和去心邻域 | 不看笔记写出四种集合及距离形式 |
| 聚点定义与量词 | Understanding | 能解释 $\forall\delta>0\,\exists x\in A$，并认识到 $x$ 可依赖 $\delta$ | 正式证明中偶尔遗漏量词或混淆 $x_0$ 与 $x$ | 独立写出定义与精确否定 |
| 区间中的见证构造 | Understanding | 已能在左右端点及任意 $x_0\in(1,2)$ 中使用 $x=x_0\pm r$ | 面对新集合时仍不易独立发现见证形式 | 无提示证明任意开区间的聚点集合 |
| 非聚点的阻断半径 | Understanding | 能为离散集合、$x_0<0$ 和 $x_0>2$ 选择 $\delta_0$ | 邻域端点界偶尔验证错对象 | 独立寻找并验证阻断半径 |
| 完整证明与考试压缩 | Understanding | 在帮助下完成 Esercizio 3.1，并能核验意大利语版本 | 尚未无提示重构整题 | 独立完成两个包含方向并压缩为考试版 |

## Level Criteria

- **Beginner**：能辨认概念并复述部分定义，但不能稳定解释或应用。
- **Understanding**：能用自己的话解释，能跟随并核验标准证明。
- **Intermediate**：能独立完成标准题、构造证明并识别常见错误。
- **Mastery**：能迁移到陌生情境、比较等价表述、压缩证明并清晰讲解。

## Evidence Log

| Date | Task / Evidence | Result | First Decisive Error | Level Update |
|---|---|---|---|---|
| 2026-08-01–2026-08-02 | 判断 $0$ 是否为三个集合的聚点 | 在纠正成员关系误区后能使用定义完成 | 用 $x_0\in A$ 代替聚点定义 | Beginner → Understanding |
| 2026-08-01–2026-08-02 | 为区间端点构造见证 | 能独立写出左侧情形 $x=x_0-r$ | 正负号和 `min` 不等号不稳定 | 保持 Understanding |
| 2026-08-01–2026-08-02 | 证明任意 $x_0\in(1,2)$ 是聚点 | 构造正确，遗漏任取 $\delta>0$，并误用上界条件 | 量词缺失 | 保持 Understanding |
| 2026-08-01–2026-08-02 | 排除 $x_0<0$ 与 $x_0>2$ | 理解阻断半径并能复现 | 对 $x_0>2$ 只证明邻域端点大于 $0$ | 保持 Understanding |
| 2026-08-02 | 完成 Esercizio 3.1 | 在完整引导下得到聚点集合 $[0,2]$ | 尚未无提示重构整题 | 保持 Understanding |

# Knowledge Guide

## Topic Identity

- **中文名称**：邻域与聚点
- **Nome italiano**：Intorno e punto di accumulazione
- **English term**：neighborhood and accumulation point
- **Course / Chapter**：Analisi Matematica 1；Fondamenti 与 Limiti
- **Prerequisites**：区间、集合运算、绝对值与距离、量词、[[01-real-number-theory]]
- **Next topics**：函数极限、单侧极限、[[03-limits]]

## Scope

### Included

- 有限实数点 $x_0\in\mathbb R$ 的完整邻域、左右邻域与去心邻域；
- 实数子集的聚点；
- 等价定义和精确否定；
- 区间见证构造、参数集合见证构造和阻断半径；
- Esercizio 1.20 与 Esercizio 3.1；
- 与极限定义的直接连接。

### Excluded or Deferred

- $+\infty$ 与 $-\infty$ 的邻域；
- 单侧聚点与单侧极限的完整理论；
- 一般度量空间和拓扑空间中的邻域与聚点；
- 导集的系统性质；
- 极限的 $\varepsilon$-$\delta$ 定义与运算定理。

## Core Questions

1. 邻域、左右邻域和去心邻域分别包含哪些点？
2. 聚点是 $x_0$ 的性质，还是见证 $x$ 的性质？
3. $A$、$x_0$、$\delta$、$x$ 和 $r$ 各自承担什么角色？
4. 为什么 $x_0\in A$ 与“$x_0$ 是聚点”相互独立？
5. 怎样从集合结构判断见证 $x$ 的形式？
6. 怎样精确否定聚点定义？
7. 为什么这个概念是函数极限的前置条件？

## Knowledge Base Position

```text
contents/
└── analysis/
    ├── 00-index.md
    ├── 01-real-number-theory.md
    ├── 02-intorno.md              ← current
    └── 03-limits.md
```

## Knowledge Map

```text
intorno-e-punto-di-accumulazione/
├── 01-definition/
│   ├── intorno
│   ├── intorno-destro-e-sinistro
│   ├── intorno-bucato
│   ├── punto-di-accumulazione
│   ├── equivalent-formulations
│   └── precise-negation
├── 02-intuition/
│   ├── observation-window
│   ├── set-of-valid-points
│   ├── membership-vs-accumulation
│   └── examples-and-counterexamples
├── 03-results/
│   ├── quantifier-roles
│   ├── witness-construction
│   ├── x0-plus-or-minus-r
│   ├── min-technique
│   └── blocking-radius
├── 04-connections/
│   ├── absolute-value-and-distance
│   ├── set-operations
│   ├── archimedean-property
│   ├── isolated-points
│   └── limits
└── 05-exercises/
    ├── esercizio-1-20
    ├── basic-classification
    ├── discrete-set
    ├── esercizio-3-1
    ├── mistake-archive
    └── exam-versions
```

## Dependency Flow

```text
[[01-real-number-theory]]
    ├── intervalli e operazioni tra insiemi
    ├── valore assoluto come distanza
    └── proprietà archimedea
            ↓
[[02-intorno]]
    ├── intorno bucato
    └── punto di accumulazione
            ↓
[[03-limits]]
    ├── limite finito
    └── limiti laterali
```

## Learning Route

1. 稳定区分完整邻域、左右邻域和去心邻域。
2. 用自然语言和符号写出聚点定义。
3. 明确每个变量和量词的角色。
4. 用成员关系反例建立定义边界。
5. 学会从集合结构决定见证形式。
6. 掌握 $x=x_0\pm r$ 与 `min` 的区间构造。
7. 掌握“选择一个 $\delta_0$”的非聚点证明。
8. 完成 Esercizio 3.1 的两个包含方向。
9. 压缩为意大利语考试版本。
10. 进入 [[03-limits]] 时重新调用本定义。

## Symbols and Terminology

| Symbol / Term | Meaning | Role | Common Confusion |
|---|---|---|---|
| $x_0$ | 候选中心 | 固定后检查是否为聚点 | 与见证 $x$ 混淆 |
| $\delta>0$ | 邻域半径 | 聚点证明中任意给定 | 错误地主动指定 |
| $\delta_0>0$ | 阻断半径 | 非聚点证明中主动选择 | 误以为也需任意 |
| $x$ | 集合中的见证点 | 在看到 $\delta$ 后选择 | 误认为必须任意或唯一 |
| $r$ | 辅助距离 | 控制接近程度和成员关系 | 误认为是凭空技巧 |
| $U_\delta(x_0)$ | 完整邻域 | 包含 $x_0$ | 与去心邻域混淆 |
| $U_\delta^*(x_0)$ | 去心邻域 | 删除 $x_0$ | 忘记 $0<|x-x_0|$ |
| punto di accumulazione | 聚点 | 集合在该点附近不可被隔离 | 与集合成员混淆 |

## Sources

| Source | Section / Page | Used For | Note |
|---|---|---|---|
| Annalisa Malusa, *Primo corso di Analisi matematica* | Definizione 1.19, p. 20 | 邻域及左右邻域 | 课程教材表述 |
| Annalisa Malusa, *Primo corso di Analisi matematica* | Definizione 3.1, p. 137 | 聚点定义 | 课程教材表述 |
| Annalisa Malusa, *Primo corso di Analisi matematica* | Esercizi 1.20 e 3.1 | 练习题 | 课程教材题目 |
| `02-intorno.md` 原始草稿 | 全文 | Stage A 个人思维快照 | 保留错误、重复和疑问 |
| 当前可见学习对话 | 2026-08-01–2026-08-02 | 构造方法、错误诊断、熟练度证据 | 只提取本主题数学内容 |

## Functional Role

本主题把“实数轴上的距离”和“集合在一点附近的局部结构”连接起来。它提供：

- 极限中“$x$ 接近 $x_0$”的严格语言；
- 判断定义域是否能从其他点逼近 $x_0$ 的条件；
- 构造见证与反例的基础训练；
- 量词顺序和精确否定的典型范例。

## Typed Connections

**Prerequisites**

- [[01-real-number-theory]]：绝对值、不等式和阿基米德性质支撑距离估计与序列型见证。
- 区间与集合运算：用于表示邻域、去心和交集。

**Enables**

- [[03-limits]]：函数在 $x_0$ 处的极限以 $x_0$ 为定义域的聚点为前提。
- `XX-one-sided-limits.md`：左右邻域发展为单侧极限。

**Used in**

- 极限的定义证明；
- 连续性；
- 序列与函数局部行为；
- 判断孤立点和局部结构。

**Contrasts with**

- 集合成员关系：$x_0\in A$ 不等价于 $x_0$ 是聚点。
- 孤立点：属于集合，但存在去心邻域不含其他集合点。

## Exam Role

- **Direct relevance**：high
- **Structural relevance**：high
- **Required depth**：能写定义、精确否定、标准见证构造、阻断半径，并独立完成教材 Esercizio 3.1。
- **Stop criterion**：能在无提示下证明一个开区间的聚点集合是其闭包，并写出简洁意大利语版本；暂不深入一般拓扑推广。

# Knowledge Framework

## Stage B — Refined Synthesis

> 本阶段依据被冻结的 Stage A、当前可见对话中与本主题直接相关的数学学习过程，以及课程教材中的 Definizione 1.19、Definizione 3.1、Esercizio 1.20 和 Esercizio 3.1 完成。这里的精炼内容不回写 Stage A。

### Definition — What Is It?

#### 1. 邻域

**邻域 (Intorno; neighborhood)** 描述实数轴上以 $x_0$ 为中心、与 $x_0$ 的距离小于 $\delta$ 的全部点。

**Definizione rigorosa**

*L’intorno di $x_0\in\mathbb R$ di ampiezza $\delta>0$ è l’intervallo aperto*

$$
(x_0-\delta,x_0+\delta).
$$

等价地，

$$
x\in(x_0-\delta,x_0+\delta)
\iff
|x-x_0|<\delta.
$$

为便于书写，可以记作

$$
U_\delta(x_0)=(x_0-\delta,x_0+\delta).
$$

教材还定义：

$$
U_\delta^+(x_0)=(x_0,x_0+\delta)
$$

为右邻域，以及

$$
U_\delta^-(x_0)=(x_0-\delta,x_0)
$$

为左邻域。

必须区分：

- 完整邻域 $U_\delta(x_0)$ **包含**中心 $x_0$；
- 左邻域和右邻域是开区间，均**不包含**中心 $x_0$；
- 去心邻域是从完整邻域中删除中心：

$$
U_\delta^*(x_0)
=
U_\delta(x_0)\setminus\{x_0\}
=
\{x\in\mathbb R:0<|x-x_0|<\delta\}.
$$

#### 2. 聚点

**聚点 (Punto di accumulazione; accumulation point)** 是点 $x_0$ 相对于集合 $A$ 所具有的性质：无论把以 $x_0$ 为中心的邻域缩得多小，其中都能找到一个属于 $A$ 且不同于 $x_0$ 的点。

**Definizione rigorosa**

*Sia $A\subseteq\mathbb R$. Diremo che $x_0\in\mathbb R$ è un punto di accumulazione di $A$ se ogni intorno di $x_0$ contiene punti di $A$ distinti da $x_0$ stesso.*

符号形式为

$$
\forall\delta>0,
\qquad
U_\delta^*(x_0)\cap A\neq\varnothing.
$$

等价地，

$$
\forall\delta>0\;
\exists x\in A:
0<|x-x_0|<\delta.
$$

#### Objects and Logical Roles

| Object | Fixed / Arbitrary / Chosen | Mathematical Role |
|---|---|---|
| $A$ | 题目给定 | 正在研究的集合，决定哪些见证点有效 |
| $x_0$ | 候选点；证明中先固定 | 被检查是否为聚点的中心 |
| $\delta$ | 任意给定，随后固定 | 邻域半径，可以任意小 |
| $x$ | 在看到 $x_0$ 与 $\delta$ 后选择 | 属于 $A$ 的见证点 |
| $r$ | 证明者选择的辅助距离 | 控制 $x$ 与 $x_0$ 的距离及集合成员关系 |

#### Quantifier Structure and Logical Flow

要证明某个固定的 $x_0$ 是 $A$ 的聚点：

$$
\forall\delta>0\;\exists x\in A:
0<|x-x_0|<\delta.
$$

量词顺序表示：

1. 先固定候选点 $x_0$；
2. 对方任意给出 $\delta>0$；
3. 我们可以根据 $x_0$、$\delta$ 和集合 $A$ 选择 $x$；
4. 验证 $x\in A$ 与 $0<|x-x_0|<\delta$。

见证点可以依赖于 $\delta$：

$$
x=x(\delta)
$$

或更一般地，

$$
x=\Phi(x_0,\delta).
$$

定义不要求同一个 $x$ 同时适用于所有 $\delta$。

若要证明区间中每个点都是聚点，量词结构是

$$
\forall x_0\in I\;
\forall\delta>0\;
\exists x\in A:
0<|x-x_0|<\delta.
$$

“任取 $x_0\in I$”之后，$x_0$ 在当前证明中是**任意但固定**的实数。

#### Precise Negation

$x_0$ 不是 $A$ 的聚点，当且仅当

$$
\exists\delta_0>0:
U_{\delta_0}^*(x_0)\cap A=\varnothing.
$$

等价地，

$$
\exists\delta_0>0\;
\forall x\in A\setminus\{x_0\},
\qquad
|x-x_0|\geq\delta_0.
$$

也可以写成

$$
\exists\delta_0>0\;
\forall x\in A,
\qquad
x=x_0
\quad\text{或}\quad
|x-x_0|\geq\delta_0.
$$

最后一种写法保留了 $x_0\in A$ 的可能性，不能随意省略 $x=x_0$ 这一分支。

#### Definition Boundary

定义要求：

- 对每一个 $\delta>0$，至少存在一个有效见证；
- 见证必须属于 $A$；
- 见证必须不同于 $x_0$；
- 见证与 $x_0$ 的距离必须小于 $\delta$。

定义不要求：

- $x_0\in A$；
- 邻域中的每个点都属于 $A$；
- 同一个见证适用于所有 $\delta$；
- 见证由唯一公式给出；
- 证明者在“是聚点”的证明中主动选择 $\delta$。

### Intuition — Why Is It Needed?

#### Core Intuition

邻域告诉我们“去哪里看”，集合 $A$ 告诉我们“哪些点有效”。

$$
\underbrace{U_\delta^*(x_0)}_{\text{寻找区域}}
\cap
\underbrace{A}_{\text{允许使用的点}}
$$

聚点定义问的是：

> 无论观察窗口缩得多小，是否总能在窗口中发现另一个属于 $A$ 的点？

因此，聚点刻画的是集合在 $x_0$ 附近是否可以无限逼近，而不是单纯判断 $x_0$ 是否属于集合。

#### Canonical Examples

##### Example 1 — $0$ 是 $(0,1)$ 的聚点

虽然

$$
0\notin(0,1),
$$

但任取 $\delta>0$，令

$$
x=\min\left\{\frac{\delta}{2},\frac12\right\}.
$$

则

$$
x\in(0,1)
$$

且

$$
0<|x-0|=x<\delta.
$$

因此 $0$ 是 $(0,1)$ 的聚点。

##### Example 2 — $0$ 不是 $\{0\}$ 的聚点

取 $\delta_0=1$，则

$$
\left[(-1,1)\setminus\{0\}\right]\cap\{0\}
=
\varnothing.
$$

因此 $0$ 不是 $\{0\}$ 的聚点。

##### Example 3 — $0$ 是 $\left\{\frac1n:n\in\mathbb N^+\right\}$ 的聚点

任取 $\delta>0$。由阿基米德性质，存在 $n\in\mathbb N^+$ 使

$$
n>\frac1\delta.
$$

因为 $n,\delta>0$，所以

$$
0<\frac1n<\delta.
$$

令

$$
x=\frac1n.
$$

则 $x$ 属于该集合，并且

$$
0<|x-0|<\delta.
$$

##### Example 4 — $0$ 不是 $\{2n:n\in\mathbb N^+\}$ 的聚点

取 $\delta_0=1$。任意集合点都满足

$$
x=2n\geq2,
$$

所以没有集合点落入 $(-1,1)$。因此 $0$ 不是该集合的聚点。

#### Common Misconceptions

| Misconception | Why It Is Wrong | Correct Replacement |
|---|---|---|
| $x_0\notin A$，所以 $x_0$ 不是聚点 | 聚点定义检查附近是否有 $A$ 的其他点 | 成员关系与聚点性质相互独立 |
| $x_0\in A$，所以 $x_0$ 是聚点 | 单独存在中心点不够 | 去心邻域中还必须有别的 $A$ 点 |
| 在邻域中“任取”一个 $x$ | 这会暗示对所有 $x$ 成立 | 定义只要求存在至少一个 $x$ |
| 找不到某个候选公式，所以不是聚点 | 一个失败的候选不能排除其他候选 | 不是聚点必须找到一个阻断所有见证的 $\delta_0$ |
| 证明聚点时可以令 $\delta=1$ | $\delta$ 是对方任意给定的 | 任取 $\delta>0$ 后构造 $x$ |
| 证明不是聚点时也要讨论所有 $\delta$ | 否定只要求一个成功的半径 | 主动选择一个 $\delta_0>0$ |

### Results — What Are the Most Important Facts and Results?

#### The Idea Behind the Demonstration

##### Recognition Trigger

题目要求“用定义证明 $x_0$ 是聚点”时，立即写出两个必须同时满足的约束：

$$
\boxed{x\in A}
\qquad\text{和}\qquad
\boxed{0<|x-x_0|<\delta}.
$$

构造见证不是解一个具有唯一答案的方程，而是在允许范围内设计一个满足两个约束的对象。

##### First Observation: 集合中的点长什么样？

集合结构先决定 $x$ 的形式：

- 若 $A$ 是区间，通常从 $x_0$ 向区间内部移动；
- 若 $A=\{\varphi(n):n\in\mathbb N^+\}$，见证必须保持 $x=\varphi(n)$ 的形式；
- 若 $A$ 是离散集合，证明不是聚点时通常寻找正的最小间隔或阻断半径。

##### Why $x=x_0\pm r$ Is Natural

若集合位于 $x_0$ 右侧，令

$$
r=x-x_0>0,
\qquad
x=x_0+r.
$$

若集合位于 $x_0$ 左侧，令

$$
r=x_0-x>0,
\qquad
x=x_0-r.
$$

这只是把距离 $|x-x_0|$ 命名为 $r$。于是

$$
|x-x_0|=r,
$$

距离条件被简化为

$$
0<r<\delta.
$$

真正需要继续解决的是：为了让 $x$ 仍属于 $A$，$r$ 还必须满足什么上界？

##### The `min` Construction

若需要同时满足

$$
0<r<a
\qquad\text{和}\qquad
0<r<b,
$$

其中 $a,b>0$，一个安全选择是

$$
r=\frac12\min\{a,b\}.
$$

于是

$$
r\leq\frac a2<a
\qquad\text{且}\qquad
r\leq\frac b2<b.
$$

必须注意：

$$
\min\{a,b\}\leq a
$$

给出的是 $\leq$，不是直接给出 $<$。严格不等式来自再取一半以及 $a,b>0$。

##### Verification Checklist

构造后依次验证：

1. $r>0$；
2. $x\in A$；
3. $x\neq x_0$；
4. $|x-x_0|=r$；
5. $r<\delta$；
6. 因为 $\delta>0$ 任意，所以结论成立。

#### Standard Proof Template — To Prove Accumulation

固定候选点 $x_0$。任取 $\delta>0$。

根据集合结构选择

$$
r=\frac12\min\{\text{保持成员关系所需的距离},\delta\}
$$

并令

$$
x=x_0+r
$$

或

$$
x=x_0-r.
$$

然后证明

$$
x\in A
$$

和

$$
0<|x-x_0|<\delta.
$$

最后写：

> 因为 $\delta>0$ 是任意的，所以 $x_0$ 是 $A$ 的聚点。

这个模板主要适用于区间或在 $x_0$ 一侧含有连续点段的集合，并不是所有集合的万能公式。

#### Standard Proof Template — To Prove Non-Accumulation

选择一个具体的

$$
\delta_0>0.
$$

证明

$$
U_{\delta_0}^*(x_0)\cap A=\varnothing.
$$

可以通过下列任一方式完成：

- 证明邻域全部位于 $A$ 的左侧或右侧；
- 证明每个 $x\in A\setminus\{x_0\}$ 都满足 $|x-x_0|\geq\delta_0$；
- 假设交集非空，并由集合结构导出矛盾。

#### Compression Summary

```text
证明是聚点：
对方给 δ
    ↓
集合决定 x 的形式
    ↓
选择见证 x
    ↓
验证 x∈A 且 0<|x-x₀|<δ

证明不是聚点：
主动选 δ₀
    ↓
证明这个去心邻域中没有任何 A 的有效点
```

### Connections — How Does It Connect with Other Concepts?

#### 1. 绝对值与距离

$$
|x-x_0|
$$

是在实数轴上测量 $x$ 与 $x_0$ 的距离。邻域定义把区间语言与距离语言连接起来：

$$
x_0-\delta<x<x_0+\delta
\iff
|x-x_0|<\delta.
$$

这依赖 [[01-real-number-theory]] 中的绝对值与不等式。

#### 2. 集合运算

去心邻域和聚点定义使用：

- 差集；
- 交集；
- 空集与非空集；
- 区间端点。

因此，Esercizio 1.20 不只是集合运算练习，也为聚点定义中的

$$
U_\delta^*(x_0)\cap A
$$

准备语言。

#### 3. 阿基米德性质

对于

$$
A=\left\{\frac1n:n\in\mathbb N^+\right\},
$$

需要把“任意小的 $\delta$”转化为“选择足够大的 $n$”。这正是阿基米德性质的作用。

#### 4. 极限

[[03-limits]] 要求 $x_0$ 是函数定义域 $A$ 的聚点，因为极限研究的是：

> 当定义域中的点 $x\neq x_0$ 任意接近 $x_0$ 时，函数值怎样变化。

如果 $x_0$ 附近没有定义域中的其他点，“令 $x\to x_0$”就缺少需要考察的输入点。

#### 5. 孤立点

若 $x_0\in A$，并且存在 $\delta_0>0$ 使

$$
U_{\delta_0}^*(x_0)\cap A=\varnothing,
$$

那么 $x_0$ 是 $A$ 的孤立点。孤立点属于集合，但不是聚点。这一对比能防止把成员关系与聚点性质混为一谈。

### Exercises — Have I Genuinely Learned How to Apply It?

#### Esercizio 1.20 — Set Operations with Neighborhoods

已知：

$$
A=(-1,3),
\qquad
B=(0,1).
$$

因此

$$
A\cup B=(-1,3),
$$

$$
A\cap B=(0,1),
$$

$$
A\setminus B=(-1,0]\cup[1,3),
$$

$$
B\setminus A=\varnothing.
$$

关键识别：$B$ 是右邻域，而不是完整邻域。

#### Basic Classification Exercise

判断 $0$ 是否是下列集合的聚点：

$$
A_1=(0,1),
\qquad
A_2=\{0\},
\qquad
A_3=\left\{\frac1n:n\in\mathbb N^+\right\}.
$$

结论：

$$
0\text{ 是 }A_1\text{ 的聚点},
$$

$$
0\text{ 不是 }A_2\text{ 的聚点},
$$

$$
0\text{ 是 }A_3\text{ 的聚点}.
$$

判断依据始终是去心邻域中是否存在集合点，而不是 $0$ 是否属于集合。

#### Classical Exercise — A Discrete Set

设

$$
E=\{2n:n\in\mathbb N^+\}.
$$

取 $\delta_0=1$。对任意 $x\in E$，存在 $n\in\mathbb N^+$ 使

$$
x=2n\geq2.
$$

因此

$$
x\notin(-1,1),
$$

从而

$$
\left[(-1,1)\setminus\{0\}\right]\cap E=\varnothing.
$$

所以 $0$ 不是 $E$ 的聚点。

**Versione per l’esame**

*Poniamo $x_0=0$ e scegliamo $\delta_0=1$. Per ogni $x\in E$ esiste $n\in\mathbb N^+$ tale che $x=2n\geq2$. Pertanto $x\notin(-1,1)$ e quindi*

$$
\left[(-1,1)\setminus\{0\}\right]\cap E=\varnothing.
$$

*Ne segue che $0$ non è un punto di accumulazione di $E$.*

#### Construction Training — Left Endpoint

设

$$
A=(-6,1).
$$

证明 $1$ 是 $A$ 的聚点。任取 $\delta>0$，令

$$
r=\frac12\min\{7,\delta\},
\qquad
x=1-r.
$$

因为

$$
0<r\leq\frac72<7,
$$

所以

$$
-6<1-r<1,
$$

即 $x\in A$。同时

$$
0<|x-1|=r\leq\frac{\delta}{2}<\delta.
$$

因此 $1$ 是 $A$ 的聚点。

#### Esercizio 3.1

证明集合

$$
A=(0,1)\cup(1,2)
$$

的聚点集合恰好为

$$
[0,2].
$$

证明分为两个方向。

##### 第一方向：每个 $x_0\in[0,2]$ 都是聚点

任取 $\delta>0$。

**情形 1：$x_0\in[0,1)$**

令

$$
r=\frac12\min\{\delta,1-x_0\},
\qquad
x=x_0+r.
$$

因为

$$
0<r<1-x_0,
$$

所以

$$
0<x_0+r<1.
$$

因此

$$
x\in(0,1)\subseteq A.
$$

并且

$$
0<|x-x_0|=r\leq\frac{\delta}{2}<\delta.
$$

**情形 2：$x_0=1$**

令

$$
r=\frac12\min\{\delta,1\},
\qquad
x=1+r.
$$

则

$$
1<x<2,
$$

所以 $x\in A$，并且

$$
0<|x-1|=r<\delta.
$$

**情形 3：$x_0\in(1,2]$**

令

$$
r=\frac12\min\{\delta,x_0-1\},
\qquad
x=x_0-r.
$$

因为

$$
0<r<x_0-1,
$$

所以

$$
1<x<x_0\leq2.
$$

又因 $r>0$，有 $x<x_0$；即使 $x_0=2$，也有 $x<2$。因此

$$
x\in(1,2)\subseteq A.
$$

并且

$$
0<|x-x_0|=r\leq\frac{\delta}{2}<\delta.
$$

由三个情形可知，每个 $x_0\in[0,2]$ 都是 $A$ 的聚点。

##### 第二方向：区间外的点都不是聚点

**情形 1：$x_0<0$**

选择

$$
\delta_0=-\frac{x_0}{2}>0.
$$

邻域的右端点为

$$
x_0+\delta_0
=
\frac{x_0}{2}
<
0.
$$

因此

$$
(x_0-\delta_0,x_0+\delta_0)
\subset(-\infty,0),
$$

与 $A\subset(0,2)$ 不相交。所以 $x_0$ 不是 $A$ 的聚点。

**情形 2：$x_0>2$**

选择

$$
\delta_0=\frac{x_0-2}{2}>0.
$$

邻域的左端点为

$$
x_0-\delta_0
=
\frac{x_0+2}{2}
>
2.
$$

因此

$$
(x_0-\delta_0,x_0+\delta_0)
\subset(2,\infty),
$$

与 $A\subset(-\infty,2)$ 不相交。所以 $x_0$ 不是 $A$ 的聚点。

综上，$A$ 的聚点集合为

$$
\boxed{[0,2]}.
$$

##### Versione per l’esame

*Sia $A=(0,1)\cup(1,2)$. Dimostriamo anzitutto che ogni $x_0\in[0,2]$ è un punto di accumulazione di $A$.*

*Sia $\delta>0$.*

- *Se $x_0\in[0,1)$, poniamo*

$$
r=\frac12\min\{\delta,1-x_0\},
\qquad
x=x_0+r.
$$

*Allora $0<x<1$, quindi $x\in A$, e*

$$
0<|x-x_0|=r<\delta.
$$

- *Se $x_0=1$, poniamo*

$$
r=\frac12\min\{\delta,1\},
\qquad
x=1+r.
$$

*Allora $1<x<2$, dunque $x\in A$, e $0<|x-1|=r<\delta$.*

- *Se $x_0\in(1,2]$, poniamo*

$$
r=\frac12\min\{\delta,x_0-1\},
\qquad
x=x_0-r.
$$

*Allora $1<x<2$, quindi $x\in A$, e*

$$
0<|x-x_0|=r<\delta.
$$

*Pertanto ogni punto di $[0,2]$ è di accumulazione per $A$.*

*Viceversa, se $x_0<0$, scegliamo $\delta_0=-x_0/2$. Poiché*

$$
x_0+\delta_0=\frac{x_0}{2}<0,
$$

*l’intorno $(x_0-\delta_0,x_0+\delta_0)$ non interseca $A$.*

*Se invece $x_0>2$, scegliamo $\delta_0=(x_0-2)/2$. Poiché*

$$
x_0-\delta_0=\frac{x_0+2}{2}>2,
$$

*anche in questo caso l’intorno non interseca $A$.*

*Ne segue che l’insieme dei punti di accumulazione di $A$ è esattamente $[0,2]$.*

#### Mistake Archive

##### Mistake 1 — 用成员关系判断聚点

- **Original attempt**：根据 $0\in A$ 或 $0\notin A$ 直接判断。
- **First decisive error**：没有检查去心邻域与 $A$ 的交集。
- **Error type**：定义使用错误。
- **Transfer lesson**：聚点性质与成员关系相互独立。

##### Mistake 2 — 构造的点靠近错误的中心

- **Original attempt**：证明 $x_0=1$ 或 $x_0=2$ 时选择 $x=\delta/2$。
- **First decisive error**：$\delta/2$ 天然靠近 $0$，不保证靠近 $x_0$。
- **Minimal correction**：从候选中心出发，令 $x=x_0\pm r$。
- **Transfer lesson**：先确定中心，再设计距离。

##### Mistake 3 — 一个候选失败就宣布不是聚点

- **Why it fails**：存在性命题允许许多不同见证；一个公式失败不能排除其他见证。
- **Correct replacement**：证明不是聚点必须给出一个 $\delta_0$，阻断所有 $x\in A\setminus\{x_0\}$。

##### Mistake 4 — 混淆 `min` 的严格与非严格不等式

由

$$
r=\frac12\min\{a,b\}
$$

应先写

$$
r\leq\frac a2,
\qquad
r\leq\frac b2,
$$

再利用 $a,b>0$ 得到

$$
r<a,
\qquad
r<b.
$$

##### Mistake 5 — 在正式存在性证明中先假设 $x\in A$

草稿可以倒推“若 $x\in A$，则它必须满足什么”；正式证明应先定义 $x$，再验证 $x\in A$。

##### Mistake 6 — 任意点证明中遗漏任取 $\delta>0$

证明

$$
\forall x_0\in I,
\quad
x_0\text{ 是聚点}
$$

时，开头必须包含：

> 任取 $x_0\in I$，并任取 $\delta>0$。

##### Mistake 7 — 阻断邻域时证明了错误的端点界

对于 $x_0>2$，需要证明

$$
x_0-\delta_0>2,
$$

而不仅仅是大于 $0$。只有这样才能推出整个邻域位于 $(2,\infty)$。

#### Self-Test

1. 不看笔记写出邻域、左右邻域和去心邻域。
2. 不看笔记写出聚点定义及其精确否定。
3. 解释 $A$、$x_0$、$\delta$、$x$、$r$ 的角色。
4. 说明为什么 $x_0\in A$ 与“$x_0$ 是聚点”互不推出。
5. 对区间端点，根据集合方向独立构造 $x=x_0\pm r$。
6. 对参数集合保留集合规定的元素形式并选择参数。
7. 证明不是聚点时，独立选择一个阻断半径。
8. 不看解答重写 Esercizio 3.1 的两个方向。
9. 将完整证明压缩成意大利语考试版本。

## Revision Bridge — From Personal Thought to Refined Mathematics

### What I Originally Thought

- 最初倾向于通过 $x_0\in A$ 或 $x_0\notin A$ 判断聚点。
- 曾把聚点理解为邻域中选出的 $x$，而不是正在考察的中心 $x_0$。
- 知道定义要求找到 $x\in A$，但不知道见证点的表达式从何而来。
- 面对区间时先尝试按 $\delta$ 的大小分情况，并选择 $\delta/2$ 或 $1/\delta$。
- 对证明“不是聚点”的量词结构不稳定，最初仍想讨论任意 $\delta$。
- 经过多轮练习后，逐渐形成“中心 $\pm$ 距离”和 `min` 统一构造。

### What Was Already Correct

- 已经准确意识到邻域是围绕 $x_0$ 的观察区域。
- 已经抓住聚点定义中的量词顺序 $\forall\delta>0\,\exists x\in A$。
- 已经认识到见证 $x$ 可以依赖于 $\delta$。
- 已经理解集合 $A$ 决定哪些点可以作为见证。
- 已经能够在区间位于中心左侧或右侧时，使用 $x=x_0\mp r$。
- 已经能够利用 `min` 同时满足距离限制和成员关系限制。
- 已经完成了离散集合的阻断半径证明，并能处理 $x_0<0$、$x_0>2$ 的外部点。

### What Needed Correction

| Stage A Passage | Error / Limitation | Refined Replacement | Why the Change Matters |
|---|---|---|---|
| A-004：“左右邻域包含 $x_0$，完整邻域不包含” | 结论完全相反 | 完整邻域包含中心；左右邻域不包含；去心邻域删除中心 | 决定后续定义中使用哪一个集合 |
| A-005 中 `\setminus{x_0}` 及下标说明 | 集合花括号与 `\underbrace` LaTeX 不完整 | `\setminus\{x_0\}`，并使用 `_{\text{...}}` | 保证符号表示正确集合且可渲染 |
| A-008 中“等价条件 $|x-x_0|<0$” | 距离小于零不可能成立 | 应为 $0<|x-x_0|<\delta$ | 这是去心邻域的核心条件 |
| A-009 根据成员关系判断聚点 | 定义使用错误 | 检查每个去心邻域是否含 $A$ 的点 | 成员关系与聚点性质相互独立 |
| A-011 对 $x_0=1,2$ 选择 $x=\delta/2$ | 见证靠近 $0$，不一定靠近中心 | 使用 $x=x_0\pm r$ | 构造必须围绕候选中心 |
| A-011 一个分情况计算失败后改变 $\delta$ | 破坏“任取 $\delta>0$” | 对给定 $\delta$ 构造有效见证；或用 `min` 统一 | 保持量词顺序 |
| A-014 `\min{7,\delta}` | LaTeX 花括号范围错误 | `\min\{7,\delta\}` | 保证函数参数正确渲染 |
| A-015 未明确任取 $\delta>0$ | 量词缺失 | “任取 $x_0\in(1,2)$，并任取 $\delta>0$” | 证明必须覆盖每个邻域 |
| A-015 由 $x_0>1$ 推出 $x\in(1,2)$ | 使用了错误的上界条件 | 由 $1<x<x_0$ 与 $x_0<2$ 推出 | 成员关系验证必须使用完整条件 |
| 外部点 $x_0>2$ 的初次证明 | 只证明邻域左端点 $>0$ | 必须证明左端点 $>2$ | 才能推出邻域与 $A$ 不相交 |

### What Became More Precise

- “找一个 $x$”被精确为：设计一个满足 $x\in A$ 与 $0<|x-x_0|<\delta$ 的见证。
- “令 $r=x-x_0$”不再被视为灵感，而被理解为给距离命名。
- “任意但固定”被用于解释参数 $x_0$ 和 $\delta$ 的证明角色。
- “不是聚点”被写成精确否定，而不是模糊地说“不等式没有解”。
- `min` 的使用从分情况技巧升级为同时控制多个上界的统一工具。
- Esercizio 3.1 从只验证 $0,1,2$，扩展为证明整个 $[0,2]$，并补全区间外点的排除。

### What Was Compressed but Preserved in Stage A

Stage B 没有逐字重复：

- 对同一量词结构的多次解释；
- Esercizio 3.1 中多个失败的分情况计算；
- 端点 $0,1,2$ 的重复证明过程；
- 对 `min` 的多轮反复验证；
- 多个由助教逐步提示形成的中间版本。

这些内容仍完整保存在 Stage A，用于回看个人认知变化；Stage B 只保留可迁移的最终结构。

### Remaining Difficulties

- 目前能够在相似区间题中使用 $x=x_0\pm r$，但独立面对新集合时，见证形式仍可能需要提示。
- 容易在正式证明中遗漏“任取 $\delta>0$”或先假设待构造的 $x\in A$。
- 使用 `min` 时仍需稳定区分 $\leq$ 与 $<$。
- 能够理解完整证明，但尚需训练在无提示条件下重构 Esercizio 3.1。
- 意大利语考试版目前可以核验，但独立压缩能力仍需练习。

### Next Review Target

不看 Stage B，独立证明：

$$
A=(2,5)
$$

的聚点集合为

$$
[2,5].
$$

要求：

1. 写出两个包含方向；
2. 区分“任取 $\delta>0$”与“选择一个 $\delta_0>0$”；
3. 至少有一个区间内部点使用任意但固定的 $x_0$；
4. 最后写出不超过十行的意大利语考试版本。

