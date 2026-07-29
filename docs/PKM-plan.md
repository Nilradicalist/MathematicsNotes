# 长期数学知识库的搭建与网页发布

## 项目目标

建立一个长期维护、完全基于自由开源软件（FOSS）的数学知识库。

目标包括：

* 使用 **Zettlr** 编写原生 Markdown 数学笔记。
* 使用 **Git** 管理全部历史版本。
* 使用 **Codeberg** 作为主仓库（Primary Remote）。
* 使用 **GitHub** 作为镜像仓库，并利用 **GitHub Pages** 发布网站。
* 使用 **Quartz 5** 将 Markdown 转换为静态数学知识网站。
* 整个方案保持可迁移、长期可维护，不依赖任何专有平台。

---

# 当前工具链

系统：

* Debian（长期主力系统）

笔记：

* Zettlr
* Markdown（原生格式）

版本管理：

* Git

远程仓库：

* origin → Codeberg（主仓库）
* github → GitHub（镜像仓库）

网站：

* Quartz 5
* GitHub Pages

设计原则：

> 数据属于自己，而不是属于某个平台。

所有核心数据均保存为：

```text
*.md
```

因此以后即使迁移到其他工具，也无需转换格式。

---

# Git 工作流程

推荐采用最简单稳定的流程：

```text
git pull
↓
修改笔记
↓
git status
↓
git add .
↓
git commit -m "..."
↓
git push origin main
↓
git push github main
```

原则：

* 绝大多数修改都在本地完成。
* GitHub 和 Codeberg 网页主要用于浏览，不直接修改文件。
* 避免在网页编辑 Markdown，以减少远程历史分叉。

---

# GitHub 推送冲突总结

曾遇到的问题：

```text
Updates were rejected because the remote contains work that you do not have locally.
```

原因：

GitHub 仓库初始化时自动创建了 README，因此 GitHub 的历史与本地不同。

解决方法：

```bash
git push github main --force-with-lease
```

完成后：

GitHub 与 Codeberg 保持一致。

以后：

```bash
git push origin main
git push github main
```

即可正常同步。

---

# Git 对空目录的处理

Git 不会跟踪空目录。

例如：

```text
assets/
content/
```

如果目录为空，则不会上传。

解决方法：

放入：

```text
.gitkeep
```

或者任何实际文件即可。

---

# 仓库整体规划

建议采用如下结构：

```text
MathematicsNotes/

content/
assets/
quartz/

README.md
```

其中：

content：

存放全部数学知识。

assets：

存放图片。

quartz：

Quartz 配置。

---

# 数学知识的组织方式

不采用：

```text
Undergraduate/
First Year/
Semester 1/
Analysis I/
...
```

原因：

这是课程组织方式。

知识不会按照课程存在。

例如：

极限

以后会出现在：

* Analysis I
* Analysis II
* Functional Analysis
* Numerical Analysis

因此：

课程不是知识分类依据。

---

推荐按照学科分类：

```text
content/

analysis/
linear-algebra/
geometry/
topology/
probability/
number-theory/
logic/
optimization/
measure-theory/
functional-analysis/
complex-analysis/
```

以后增加新学科即可。

目录几乎不会发生变化。

---

# 一主题一文件

推荐：

```text
analysis/

limit.md

sequence.md

continuity.md

compactness.md
```

不要：

```text
Limit/
    Definition/
    Theorem/
    Exercise/
```

Markdown 自身已经支持：

```markdown
# Topic

## Definition

## Theorem

## Example

## Proof

## Exercises
```

无需继续建立目录。

---

# 课程与知识分离

课程：

属于学习路径。

知识：

属于长期知识库。

课程建议：

```text
courses/

analysis-i.md
analysis-ii.md
```

其中：

```markdown
# Analysis I

Week 1

- [[real-numbers]]
- [[supremum]]

Week 2

- [[limit]]
- [[sequence]]
```

课程只是索引。

真正知识全部放在：

```text
analysis/
```

---

# Exercises 的规划

