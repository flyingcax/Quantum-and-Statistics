# 量子统计 {ignore=true}
## 目录 {ignore=true}
[toc]

---

## 量子力学
### $\mathcal{H}$ 空间与 Dirac 符号
**$\mathcal{H}$ 空间：** 是一种复线性空间，用于表示纯态。
- 若 $|\psi _1\rangle$ 与 $|\psi _2\rangle$ 是 $\mathcal{H}$ 空间中的矢量，则 $c_1|\psi _1\rangle+c_2|\psi _2\rangle$ 也是 $\mathcal{H}$ 空间中的矢量
- $$\langle \psi | = (|\psi\rangle)^{\dagger}$$
- 内积定义： 
  - $$(\,|\psi _1\rangle\, ,\,|\psi _2\rangle\,) = \langle \psi _1|\psi _2\rangle$$
- $$\langle \psi _2|\psi _1\rangle = \langle \psi _1|\psi _2\rangle ^*$$
> **注：** 内积定义中的 $\langle \psi _1|\psi _2\rangle$ 是一个符号，不是左矢与右矢相乘的意思，不过确实可以简单理解为 $|\psi _1\rangle$ 的厄米共轭与 $|\psi _2\rangle$ 相乘

**量子中的态矢量：** 满足归一化，且认为仅相差一个相因子的两个态是一个态。
- $||\psi|| = \sqrt{\langle \psi|\psi\rangle} = 1$
- 若 $|\psi _2\rangle = e^{i\phi} |\psi _1\rangle$ ，则认为 $|\psi _1\rangle$ 与 $|\psi _2\rangle$ 表示同一个态

**基矢 $\{|\psi\rangle\}$ ：** 满足正交性与完备性。
- $\forall\, |\psi _i\rangle,|\psi _j\rangle \in \{|\psi\rangle\}$ ，满足 $\langle\psi _i|\psi _j\rangle = \delta_{ij}$
- $\sum_i|\psi _i\rangle\langle\psi _i| = I$ 

**算符：** 态矢量外积空间中的元素，可以将一个态变化为另一个态。
- $\hat{O} |\psi _1\rangle = |\psi _2\rangle$
- 厄米共轭： $\forall\, |\psi _1\rangle,|\psi _2\rangle$ ，若 $\hat{O}^{\dagger}$ 满足 $\langle \psi _2|\hat{O}^{\dagger}|\psi _1\rangle = \langle \psi _1|\hat{O}|\psi _2\rangle^*$ ，则 $\hat{O}^{\dagger}$ 是 $\hat{O}$ 的厄米共轭
> **注：** 线性算符的厄米共轭是如上定义的，如果是反线性算符（如时间反演算符），则应该为 $\langle \psi _2|\hat{T}^{\dagger}|\psi _1\rangle = \langle \psi _1|\hat{T}|\psi _2\rangle$
- 厄米算符： $\hat{O}^{\dagger} = \hat{O}$
  $$(\hat{O}_1 \hat{O}_2)^{\dagger} = \hat{O}_2^{\dagger}\hat{O}_1^{\dagger}$$
  在量子力学中，力学量（可观测量）用厄米算符表示，具体的值即对应的本征值。
- 力学量的期望：当系统处于态 $|\psi\rangle$ 时，力学量 $\hat{O}$ 的期望 $\langle O \rangle$ 为
  $$\langle O \rangle = \langle \psi |O|\psi\rangle$$

**本征方程、本征值、本征矢：** 连接理论与现实的桥梁。
- 本征方程： $\hat{A}|e\rangle = a|e\rangle$
- 本征值： $a\in \mathbb{C}$ 
  对于厄米算符，其本征值均为实数 $a\in \mathbb{R}$
- 本征矢： $|e\rangle$

**密度算符：** 包含了系统所有信息的算符，等效替代态矢量
- 由态矢量的外积构成密度算符
  $$\hat{\rho}(t) = |\psi(t)\rangle\langle\psi(t)|$$
  满足厄米性与归一性
  $$\hat{\rho}^{\dagger} = \hat{\rho}\quad,\quad \mathrm{tr}(\hat{\rho}) =1$$
  具有一种运算不变性
  $$\hat{\rho}^2 = \hat{\rho}$$
