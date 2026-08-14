# Crouzeix Conjecture Prompt

## 克鲁泽猜想证明搜索指令 · 中英双语整理

来源：[jinshanmu/CrouzeixConjecture/crouzeix_conjecture_prompt.txt](https://github.com/jinshanmu/CrouzeixConjecture/blob/main/crouzeix_conjecture_prompt.txt)

本文件保留原 prompt 的数学命题和任务指令，并在每一段英文后附中文翻译。中文翻译用于阅读，不替代原始英文文本。

## Mathematical statement · 数学命题

### English

Let \(A\) be an \(n \times n\) complex matrix, and define its numerical range by

\[
W(A)=\left\{x^{*}Ax:x\in\mathbb{C}^{n}\text{ and }\|x\|_2=1\right\},
\]

where \(x^{*}\) denotes the conjugate transpose of \(x\). Then, for every complex polynomial \(p\),

\[
\|p(A)\|_2\leq 2\max_{z\in W(A)}|p(z)|,
\]

where \(\|p(A)\|_2\) is the operator norm induced by the Euclidean norm. Equivalently, the closure of the numerical range \(W(A)\) is a \(2\)-spectral set for \(A\).

### 中文

设 (A) 是一个 (n\times n) 的复矩阵，并定义它的数值域为

\[
W(A)=\left\{x^{*}Ax:x\in\mathbb{C}^{n}\text{ 且 }\|x\|_2=1\right\},
\]

其中 (x^{*}) 表示 (x) 的共轭转置。对于任意复系数多项式 (p)，要求证明

\[
\|p(A)\|_2\leq 2\max_{z\in W(A)}|p(z)|,
\]

其中 (|p(A)|_2) 是由欧几里得范数诱导的算子范数。等价地说，数值域 (W(A)) 的闭包是矩阵 (A) 的一个 (2)-谱集。

## Current task statement · 当前任务

### 01 · The task · 任务

**English**

Give a rigorous standalone proof of the above math problem using your own knowledge, computation, and reasoning without searching the public web, connected sources, previous conversations, project contexts, or existing local files. Return the proof as one compilable full-English LaTeX `.tex` file in `/Users/shanmujin/Documents/CrouzeixConjecture/LaTeX`.

**中文**

使用你自己的知识、计算与推理，对上述数学问题给出一个严谨、独立完整的证明；不得检索公共网络、已连接的数据源、以往对话、项目上下文或现有本地文件。将证明作为一个可编译的、全英文 LaTeX `.tex` 文件返回，路径为 `/Users/shanmujin/Documents/CrouzeixConjecture/LaTeX`。

### 02 · Assume a proof exists · 假定存在证明

**English**

Assume for purposes of this task that a complete affirmative proof exists. Work iteratively until a correct proof has been reached.

**中文**

就本任务而言，假定存在一个完整的、肯定性的证明。请迭代地工作，直到得出一个正确的证明为止。

### 03 · What does not count · 哪些不算完成

**English**

Partial progress does not count unless it implies exactly the resolution of the entire problem above. In particular, reductions to other unproved conjectures, computational verification through any fixed parameters, and candidate counterexamples without a proved certificate are insufficient.

**中文**

部分进展不算数，除非它恰好蕴含对上述整个问题的解决。特别地，归约到其他未经证明的猜想、通过任意固定参数进行的计算验证，以及没有经证明凭证的候选反例，均不足够。

## Orchestration heuristics · 编排启发式

### 04 · Use multiagents aggressively and dynamically · 积极、动态地使用多智能体

**English**

Use multiagents aggressively and dynamically. Do not use a fixed assignment such as “N agents for strategy X.” Instead, manage the search using the following heuristics:

**中文**

积极且动态地使用多智能体。不要采用诸如“(N) 个智能体负责策略 (X)”这样的固定分配。相反，请依据以下启发式原则来管理这次搜索：

### 05 · Start with diverse approaches · 从多样化的方法开始

**English**

Begin with a genuinely diverse portfolio of approaches. Agents should explore substantially different formulations, invariants, reductions, algebraic viewpoints, structural inductions, decompositions, flow formulations, transition systems, embeddings, extremal arguments, and computational sanity checks.

**中文**

以一个真正多样化的方法组合开始。各智能体应探索实质上不同的表述形式、不变量、归约、代数视角、结构归纳、分解、流的表述、转移系统、嵌入、极值论证，以及计算上的合理性检验。

### 06 · Preserve independence · 保持独立性

**English**

Do not tell most agents the currently favored approach. Preserve independence during early rounds so that agents do not all converge to the same attractive but incomplete reduction.

**中文**

不要把当前看好的方法告诉大多数智能体。在早期各轮中保持独立性，以免所有智能体都收敛到同一个诱人却不完整的归约上。

### 07 · Maintain an approach registry · 维护方法族登记表

**English**

Maintain an explicit registry of approach families. Group agents by the mathematical idea they are using, not by superficial wording. If many agents converge to one family, redirect some of them toward underexplored formulations.

**中文**

维护一份明确的方法族登记表。按智能体所使用的数学思想来分组，而非按表面措辞。若许多智能体收敛到某一个族，就把其中一些重新引导到尚未充分探索的表述上。

### 08 · Do not reward elegant reductions alone · 不要只奖励优雅归约

**English**

Do not allow one approach to dominate merely because it gives elegant reductions. A route that ends at a lemma equivalent in strength to the original problem is not close to completion unless it supplies a genuinely new proof of that lemma.

**中文**

不要仅仅因为某个方法给出了优雅的归约，就任由它占据主导。一条最终止步于“与原问题强度等价的引理”的路线并不接近完成——除非它为该引理提供了一个真正全新的证明。

### 09 · Mark theorem-strength gaps as blocked · 标记定理强度的缺口

**English**

When an approach stalls at a theorem-strength missing lemma, mark that route as blocked. Only continue assigning agents to it if someone proposes a materially new mechanism, invariant, or construction.

**中文**

当某个方法停滞于一个“定理强度”的缺失引理时，将该路线标记为受阻。只有当有人提出实质上全新的机制、不变量或构造时，才继续为其分配智能体。

### 10 · Keep incompatible routes alive · 保留互不相容的路线

**English**

Keep several incompatible proof routes alive through multiple rounds. Cross-pollinate ideas only after independent agents have developed them far enough to expose their real strengths and gaps.

**中文**

让若干互不相容的证明路线在多轮中持续存活。只有在各独立智能体已将想法发展到足以暴露其真正的优势与缺陷之后，才进行思想的交叉融合。

### 11 · Use adversarial agents · 使用对抗性智能体

**English**

Use adversarial agents throughout: every candidate proof must be checked for gaps, conditionals, handwavings, and circular uses of an equivalent statement.

**中文**

全程使用对抗性智能体：每一个候选证明都必须接受检查，以发现其中的漏洞、隐含条件、含糊其辞之处，以及对等价命题的循环使用。

### 12 · Demand concrete outputs · 要求具体产出

**English**

Require agents to return concrete lemmas, constructions, equations, or counterexamples to proposed sublemmas. Reject status reports, vague optimism, and claims that an unproved statement is “routine.”

**中文**

要求各智能体返回具体的引理、构造、方程，或针对所提子引理的反例。拒绝进度汇报、含糊的乐观情绪，以及声称某个未经证明的命题“是例行常规”的说法。

## Persistence and return conditions · 坚持与返回条件

### 13 · Synthesize and relaunch · 综合、质疑并启动新轮次

**English**

The root agent should repeatedly synthesize, challenge, redirect, and launch new rounds. Do not stop after the first wave fails. Produce a complete proof if one survives audit; otherwise report only the strongest rigorously proved derivation and its exact remaining gap.

**中文**

根智能体应反复地综合、质疑、重新引导并启动新一轮。不要在第一波失败后就停止。如果有一个证明能够通过审核，则给出完整证明；否则只报告经过严格证明的最强推导及其确切的剩余缺口。

### 14 · Continue after failure · 不要因为失败就返回

**English**

Do not return merely because current approaches fail or agents report theorem-strength gaps. Continue launching new rounds, reopening blocked approaches only when there is a genuinely new mechanism, and searching for fresh formulations.

**中文**

不要仅仅因为当前方法失败、或智能体报告了定理强度的缺口就返回。请继续启动新一轮，仅在出现真正全新机制时才重新开启受阻的方法，并不断寻找新的表述形式。

### 15 · Return only after a complete audited proof · 只有通过审查的完整证明才可返回

**English**

Return only when a complete affirmative proof has been found and survives adversarial audit. Do not return a reduction, partial result, isolated missing lemma, “best effort” summary, or explanation of why the problem is difficult.

**中文**

只有当已经找到一个完整的、肯定性的证明，并且它通过了对抗性审核时，才可返回。不要返回归约、部分结果、孤立的缺失引理、“尽力而为”的总结，或关于该问题为何困难的解释。

### 16 · Do not search the public web · 不要检索公共网络

**English**

Do not search the public web to determine whether the problem is open, and do not answer that it is open.

**中文**

不要为了判断该问题是否为开放问题而检索公共网络，也不要回答说它是开放的。

## Reading note · 阅读说明

This file is a bilingual reading edition of the prompt. It is not a proof of the stated mathematical claim. The original English prompt is preserved in [`../original/crouzeix_conjecture_prompt.txt`](../original/crouzeix_conjecture_prompt.txt), and the two-column PDF is available at [`../Crouzeix-Conjecture-Prompt-Bilingual.pdf`](../Crouzeix-Conjecture-Prompt-Bilingual.pdf).

这是一份 prompt 的双语阅读版，不是上述数学命题的证明。原始英文 prompt 保存在 [`../original/crouzeix_conjecture_prompt.txt`](../original/crouzeix_conjecture_prompt.txt)，中英双栏 PDF 位于 [`../Crouzeix-Conjecture-Prompt-Bilingual.pdf`](../Crouzeix-Conjecture-Prompt-Bilingual.pdf)。