建议建立：

```text
exercises/

analysis/
linear-algebra/
geometry/
```

只保存：

真正具有代表性的题目。

例如：

* ε-δ 证明
* Heine–Borel
* Jordan Canonical Form
* Hahn–Banach

不保存：

Homework1

Homework2

Homework3

……

因为以后不会按作业寻找题目。

而是按知识寻找。

---

# 教授资料的保存

教授提供：

* Slides
* PDF
* Lecture Notes
* Past Exams
* Homework

建议：

完全独立保存。

例如：

```text
University/

2026-2027/

Semester 1/

Analysis I/

Slides/
Homework/
Past Exams/
Lecture Notes/
```

不放入 Git。

因为：

* 文件较大。
* 基本不会修改。
* 使用频率较低。

属于课程档案。

不是知识库。

---

# PDF 习题的记录方式

推荐顺序：

第一：

截图题目。

Markdown：

```markdown
## Problem

![[exercise.png]]

## My Solution

……
```

第二：

OCR。

第三：

Mathpix（可将图片转换为 LaTeX）。

第四：

Pix2Text（开源、本地运行）。

原则：

真正重要的是：

自己的证明。

不是重新打一遍题目。

---

# Reference 工具目录

建议建立：

```text
reference/

latex-cheat-sheet.md

git-cheat-sheet.md

linux-cheat-sheet.md

zettlr-cheat-sheet.md
```

用于保存：

工具使用说明。

而不是数学知识。

避免污染知识搜索结果。

---

# 命名规范

采用 FOSS 社区通用约定：

目录：

```text
analysis/
linear-algebra/
measure-theory/
```

文件：

```text
limit.md

compactness.md

continuity.md
```

原则：

* 全小写
* 使用连字符（-）
* 不使用空格
* 不使用中文
* 不使用大小写混合

例外：

```text
README.md
LICENSE
CHANGELOG.md
```

属于历史传统。

---

# Quartz 与 GitHub Pages

目前确认：

Quartz：

免费。

GitHub Pages：

免费（公开仓库静态网站）。

无需：

* VPS
* Linux Server
* Nginx
* Apache

无需长期维护服务器。

整个网站属于：

静态网站。

以后：

```bash
git push
```

GitHub 自动重新生成网站。

---

# Quartz 学习计划

采用分阶段学习。

## 第一阶段

本地搭建 Quartz。

包括：

* Node.js
* npm
* Quartz
* 本地预览
* 热更新

目标：

浏览器成功打开：

localhost。

---

## 第二阶段

理解 Quartz。

包括：

* Front Matter
* 双向链接
* 数学公式
* 图片
* Graph
* 标签

---

## 第三阶段

网站美化。

包括：

* Logo
* 首页
* CSS
* 字体
* 导航栏
* 深色模式
* 数学字体

---

## 第四阶段

GitHub Pages 自动部署。

包括：

* GitHub Actions
* 自动发布
* HTTPS

以后：

```bash
git push
```

即可自动更新网站。

---

## 第五阶段

高级功能。

包括：

* 全文搜索
* Graph View
* RSS
* Sitemap
* SEO
* Mermaid
* 评论系统（Giscus）
* PDF 导出
* LaTeX 宏

---

# 下一步

下一次继续时，从第一阶段开始。

首先检查：

```bash
node -v
npm -v
```

若未安装，则先完成 Node.js LTS 与 npm 的安装。

随后开始本地搭建 Quartz，并逐步完成网站部署与美化。

---

# 长期原则

整个项目遵循以下原则：

1. 原生 Markdown，不依赖专有格式。
2. Git 管理全部历史。
3. Codeberg 为主仓库，GitHub 为镜像与发布平台。
4. 知识按学科组织，不按课程、年级组织。
5. 一主题一文件，避免过深目录。
6. 使用双向链接构建知识网络，而非依赖目录层级。
7. 工具笔记、课程资料、知识库三者严格分离。
8. 保持整个知识库十年以上仍具有可维护性与可迁移性。