- 力学量的期望
  $$\langle O \rangle = \mathrm{tr}(\hat{O}\hat{\rho})$$

**$A$ 表象：** 用 $A$ 的全部本征矢（正交归一后）作为基矢，可以表示全部的态矢量与算符。
- $\hat{A}|e_k\rangle = a_k|e_k\rangle$
- 态矢量： $\forall \, |\psi\rangle \in \mathcal{H} \, ,\, \exists\, \{c_k\} \in \mathbb{C} \, , \, s.t.\,|\psi\rangle = \sum_k c_k|e_k\rangle$ 。其中 $c_k = \langle e_k | \psi \rangle$
- 算符： $\forall \, \hat{O} \, ,\, \exists\, \{o_{ij}\} \in \mathbb{C} \, , \, s.t.\,|\psi\rangle = \sum_{ij} o_{ij}|e_i\rangle\langle e_j|$ 。其中 $o_{ij} = \langle e_i | \hat{O} |e_j \rangle$
> **注：** 同一个 $\mathcal{H}$ 空间可以有多种不同的表象，表象仅仅是表示这个空间的书面形式。本质就是为线性空间选择一组基矢

**坐标表象、动量表象：** 无穷维 $\mathcal{H}$ 空间
- 坐标 $\hat{x}|x\rangle = x |x\rangle$ ，动量 $\hat{p}|p\rangle = p |p\rangle$ 
- 正交归一： 
  - $$\langle x|x'\rangle = \delta (x-x')$$
- 完备性： 
  - $$\int |x\rangle\langle x| \mathrm{d} x = \hat{I}$$
- 波函数： 
  - $$\psi(x) = \langle x | \psi \rangle$$    
  - 此时态矢量表示为 $| \psi \rangle = \int \psi(x) |x\rangle \mathrm{d} x$
- 基本对易关系： 
  - $$[x,p] = i\hbar = i$$
- 坐标与动量内积： 
  - $$\langle x|p\rangle = \frac{1}{\sqrt{2\pi}}e^{ipx}$$
- 等效算符： 
  - $\langle x|\hat{p}|\psi\rangle = - i\frac{\partial}{\partial x} \psi(x)$ ，即 $\hat{p}\Leftrightarrow - i\nabla$ 
  - 此时 $\langle \psi_1| \hat{p} |\psi_2 \rangle = \int \psi_1^*(x) (-i\partial_x) \psi_2(x)$
> **注：** 等效算符是作用在复空间的函数上的，不是定义在 $\mathcal{H}$ 空间中的算符
- 傅里叶变换：
$$
\begin{align*}
    \psi_p &= \frac{1}{\sqrt{2\pi}}\int \mathrm{d} x\, e^{-ipx} \psi_x\\
    \psi_x &= \frac{1}{\sqrt{2\pi}}\int \mathrm{d} p\, e^{ipx} \psi_p
\end{align*}
$$

<a id="angular-momentum"></a>
**角动量：** $\mathcal{H}$ 空间中的转动生成元 
- 用 $\hat{\bm{J}}= \sum \hat{J}_i \bm{e}_i$ 表示，可知 $\hat{J}^2 = \sum \hat{J}_i\hat{J}_i$ 。
- 对易关系：
  $$
  \begin{align*}
    &[\hat{J}_i,\hat{J}_j] = i \hbar \epsilon_{ijk} \hat{J}_k \\
    &[\hat{J}_i,\hat{J}^2] = 0
  \end{align*}
  $$
- 本征方程：
  $$
  \begin{align*}
    &\hat{J}^2 |j,m\rangle = j(j+1)\hbar ^2|j,m\rangle\\
    & \hat{J}_z |j,m\rangle = m\hbar |j,m\rangle\\
    & j= 0,\frac{1}{2},1,\cdots  \\
    & m=-j,-j+1\cdots,j
  \end{align*}
  $$
- $\hat{J}_{\pm }$ 是 $\hat{J}_3$ 的升降算符，是计算角动量本征值的手段。

<p align="right"><a href="#目录">返回目录</a></p>



### 含时演化
**绘景：** 描述量子世界的方式，不影响力学量的值的计算
- 薛定谔绘景（T）：算符不变，态随时间演化
  $$|\psi_T(t)\rangle = \hat{\mathcal{U}}_T(t,t_0)\,|\psi(t_0)\rangle$$
