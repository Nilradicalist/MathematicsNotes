# 1 实数理论 (Teoria dei Numeri Reali)

## 引言：为什么我们需要重新定义数字？


---

## 1.1 域公理 (Assiomi di Campo)

假设我们在集合 $\mathbb{R}$ 上定义了两种二元运算：**加法 (Addizione)**，记作 $+$ ；以及 **乘法 (Moltiplicazione)**，记作 $\cdot$ 。
为了让 $\mathbb{R}$ 构成一个**域 (Campo)**，这两种运算必须满足以下 11 条基础公理（我们将它们分为加法、乘法以及两者的结合来讲解）。

### 1.1.1 加法公理与阿贝尔群

如果只看加法运算，集合 $\mathbb{R}$ 和加法 $+$ 共同构成了一个 **阿贝尔群 / 交换群 (Gruppo Abeliano)**。具体需要满足以下 5 条规则：

* **A1. 封闭性 (Chiusura rispetto all'addizione):**
    文字语言：对于任意 $a, b \in \mathbb{R}$，它们的和也是实数，即 $a + b \in \mathbb{R}$。
    数学符号：$$\forall a, b \in \mathbb{R}, \quad (a + b) \in \mathbb{R}$$
    *(注：加法是一个从 $\mathbb{R} \times \mathbb{R} \rightarrow \mathbb{R}$ 的映射。)*
    *(注：在严谨的代数定义中，封闭性通常包含在“二元运算”的定义本身中，但在初学时单独列出有助于理解体系的自洽性。)*
* **A2. 结合律 (Proprietà associativa dell'addizione):**
    文字语言：对于任意 $a, b, c \in \mathbb{R}$，满足 $(a + b) + c = a + (b + c)$。
    数学符号：$$\forall a, b, c \in \mathbb{R}, \quad (a + b) + c = a + (b + c)$$
    *(注：这说明多个数相加时，先算哪一部分都不影响最终结果，因此我们可以放心地去掉括号。)*
* **A3. 加法交换律 (Proprietà commutativa dell'addizione):**
    文字语言：对于任意 $a, b \in \mathbb{R}$，满足 $a + b = b + a$。
    数学符号：$$\forall a, b \in \mathbb{R}, \quad a + b = b + a$$
    *(注：这正是“阿贝尔群”中“阿贝尔/交换”一词的来源。正是因为满足这一条，$(\mathbb{R}, +)$ 才被称为**阿贝尔群**，而非普通的群。)*
* **A4. 存在加法单位元 (Esistenza dell'elemento neutro):**
    文字语言：集合 $\mathbb{R}$ 中存在一个特殊的元素，我们记作 $0$，使得对于任意 $a \in \mathbb{R}$，都满足 $a + 0 = 0 + a = a$。
    数学符号：$$\exists 0 \in \mathbb{R}, \quad \forall a \in \mathbb{R}, \quad a + 0 = 0 + a = a$$
* **A5. 存在加法逆元 (Esistenza dell'opposto):**
    文字语言：对于每一个 $a \in \mathbb{R}$，在 $\mathbb{R}$ 中都必定存在另一个元素，我们记作 $-a$，使得 $a + (-a) = (-a) + a = 0$。
    数学符号：$$\forall a \in \mathbb{R}, \quad \exists (-a) \in \mathbb{R}, \quad a + (-a) = (-a) + a = 0$$
    *(注：正因为有了这套规则，我们才在逻辑上“发明”了减法：减去一个数，本质上就是加上它的负元。)*

### 1.1.2 乘法公理与单位交换环

接下来我们加入乘法。集合 $\mathbb{R}$ 在同时配备了加法和乘法后，如果满足以下公理，它将构成一个 **单位交换环 (Anello Commutativo con Unità)**。

* **M1. 封闭性 (Chiusura rispetto alla moltiplicazione):**
    文字语言：对于任意 $a, b \in \mathbb{R}$，它们的积也是实数，即 $a \cdot b \in \mathbb{R}$。
    数学符号：$$\forall a, b \in \mathbb{R}, \quad (a \cdot b) \in \mathbb{R}$$
* **M2. 结合律 (Proprietà associativa della moltiplicazione):**
    文字语言：对于任意 $a, b, c \in \mathbb{R}$，满足 $(a \cdot b) \cdot c = a \cdot (b \cdot c)$。
    数学符号：$$\forall a, b, c \in \mathbb{R}, \quad (a \cdot b) \cdot c = a \cdot (b \cdot c)$$
* **M3. 乘法交换律 (Proprietà commutativa della moltiplicazione):**
    文字语言：对于任意 $a, b \in \mathbb{R}$，满足 $a \cdot b = b \cdot a$。
    数学符号：$$\forall a, b \in \mathbb{R}, \quad a \cdot b = b \cdot a$$
    *(注：这赋予了该环“交换环”的性质。)*
* **M4. 存在单位元 (Esistenza dell'unità):**
    文字语言：集合 $\mathbb{R}$ 中存在一个特殊的元素，我们记作 $1$，且明确要求 $1 \neq 0$，使得对于任意 $a \in \mathbb{R}$，都满足 $a \cdot 1 = 1 \cdot a = a$。
    数学符号：$$\exists 1 \in \mathbb{R}, \quad \forall a \in \mathbb{R}, \quad a \cdot 1 = 1 \cdot a = a$$
    *(注：这赋予了该环“含有单位元”的性质。)*

### 1.1.3 连接加法与乘法的桥梁

加法和乘法不能是两个毫无关联的孤岛，它们必须通过一条规则发生互动，这就是分配律：

* **D1. 分配律 (Proprietà distributiva):**
    文字语言：对于任意 $a, b, c \in \mathbb{R}$，乘法对加法满足分配律：$a \cdot (b + c) = a \cdot b + a \cdot c$。
    数学符号：$$\forall a, b, c \in \mathbb{R}, \quad a \cdot (b + c) = (a \cdot b) + (a \cdot c)$$

*(注：到此为止，满足 A1-A5, M1-M4, D1 的结构，在代数学中被称为**含幺/单位交换环**。比如所有的整数 $\mathbb{Z}$ 就构成这样一个环。但整数无法做除法（比如 $2 \div 3$ 不是整数），为了让系统能够进行无障碍的除法，我们需要添加最后一条规则。)*

### 1.1.4 通向“域”的最后一步

为了让这个环升级为真正的 **域 (Campo)**，我们需要保证除了 $0$ 之外的每一个数都能被“除”。这意味着除 $0$ 以外的全体实数 $\mathbb{R} \setminus \{0\}$ 必须在乘法下构成一个阿贝尔群。

* **M5. 存在倒数 / 乘法逆元 (Esistenza dell'inverso):**
    文字语言：对于任意一个**非零**实数 $a \in \mathbb{R} \setminus \{0\}$，在 $\mathbb{R}$ 中都必定存在另一个元素，记作 $a^{-1}$（或 $\frac{1}{a}$），使得 $a \cdot a^{-1} = a^{-1} \cdot a = 1$。
    数学符号：$$\forall a \in \mathbb{R} \setminus \{0\}, \quad \exists a^{-1} \in \mathbb{R}, \quad a \cdot a^{-1} = a^{-1} \cdot a = 1$$
    *(注：0 不能有倒数，这是游戏规则的基础限制。除法本质上就是乘以一个数的逆元：$a \div b = a \cdot b^{-1}$。)*

### 小结
当一个集合同时满足了上述的 11 条公理（或者抛开默认的封闭性，称为 9 条公理）时，我们说这个集合构成了一个 **域 (Campo)**。实数集 $\mathbb{R}$ 是一个域，有理数集 $\mathbb{Q}$ 也是一个域。仅仅依靠域公理，我们无法区分有理数和实数，这就引出了我们下一节要讲的——序公理与完备性公理。

---

<div style="page-break-after: always;"></div>

## 1.2 序公理 (Assiomi di Ordine)

### 1.2.1 为什么我们需要“序”？
在上一节中，我们学习了**域公理 (Assiomi del Campo)**。域公理赋予了实数集合加法和乘法的运算规则。但是，光有运算是不够的。
想象一个没有刻度的钟表，或者一堆杂乱无章的数字，如果没有规定谁大谁小，我们就无法谈论“距离”、“极限”或者“逼近”——这些恰恰是微积分的核心。
因此，我们需要引入第二套规则：**序公理**。它的作用是给这堆数字排出一个绝对的先后顺序，把实数变成一条有方向的、一维的“数轴”。

### 1.2.2 定义

**定义1：序关系本身的公理 (Assiomi della Relazione d'Ordine)**：
设 $\mathbb{R}$ 是一个满足域公理的集合，如果在这个集合上定义了一个二元关系 $\le$，并且满足以下所有条件，我们就称 $\mathbb{R}$ 是一个**有序域 (Campo Ordinato)**：
对于任意 $x, y, z \in \mathbb{R}$：
1.  **自反性 (Riflessività):** 
    文字语言：对于任意 $x \in \mathbb{R}$，满足 $\quad x \le x$。
    数学符号：$$\forall x \in \mathbb{R}, \quad x \le x$$
2.  **反对称性 (Antisimmetria):** 
    文字语言：如果 $x \le y$ 且 $y \le x$，则 $x = y$。
    数学符号：$$(x \le y \land y \le x) \implies x = y$$
3.  **传递性 (Transitività):** 
    文字语言：如果 $x \le y$ 且 $y \le z$，则 $x \le z$。
    数学符号：$$(x \le y \land y \le z) \implies x \le z$$
4.  **全序性 (Totalità / Tricotomia):** 
    文字语言：对于任意 $x, y \in \mathbb{R}$，满足 $x \le y$ 或 $y \le x$。
    数学符号：$$\forall x, y \in \mathbb{R}, \quad x \le y \lor y \le x$$

**定义2：三歧性 (Tricotomia)**：
设 $\mathbb{F}$ 是一个域。如果在 $\mathbb{F}$ 中存在一个子集 $P$（我们称 $P$ 为正数集），并且 $P$ 满足以下三条**序公理 (Assiomi dell'Ordine)**，我们就称 $\mathbb{F}$ 是一个**有序域 (Campo Ordinato)**：
1.  **三歧性 (Tricotomia)**：对于域 $\mathbb{F}$ 中的任意元素 $x$，以下三种情况**有且仅有一种**成立：
    * $x \in P$ （$x$ 是正数）
    * $-x \in P$ （$-x$ 是正数，即 $x$ 是负数）
    * $x = 0$
2.  **加法封闭性 (Chiusura rispetto all'addizione)**：如果 $x \in P$ 且 $y \in P$，那么必有 $(x + y) \in P$。
    *(注：正数加正数，还是正数)*
3.  **乘法封闭性 (Chiusura rispetto alla moltiplicazione)**：如果 $x \in P$ 且 $y \in P$，那么必有 $(x \cdot y) \in P$。
    *(注：正数乘正数，还是正数)*

**定义：序与运算的相容性公理 (Assiomi di Compatibilità)**
对于任意 $x, y, z \in \mathbb{R}$：
6.  **与加法的相容性 (Compatibilità con l'addizione):** 
    文字语言：如果 $x \le y$，则 $x + z \le y + z$。
    数学符号：$$x \le y \implies x + z \le y + z$$
7.  **与乘法的相容性 (Compatibilità con la moltiplicazione):** 
    文字语言：如果 $0 \le x$ 且 $0 \le y$，则 $0 \le x \cdot y$。
    数学符号：$$(0 \le x \land 0 \le y) \implies 0 \le x \cdot y$$

### 1.2.3 全序性和三歧性的异同

**它们在逻辑上是等价的，但描述的对象不同：一个是针对“非严格不等号 $\le$”，另一个是针对“严格不等号 $<$”。**

1.  **全序性 (Ordine Totale)** 是用来定义 **$\le$** 的。
    在一个集合中，如果关系 $\le$ 满足自反性、反对称性和传递性，我们叫它“偏序 (Ordine Parziale)”。加上“全序性”，意思是**任意两个元素都可以比较大小**：对于任意 $a, b$，必然有 $a \le b$ 或者 $b \le a$（这两者可以同时成立，此时 $a = b$）。
2.  **三歧性 (Tricotomia)** 是用来定义 **$<$** 的。
    意思是，对于任意 $a, b$，以下三种情况**有且仅有一种**成立：$a < b$，$a = b$，$b < a$。

在代数中，只要有了 $\le$ 就可以定义 $<$ （即 $a \le b$ 且 $a \neq b$）；反之，有了 $<$ 也可以定义 $\le$。
如果用 $\le$ 来构建序公理，就需要写“全序性”；如果用 $<$ 来构建（或者用“正数集 $P$”来构建），就会自然推导出“三歧性”。两者可以互相无缝推导。


### 1.2.4. 由公理推导出的定理与性质 (Teoremi e Proprietà Deducibili)

有了以上几条犹如宪法般的公理，我们就可以通过纯逻辑推理，得出所有我们在高中见过的所有不等式规则。数学最迷人的地方：**从最少的假设，推导出整个世界。**

**性质 1：正数的相反数一定是负数。**
* **描述：** 如果 $x > 0$，那么 $-x < 0$。
* **证明：** 已知 $0 \le x$。根据加法相容性公理，我们在不等式两边同时加上 $(-x)$。
    得到 $0 + (-x) \le x + (-x)$。
    根据域公理中关于“零元”和“相反数”的定义，$0 + (-x) = -x$，且 $x + (-x) = 0$。
    因此得到 $-x \le 0$。由于 $x \neq 0$，则 $-x \neq 0$，所以 $-x < 0$。证毕。

**性质 2：任何非零实数的平方必定大于零。**
* **定理:** $\forall x \in \mathbb{R}, x \neq 0 \implies x^2 > 0$
* **证明：** 根据全序性公理，既然 $x \neq 0$，那么对于 $x$ 只有两种可能：
    情况一：$x > 0$。根据乘法相容性公理，$x \cdot x > 0$，即 $x^2 > 0$。
    情况二：$x < 0$。由性质 1 可知 $-x > 0$。根据乘法相容性公理，$(-x) \cdot (-x) > 0$。根据上一节域公理推导过的性质，负负得正，即 $(-x)(-x) = x^2$。所以 $x^2 > 0$。
    无论是哪种情况，$x^2 > 0$ 始终成立。证毕。

**推论 1：1 > 0 必定成立。**
* **证明**因为 1 是域的乘法单位元，且 $1 \neq 0$。既然 $1 = 1^2$，根据性质2，任何非零数的平方都大于0，所以 $1 > 0$。
*注：* 这个推论看似废话，但在数学体系中至关重要。它确立了数轴正方向的“基石”，保证了 $0, 1, 2, 3 \dots$ 会向着右边无限延伸，而不会像复数系 $\mathbb{C}$ 那样无法比较大小。

---

<div style="page-break-after: always;"></div>

## 1.3 完备性公理 (L'Assioma di Completezza)

### 1.3.1 引入：为什么我们需要完备性公理？
在前面的第一节和第二节中，我们已经学习了**域公理 (Assiomi del Campo)**（保证了加减乘除的顺利进行）和**序公理 (Assiomi dell'Ordine)**（保证了数字之间可以比较大小）。

**一个关键的问题出现了：** 我们熟知的有理数集合 $\mathbb{Q}$（即所有的分数）完美地满足了域公理和序公理。那么，仅仅用有理数够用吗？我们为什么还需要实数 $\mathbb{R}$？

**答案是：有理数的数轴上充满了“漏洞” (Buchi)。**
早在古希腊时期，毕达哥拉斯学派就发现了一个引发危机的结论：一个边长为 $1$ 的正方形，其对角线的长度（即 $\sqrt{2}$）不能表示为任何两个整数的比例。换句话说，方程 $x^2 = 2$ 在有理数集 $\mathbb{Q}$ 中无解。如果我们只在有理数的世界里做微积分，当我们试图逼近某个极限时，可能会掉进这些“漏洞”里。

为了填补这些漏洞，让数轴变得“连续”且“没有缝隙”，我们需要引入实数系统的最后一块拼图——**完备性公理**。

### 1.3.2 核心预备概念：上界与确界

在引出完备性公理之前，我们需要先定义几个严格的数学概念。

#### 1.3.2.1 上界与下界 (Maggiorante e Minorante)
> **定义 3.2.1**：设 $A$ 是实数集 $\mathbb{R}$ 的一个非空子集（$A \subset \mathbb{R}, A \neq \emptyset$）。
> - 如果存在一个实数 $M \in \mathbb{R}$，使得对于集合 $A$ 中的**所有**元素 $x$，都有 $x \le M$，那么我们称 $M$ 是集合 $A$ 的一个**上界 (Maggiorante)**。此时称集合 $A$ 是**上有界的 (Limitato superiormente)**。
> - 同理，如果存在一个实数 $m \in \mathbb{R}$，使得对于集合 $A$ 中的所有元素 $x$，都有 $m \le x$，那么我们称 $m$ 是集合 $A$ 的一个**下界 (Minorante)**。

*注：想象 $A$ 是一群人的身高集合。如果存在一个人（不一定在这群人里），他比这群人里的任何一个都要高或者一样高，他就是这群人的“上界”。显然，上界如果存在，就有无数个（任何比上界还要高的数字，自然也是上界）。*

#### 1.3.2.2 上确界与下确界 (Estremo Superiore e Inferiore)
既然上界有无数个，我们自然会关心：这无数个上界中，**最小的那一个**是多少？这就引出了上确界的概念。

> **定义 3.2.2**：设 $A$ 是 $\mathbb{R}$ 的一个非空子集，且是有界的。
> 实数 $S$ 被称为集合 $A$ 的**上确界 (Estremo Superiore, 记作 $\sup A$)**，如果它满足以下两个条件：
> 1. $S$ 是集合 $A$ 的一个上界（即 $\forall x \in A, x \le S$）。
> 2. $S$ 是**最小的**上界。严谨地说，对于任何比 $S$ 小的数字 $S - \epsilon$（其中 $\epsilon > 0$），它都不再是 $A$ 的上界。即：
> $$\forall \epsilon > 0, \exists x \in A \text{ 使得 } x > S - \epsilon$$

*注：同样，最大的下界被称为**下确界 (Estremo Inferiore, 记作 $\inf A$)**。上确界就像是紧紧贴着集合顶部的天花板，哪怕往下移动无穷小的一点点，都会砸到集合里的人。*

### 1.3.3 完备性公理 (L'Assioma di Completezza / Assioma di Dedekind)

现在，我们可以给出实数理论中最核心的基石了。

> **完备性公理**：
> 任何非空的、有上界的实数子集，在实数集中**必然存在**上确界。
> （Ogni sottoinsieme non vuoto di $\mathbb{R}$ limitato superiormente ammette estremo superiore in $\mathbb{R}$.）

**为什么这条公理填补了漏洞？**
让我们回到 $\sqrt{2}$ 的例子。考虑一个有理数集合 $A = \{x \in \mathbb{Q} : x^2 < 2\}$。
这个集合是非空的（例如 $1 \in A$），并且是有上界的（例如 $2$ 就是它的一个上界）。
但是，在有理数集 $\mathbb{Q}$ 中，这个集合**没有**上确界（因为 $\sqrt{2}$ 不是有理数）。有理数在这里断开了！
而完备性公理强行规定了：在**实数集 $\mathbb{R}$** 中，这种集合的上确界必须存在。这个存在的数就是 $\sqrt{2}$。完备性公理保证了实数轴上没有任何断点。

### 1.3.4 完备性公理的推论与定理 (Teoremi Derivati)

有了完备性公理，实数系统就被彻底构建完成了。依靠这最后一条公理，我们可以推导出许多重要的定理。这里我们介绍两个最核心的性质。

#### 定理：阿基米德性质 (Proprietà Archimedea)
> **定理：** 对于任意两个正实数 $x, y \in \mathbb{R}$（其中 $x > 0$），无论 $x$ 多么小，$y$ 多么大，总存在一个自然数 $n \in \mathbb{N}$，使得 $nx > y$。

*注：这在生活中非常直观。哪怕你拿的是一把只有 $1$ 毫米长的短尺（$x$），而你要测量的是地球到月球的距离（$y$），只要你量足够多次（$n$ 次），总能超过那个距离。这意味着实数中不存在“无限大”或“无限小”的元素。*

**证明思路简述（利用反证法和完备性公理）：**
1. 假设定理不成立，即存在某个 $x > 0$ 和 $y > 0$，使得对于**所有**的自然数 $n$，都有 $nx \le y$。
2. 这意味着集合 $A = \{nx : n \in \mathbb{N}\}$ 有一个上界 $y$。
3. 根据**完备性公理**，集合 $A$ 必定存在一个上确界，设为 $S$（$S = \sup A$）。
4. 既然 $S$ 是上确界（最小的上界），那么 $S - x$ 就不能是上界。因此，集合 $A$ 中必然存在某个元素 $mx$（$m$ 为自然数），使得 $mx > S - x$。
5. 在不等式两边同时加上 $x$，得到 $(m+1)x > S$。
6. 但是 $(m+1)x$ 也是集合 $A$ 中的元素（因为 $m+1$ 也是自然数），这与 $S$ 是集合 $A$ 的上界矛盾！
7. 矛盾说明假设错误，定理得证。

#### 定理：有理数在实数中的稠密性 (Densità di $\mathbb{Q}$ in $\mathbb{R}$)
> **定理：** 对于任意两个不相等的实数 $a, b \in \mathbb{R}$（设 $a < b$），在它们之间**至少存在一个**有理数 $q \in \mathbb{Q}$，使得 $a < q < b$。

*注：这说明有理数在实数轴上是密密麻麻、星罗棋布的。无论你用放大镜把两个实数之间的距离放大到多少倍，哪怕它们靠得再近，它们中间也永远塞着无数个有理数。*

**证明逻辑流：**
这个定理的证明正是巧妙地利用了前面证明的**阿基米德性质**。因为 $b - a > 0$，根据阿基米德性质，我们一定能找到一个足够大的分母 $n$，使得 $\frac{1}{n} < b - a$。然后我们再用阿基米德性质找一个分子 $m$，使得 $\frac{m}{n}$ 刚好落在 $a$ 和 $b$ 之间。

### 1.3.5 本章总结 (Conclusione del Capitolo)

至此，实数理论的基础框架已经搭建完毕：
1. **域公理**给了我们加减乘除的四则运算工具；
2. **序公理**给了我们比较大小和建立不等式的规则；
3. **完备性公理**填补了数轴上所有的漏洞，为我们日后研究极限（Limiti）、导数（Derivate）和积分（Integrali）提供了一片坚实连续的“大地”。微积分的大厦，正是拔地起于这条完备性公理之上。

---

## 结语
到此为止，我们完成了实数理论的构建。
满足第一部分的叫**域**，满足前两部分的叫**有序域**。
而同时满足这三大公理的，在数学上被称为**完备的有序域 (Campo Ordinato Completo)**。
伟大的数学家证明了：在同构的意义下，**全宇宙存在且仅存在一个**完备的有序域，这就是我们的**实数集 $\mathbb{R}$**。

有了这条毫无缝隙的坚固数轴，我们终于可以安全地迈向下一个伟大的概念：**极限 (Limite)**。

---



这套证明基于实数集的**确界原理 (Proprietà dell'estremo superiore)**，它是 **Analisi 1** 课程中构建实数连续性（Continuità dei numeri reali）的核心基石。你可以直接将这份严谨的数学推导展示给他们。

---

## 戴德金分割定理 (Teorema di Dedekind sulla continuità di $\mathbb{R}$)

### 定理陈述 (Enunciato del Teorema)

设 $A$ 和 $B$ 是实数集 $\mathbb{R}$ 的两个**非空子集 (sottoinsiemi non vuoti)**，若它们满足以下两个条件：

1. $A \cup B = \mathbb{R}$
2. $\forall a \in A, \forall b \in B \implies a \le b$

则存在唯一的**分隔元 (elemento di separazione)** $c \in \mathbb{R}$，使得：


$$\forall a \in A, \forall b \in B \implies a \le c \le b$$

---

### 严格形式化证明 (Dimostrazione Formale)

我们要证明两部分：**存在性 (Esistenza)** 与 **唯一性 (Unicità)**。

#### 第一部分：存在性证明 (Dimostrazione dell'Esistenza)

1. **证明 $A$ 有上界：**
根据定理条件，集合 $B \neq \emptyset$，因此至少存在一个元素 $b_0 \in B$。
又因为 $\forall a \in A, \forall b \in B \implies a \le b$，所以对于任意的 $a \in A$，都有：

$$a \le b_0$$



这说明 $B$ 中的任意元素都是 $A$ 的一个**上界 (maggiorante)**。因为 $A \neq \emptyset$ 且存在上界，根据 $\mathbb{R}$ 的**确界原理 (Proprietà dell'estremo superiore)**，集合 $A$ 在实数集中必然存在唯一的**上确界 (estremo superiore)**。
我们令这个上确界为 $c$：

$$c = \sup(A) \in \mathbb{R}$$


2. **证明 $c$ 满足分隔不等式：**
* **一方面（对 $A$ 的约束）：** 根据上确界的定义， $c$ 是 $A$ 的上界，因此：

$$\forall a \in A \implies a \le c$$


* **另一方面（对 $B$ 的约束）：** 我们在前一步已经证明了 $B$ 中的任意元素 $b$ 都是 $A$ 的上界。而根据上确界的定义，$c$ 是 $A$ 的**最小上界 (minimo dei maggioranti)**。因此， $c$ 必须小于或等于 $A$ 的任何其他上界。所以：

$$\forall b \in B \implies c \le b$$




3. **结论：**
综合上述两个不等式，我们得到：

$$\forall a \in A, \forall b \in B \implies a \le c \le b$$



由此，分隔元 $c$ 的**存在性**得证。

---

#### 第二部分：唯一性证明 (Dimostrazione dell'Unicità)

我们采用**反证法 (Dimostrazione per assurdo)**。

1. **假设存在两个不同的分隔元：**
假设存在两个不同的分隔元 $c_1, c_2 \in \mathbb{R}$，且不妨设：

$$c_1 < c_2$$



这意味着它们之间的开区间是非空的，即 $(c_1, c_2) \neq \emptyset$。我们在该区间内任取一个实数 $x$，使得：

$$c_1 < x < c_2$$


2. **推导逻辑矛盾：**
由于定理条件指出 $A \cup B = \mathbb{R}$，那么这个实数 $x$ 必然属于 $A$ 或属于 $B$。我们对此进行**分类讨论 (Analisi dei casi)**：
* **情况一：若 $x \in A$**
因为 $c_1$ 是分隔元，根据定义它必须大于或等于 $A$ 中的所有元素，也就是说 $\forall a \in A \implies a \le c_1$。因此必然有 $x \le c_1$。
但这与我们选择 $x$ 时满足的条件 $c_1 < x$ **相矛盾**。
* **情况二：若 $x \in B$**
因为 $c_2$ 是分隔元，根据定义它必须小于或等于 $B$ 中的所有元素，也就是说 $\forall b \in B \implies c_2 \le b$。因此必然有 $c_2 \le x$。
但这与我们选择 $x$ 时满足的条件 $x < c_2$ **相矛盾**。


3. **结论：**
由于 $x$ 无论属于 $A$ 还是属于 $B$ 都会导致逻辑矛盾，而 $A \cup B = \mathbb{R}$ 又是绝对成立的，因此最初的假设（存在两个不同的分隔元）错误。
由此，分隔元 $c$ 的**唯一性**得证。

$$\blacksquare$$


Ciao! 作为一个曾经的文学系学生，你能把戴德金分割（Dedekind Cut）用严格数学语言向父母解释清楚，这绝对是一个了不起的里程碑！这说明你的大脑已经成功跨越了从“描述性思维”到“公理化逻辑”的鸿沟。

既然你今天想直接“真枪实弹”地感受 Analisi 1 的核心，要求跳过我们平时的教学框架，那我们就直接上硬菜。这是罗马大学黑板上最标准、最无懈可击的**极限 (Limite)** 形式化定义、证明模板以及经典习题。

### 1. 严格的数学语言定义 (Definizione Rigorosa)

**函数极限 (Limite di una funzione in un punto)**

设函数 $f: A \to \mathbb{R}$，且 $x_0$ 是定义域 $A$ 的一个**聚点 (Punto di accumulazione)**。我们称 $L \in \mathbb{R}$ 是函数 $f(x)$ 当 $x$ 趋向于 $x_0$ 时的**极限 (Limite)**，记作：

$$\lim_{x \to x_0} f(x) = L$$

当且仅当满足以下 $\varepsilon-\delta$ 逻辑命题：

$$\forall \varepsilon > 0, \exists \delta > 0 \text{ tale che } \forall x \in A, 0 < |x - x_0| < \delta \implies |f(x) - L| < \varepsilon$$

### 2. $\varepsilon-\delta$ 极限证明的“万能模板”

在草稿纸上（**Brutta copia**），你需要通过逆推 $|f(x) - L| < \varepsilon$ 来寻找 $\delta$ 与 $\varepsilon$ 的函数关系 $\delta(\varepsilon)$。但在答题纸上（**Bella copia**），你必须按照正向的逻辑流来书写。

以下是考试标准的书写模板：

**Dimostrazione:**

1.  **(引入任意的误差界限)** Sia $\varepsilon > 0$ fissato arbitrariamente. _(任取一个 $\varepsilon > 0$。)_
    
2.  **(宣告你要寻找的目标)** Dobbiamo trovare un $\delta > 0$ tale che per ogni $x$ che soddisfa $0 < |x - x_0| < \delta$, risulti $|f(x) - L| < \varepsilon$. _(我们需要找到一个 $\delta > 0$，使得...)_
    
3.  **(给出你找到的 $\delta$)** Scegliamo $\delta = \dots$ _(在这里填入你在草稿纸上算出的 $\delta$ 关于 $\varepsilon$ 的表达式，例如 $\delta = \frac{\varepsilon}{3}$ 或 $\delta = \min(1, \frac{\varepsilon}{M})$。)_
    
4.  **(正向推导验证)** Verifichiamo che questa scelta funziona. Assumiamo $0 < |x - x_0| < \delta$, allora:
    
    $|f(x) - L| = \dots$ _(进行代数变形，利用三角不等式、放缩法等)_
    
    $\dots < \dots$
    
    $\dots < \varepsilon$.
    
5.  **(收尾)** Poiché abbiamo trovato tale $\delta$ per ogni $\varepsilon > 0$, la definizione di limite è soddisfatta. Come volevasi dimostrare (C.V.D.). _(根据定义，证明完毕。)_
    

### 3. 五个最具有代表性的极限证明练习题

这五个题目涵盖了 Analisi 1 中 $\varepsilon-\delta$ 证明最核心的五种代数处理技巧。

#### 练习题 1：线性函数 (Funzione Lineare) —— 最基础的同构缩放

**题目：** 证明 $\lim_{x \to 2} (3x - 1) = 5$

**草稿纸逆推：** $|(3x - 1) - 5| = |3x - 6| = 3|x - 2| < \varepsilon \implies |x - 2| < \frac{\varepsilon}{3}$

**$\delta$ 的取值：** 选取 $\delta = \frac{\varepsilon}{3}$

#### 练习题 2：带“可去瑕点”的有理函数 (Punto di discontinuità eliminabile) —— 考察 $0 < |x - x_0|$ 的作用

**题目：** 证明 $\lim_{x \to 2} \frac{x^2 - 4}{x - 2} = 4$

**草稿纸逆推：** 因为极限定义中要求 $0 < |x - 2| < \delta$，所以 $x \neq 2$。

此时 $|\frac{x^2 - 4}{x - 2} - 4| = |(x + 2) - 4| = |x - 2| < \varepsilon$

**$\delta$ 的取值：** 选取 $\delta = \varepsilon$

#### 练习题 3：平方根函数 (Funzione Radice Quadrata) —— 共轭因式法 (Razionalizzazione)

**题目：** 证明 $\lim_{x \to 4} \sqrt{x} = 2$

**草稿纸逆推：** $|\sqrt{x} - 2| = |\frac{(\sqrt{x} - 2)(\sqrt{x} + 2)}{\sqrt{x} + 2}| = \frac{|x - 4|}{\sqrt{x} + 2}$。

因为 $x > 0$，所以 $\sqrt{x} + 2 > 2$，进而 $\frac{1}{\sqrt{x} + 2} < \frac{1}{2}$。

因此 $\frac{|x - 4|}{\sqrt{x} + 2} < \frac{|x - 4|}{2} < \varepsilon \implies |x - 4| < 2\varepsilon$

**$\delta$ 的取值：** 选取 $\delta = 2\varepsilon$

#### 练习题 4：二次函数 (Funzione Quadratica) —— 局部有界性放缩法 (Limitazione Locale)

**题目：** 证明 $\lim_{x \to 2} x^2 = 4$

**草稿纸逆推：** $|x^2 - 4| = |x - 2| \cdot |x + 2|$。这里不仅有 $|x-2|$，还多了一个变量因子 $|x+2|$。

先人为限制 $\delta \le 1$，即设 $|x - 2| < 1$，那么 $1 < x < 3$。

此时 $|x + 2| < 5$。

所以 $|x^2 - 4| = |x - 2| \cdot |x + 2| < 5|x - 2| < \varepsilon \implies |x - 2| < \frac{\varepsilon}{5}$。

为了同时满足前面的假设和推导，$\delta$ 必须取两者中的较小值。

**$\delta$ 的取值：** 选取 $\delta = \min(1, \frac{\varepsilon}{5})$

#### 练习题 5：倒数函数 (Funzione Reciproca) —— 分母下界放缩法

**题目：** 证明 $\lim_{x \to 1} \frac{1}{x} = 1$

**草稿纸逆推：** $|\frac{1}{x} - 1| = \frac{|1 - x|}{|x|} = \frac{|x - 1|}{|x|}$。我们需要放缩分母 $|x|$ 的下界（使其倒数有一个上界）。

人为限制 $\delta \le \frac{1}{2}$，即 $|x - 1| < \frac{1}{2}$，这意味着 $x \in (\frac{1}{2}, \frac{3}{2})$。

此时 $|x| > \frac{1}{2}$，因此 $\frac{1}{|x|} < 2$。

所以 $\frac{|x - 1|}{|x|} < 2|x - 1| < \varepsilon \implies |x - 1| < \frac{\varepsilon}{2}$。

**$\delta$ 的取值：** 选取 $\delta = \min(\frac{1}{2}, \frac{\varepsilon}{2})$

---