- 海森堡绘景（H）：算符随时间演化，态不变
  $$\hat{A}_H(t) = \hat{\mathcal{U}}_T^{\dagger}\,\hat{A}\,\hat{\mathcal{U}}_T$$
- 相互作用绘景（I）：算符随原体系演化，态随微扰演化
  $$
    \begin{align*}
        \hat{A}_I(t) &= \hat{\mathcal{U}}^{\dagger}(t,t_0)\hat{A}\,\hat{\mathcal{U}}(t,t_0) \\
        |\psi_I(t)\rangle &= \hat{\mathcal{U}}_I(t,t_0)\,|\psi(t_0)\rangle
    \end{align*}
    $$
> **注：**
> - 当 $H$ 不显含时间 $t$ ，则 $\hat{\mathcal{U}} = \exp(-iHt)$
> - 在相互作用绘景中，体系哈密顿量分解为无扰动项与扰动项 $\hat{H}_T = \hat{H} + \hat{V}$ ，时间演化算符被分解为 $\hat{\mathcal{U}}_T(t,t_0) = {\mathcal{U}}(t,t_0)\,{\mathcal{U}}_I(t,t_0)$

**时间演化方程：**
- 薛定谔方程：
$$
i\hbar \frac{\partial}{\partial t} |\psi(t)\rangle = \hat{H} |\psi(t)\rangle 
$$
通常，人们会在坐标表象下，计算波函数 $\psi(\bm{r} , t)$ 随时间的演化。将 $\hat{H}$ 的等效算符记为 $\mathcal{H} $ ，则有
$$
i\hbar \frac{\partial}{\partial t} \psi(\bm{r} , t) = \mathcal{H} \,\psi(\bm{r} , t)
$$
当体系处于定态时，哈密顿量 $\hat{H}$ 的本征值记为 $E$ ，对应的**定态薛定谔方程**：
$$
\mathcal{H} \,\psi(\bm{r} , t) = E \, \psi(\bm{r} , t)
$$
利用密度算符，薛定谔方程还有如下的形式
$$
\frac{\mathrm{d}}{\mathrm{d} t}\hat{\rho} = -\frac{i}{\hbar} [\hat{H},\hat{\rho}]
$$
为方便表示，取 $\hbar = 1$ ，则有
$$
\dot{\hat{\rho}} = -i[\hat{H},\hat{\rho}] 
$$
> **注：** 
> - 定态即微观状态的分布确定，若处于某个态，则力学量的测量值不会发生变化。
> - 真实体系是处于多个定态叠加形成的叠加态中。
> - 定态与不含时是两个概念。定态是对于体系而言的，不含时是对于力学量而言的。
- 海森堡方程：对于力学量算符 $\hat{O}$ ，有
$$
\frac{\mathrm{d}}{\mathrm{d} t}\hat{O} = -\frac{i}{\hbar} [\hat{O},\hat{H}]
$$
为方便表示，取 $\hbar = 1$ ，则有
$$
\dot{\hat{O}} = -i[\hat{O},\hat{H}] 
$$
- 相互作用绘景中的演化方程：
$$
\begin{align*}
  i \frac{\partial}{\partial t} |\psi_I(t)\rangle &= \hat{V}_I(t) |\psi_I(t)\rangle\\
  \frac{\mathrm{d}}{\mathrm{d} t}{\hat{O}} &= -i[\hat{O},\hat{H}]
\end{align*}
$$

<p align="right"><a href="#目录">返回目录</a></p>

### 粒子与相互作用
**自由粒子**
- 自由粒子的哈密顿量：
  $$\hat{H} = \frac{\hat{p}^2}{2m}$$

**谐振子**
- 谐振子体系的哈密顿量： 
  $$H = \frac{1}{2m}\hat{p}^2 + \frac{1}{2}m \omega^2 \hat{x}^2$$
- 为了简化方程，在保证 $\hat{x}\hat{p}$ 相乘不变的条件下，将 $\hat{x}$ 与 $\hat{p}$ 无量纲化。
  $$m\omega\hat{x}^2\Rightarrow \hat{x}^2\, , \,\hat{p}^2\Rightarrow m\omega \hat{p}^2$$
- 化简后哈密顿量： 
  $$H = \omega(\hat{p}^2 +\hat{x}^2)/2$$
- 产生-湮灭算符： 
  $$\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2}\,,\,\hat{a}^{\dagger}=(\hat{x}-i\hat{p})/\sqrt{2}$$
- 哈密顿量： 
  $$H = \omega (\hat{a}^\dagger\hat{a} + \frac{1}{2})=\omega (\hat{N}+\frac{1}{2})$$
- 对易关系： 
  $$[\hat{a},\hat{a}^\dagger]=\hat{I}$$
- 粒子数算符：产生-堙灭算符组合得到的厄米算符 
  $$\hat{N} = \hat{a}^\dagger\hat{a}\,,\,\hat{N}|n\rangle = n|n\rangle$$  
- 能级： 
  $$H|n\rangle = \omega (n+\frac{1}{2})|n\rangle = E_n|n\rangle$$
- 递归方程： 
  $$\hat{a}|n\rangle = \sqrt{n}|n-1\rangle \,,\,\hat{a}^{\dagger}|n\rangle = \sqrt{n+1}|n+1\rangle$$

**电子自旋 $\bm{S}$**
- 本征方程：
  $$
  \begin{align*}
    &\hat{S}^2 |s,m_s\rangle = s(s+1)\hbar ^2|s,m_s\rangle\\
    & \hat{S}_i |s,m_s\rangle = m_s\hbar |s,m_s\rangle\\
    & s= \frac{1}{2}  \\
    & m= -\frac{1}{2},\frac{1}{2}
  \end{align*}
  $$ 
- 泡利算符：满足[角动量算符对易关系](#angular-momentum)且本征值为 $\pm 1$ 的算符
  $$
  [\hat{\sigma}_i,\hat{\sigma}_j] = 2i\epsilon_{ijk}\hat{\sigma}_k \qquad \{\hat{\sigma}_i,\hat{\sigma}_j\} = 2\delta_{ij}
  $$
  用矩阵描述自旋：令 $\hat{\bm{S}} = \hbar \hat{\bm{\sigma}}/2$
- 泡利矩阵：用矩阵形象地表示出泡利算符
  $$
  \sigma_1 = \begin{pmatrix}
    0 &1\\
    1 &0 
  \end{pmatrix}\quad \sigma_2 = \begin{pmatrix}
    0 &-i\\
    i &0 
  \end{pmatrix}\quad \sigma_3 = \begin{pmatrix}
    1 &0\\
    0 &-1 
  \end{pmatrix}
  $$
  由上可知， $\sigma_i^2 = I$ ，可得 $\sigma_i$ 的本征值为 $\pm 1$
  $$
  \begin{align*}
    &\sigma _1 \binom{1}{1} =  \binom{1}{1} \qquad \sigma _1 \binom{1}{-1} = - \binom{1}{-1} \\
    &\sigma _2 \binom{1}{i} =  \binom{1}{i} \qquad \sigma _2 \binom{1}{-i} = - \binom{1}{-i} \\
    &\sigma _3 \binom{1}{0} =  \binom{1}{0} \qquad \sigma _3 \binom{0}{1} = - \binom{0}{1} \\
  \end{align*}
  $$
- 磁场中的自旋：
  定义波尔磁矩：
  $$\mu_B = \frac{e\hbar}{2m_e}$$
  电子自旋对应的磁矩为：
  $$\bm{\mu} = -2\mu _B\frac{\bm{S}}{\hbar}$$
  磁势：
  $$U = -\bm{\mu}\cdot\bm{B} $$

**全同粒子**
- 定义：当交换体系中任意两个粒子，任何观测量的值保持不变，则该体系由全同粒子组成
- 全同粒子分为 Boson 和 Fermion
  - Boson：波函数交换对称 
  $$\psi(\cdots q_n \cdots q_m \cdots) = \psi(\cdots q_m \cdots q_n \cdots)$$
  - Fermion：波函数交换反对称 
  $$\psi(\cdots q_n \cdots q_m \cdots) = - \psi(\cdots q_m \cdots q_n \cdots)$$
- 二粒子系统：
  - Boson：
    两粒子处于相同的能态时
    $$\psi = \psi_k(q_1)\otimes \psi_k(q_2)$$
    两粒子处于两个不同的能态 $\psi_1$ 和 $\psi_2$ 时
    $$\psi = \frac{1}{\sqrt{2}}[\psi_1(q_1)\otimes\psi_2(q_2)+\psi_2(q_1)\otimes\psi_1(q_2)]$$
  - Fermion：
    两粒子处于相同的能态时
    $$\psi = 0$$
    两粒子处于两个不同的能态 $\psi_1$ 和 $\psi_2$ 时
    $$\psi = \frac{1}{\sqrt{2}}[\psi_1(q_1)\otimes\psi_2(q_2)-\psi_2(q_1)\otimes\psi_1(q_2)]$$  
- 多体系统：假设能态 $\psi_i$ 上有 $n_i$ 个粒子。
  对于 Boson，$n_i = 0,1,2\cdots$
  对于 Fermion，$n_i$ 只能取 $0,1$
  （若 $n_i$ 取 $2$ 及以上的值，则存在处于完全相同的态的两个粒子，此时必定不是费米子）
  多体系统的态分布，见统计力学部分[无相互作用粒子](#无相互作用粒子)

<p align="right"><a href="#目录">返回目录</a></p>

### $\mathcal{L}$ 空间
**混态**
- 纯态：用单一的态 $|\psi\rangle$ 描述的状态，即 $\mathcal{H}$ 空间中描述的态
  混态：以 $p_i$ 的概率处于态 $|\psi_i\rangle$ 的状态，即多个纯态的叠加态
- 密度算符：
  $$\hat{\rho} = \sum p_i|\psi_i\rangle\langle\psi_i|$$
  与纯态中的密度算符相同，具有厄米性与归一性
  $$\hat{\rho}^{\dagger} = \hat{\rho}\quad,\quad \mathrm{tr}\hat{\rho} =1$$
  且满足以下不等式
  $$\mathrm{tr}\hat{\rho}^2 \leqslant \mathrm{tr}\hat{\rho}$$
  在选择某一表象 $\{|n\rangle\}$（正交完备归一）之后，密度算符可以展开为
  $$\hat{\rho} = \sum_{mn} \rho_{mn} |m\rangle\langle n|\qquad\rho_{mn} = \langle m| \hat{\rho} |n\rangle$$
  力学量算符可以展开为
  $$\hat{O} = \sum_{mn} O_{mn} |m\rangle\langle n|\qquad O_{mn} = \langle m| \hat{O} |n\rangle$$

**$\mathcal{L}$ 空间**
- 态与力学量的表示
  态用密度算符对应的右矢表示，力学量用对应的左矢表示
  $$
  \hat{\rho} \Rightarrow |\rho\rangle\rangle\qquad \hat{O} \Rightarrow \langle\langle O|
  $$
- 内积：用 $\mathrm{tr}$ 定义
  $$(\langle\langle O|,|\rho\rangle\rangle) = \langle\langle O|\rho\rangle\rangle = \mathrm{tr}(\hat{O}\hat{\rho})$$
- 外积生成表象：将 $\mathcal{H} $ 空间中的表象 $\{|n\rangle\}$（正交完备归一）的外积作为 $\mathcal{L} $ 空间中的表象
  $$|m\rangle\langle n| = |mn\rangle\rangle \qquad |n\rangle\langle m| = \langle\langle mn|$$
  这里的定义满足厄米关系（外积生成表象才满足，Wigner 表象不满足），即 $\langle\langle a| = |a\rangle\rangle^{\dagger}$
  同样的，这组基满足正交完备归一
  $$
  \langle\langle mn|m'n'\rangle\rangle = \delta_{mm'}\delta_{nn'} \\
  \quad\\
  \sum_{mn}|mn\rangle\rangle\langle\langle mn|=\mathcal{I} 
  $$
  此时，密度算符和力学量算符可以展开为
  $$
  \begin{align*}
    &|\rho\rangle\rangle = \sum _{mn} \rho_{mn}|mn\rangle\rangle &\quad  &\langle\langle O| =\sum _{mn} O_{nm}\langle\langle mn| \\
    &\rho _{mn} = \langle\langle mn|\rho\rangle\rangle&\quad &O_{nm} = \langle\langle O|mn\rangle\rangle
  \end{align*}
  $$
- 超算符 $\mathcal{O}$：将一个算符映射到另一个算符
  - $\mathcal{H}$ 空间中，定义如下四个超算符
  $$
  \begin{align*}
    &\hat{A}^>(\cdot ) = \hat{A}(\cdot ) \\
    &\hat{A}^<(\cdot ) = (\cdot )\hat{A} \\
    &\hat{A}^{\times}(\cdot ) = [\hat{A},(\cdot )] \\
    &\hat{A}^{\diamond}(\cdot ) = \{\hat{A},(\cdot )\} 
  \end{align*}
  $$ 
  - $\mathcal{L}$ 空间中，超算符左作用于密度算符，右作用于力学量算符
  $$
    \mathcal{O}|\rho_1\rangle\rangle = |\rho_2\rangle\rangle  \qquad\langle\langle A_1|\mathcal{O} = \langle\langle A_2|
  $$
  在外积生成表象下可以展开为
  $$
  \begin{align*}
    &\mathcal{O} = \sum _{mnm'n'} \mathcal{O} _{mnm'n'} |mn\rangle\rangle\langle\langle m'n'| \\
    &\mathcal{O} _{mnm'n'} = \langle\langle mn| \mathcal{O} |m'n'\rangle\rangle
  \end{align*}
  $$
  - 厄米共轭：对于某算符（无论是密度算符还是力学量算符），厄米共轭由下式决定
  $$
  \mathcal{O} ^{\dagger} \hat{A}= (\mathcal{O} \hat{A}^{\dagger})^{\dagger} \qquad \hat{A}\mathcal{O} ^{\dagger} = (\hat{A}^{\dagger}\mathcal{O} )^{\dagger}
  $$
  在外积生成表象下，有
  $$\mathcal{O} ^{\dagger} _{mnm'n'} = \mathcal{O} ^* _{nmn'm'}$$
  厄米超算符：满足 $\mathcal{O} ^{\dagger} = \mathcal{O}$ 的超算符
  


<p align="right"><a href="#目录">返回目录</a></p>

---

## 统计力学
### 系综理论
**态与系综** 
- 微观态：由所有粒子的坐标动量完全确定
  系统在态空间中的演化 $\Rightarrow $ 相空间 $(\bm{r}^N,\bm{p}^N)$ 的演化
- 系综：一定条件下，同一系统所有微观态的集合
- **等概率假设：** 能量 $E$ 与体积 $V$ 确定的孤立系统，在热力学平衡时，处于各种微观态的概率相同
- 宏观态：由体系的能量来确定
  一个宏观态 $E_{\nu}$ 由很多个微观态简并而成

**微正则系综**
- 微观态数目 $\Omega(N,V,E) = $ 能量在 $E\sim E+\delta E$ 之间的微观态数目
  当能级 ${E}$ 连续时，可以定义态密度
  $$\bar{\Omega} = \frac{E\sim E+\mathrm{d} E \,\text{微观态数目}}{\mathrm{d} E}$$















<p align="right"><a href="#目录">返回目录</a></p>

### 无相互作用粒子


<p align="right"><a href="#目录">返回目录</a></p>

---

## 量子统计
### 热平衡

### 统计力学的量子表述



<p align="right"><a href="#目录">返回目录</a></p>

### 线性响应理论





<p align="right"><a href="#目录">返回目录</a></p>

### 开放系统





<p align="right"><a href="#目录">返回目录</a></p>

---

## 数学补充
### 对易
- $[\hat{O}_1,\hat{O}_2] = \hat{O}_1\hat{O}_2 - \hat{O}_2\hat{O}_1$
- $[\hat{O}_1\hat{O}_2,\hat{O}_3] = \hat{O}_1[\hat{O}_2,\hat{O}_3] + [\hat{O}_1,\hat{O}_3]\hat{O}_2$
- $\{\hat{O}_1,\hat{O}_2\} = \hat{O}_1\hat{O}_2 + \hat{O}_2\hat{O}_1$
### 留数定理

<p align="right"><a href="#目录">返回目录</a></p>