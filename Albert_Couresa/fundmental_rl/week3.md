`policy` : how an agent choose an action; 将状态映射为动作；

策略对于动作的选择只与状态 *s* 有关，不与时间，不与之前的任何状态有关（马尔可夫性质）；

`Value Function` 和 `Value-Action Function`:
`Value Function` 值函数：表达的是初始状态为`s`，在策略 $\pi$ 下的回报；

`Value-Action Function` 表示的是：初始状态为s，选择动作为a后在策略$\pi$ 下的回报。



听到了一个很清晰的东西：RL is *searching and memoring* ——(nothing is new under the sun)  `search with memory` 这个观点非常类似于动态规划。动态规划是是维护了一张表，有一个目标，有限定条件，然后找到最优解。而RL是一个带有参数的多项式/神经网络作为`memory` 来进行优化和记忆。

## 贝尔曼方程

贝尔曼方程是强化学习基础得一个重要概念，其主要的作用是将`state-value function` 和`state-action value function`写成迭代递归的形式。
值函数的作用是用来评估一个状态/在某一个状态选择某一个动作的“好坏程度”
`policy`:
> Formally, a policy is a mapping from states to probabilities of selecting each possible action.

蒙特卡洛方法：
> We call estimation methods of this kind Monte Carlo methods because they involve averaging over many random samples of actual returns

**贝尔曼方程的作用**
将状态-值函数、状态-动作值函数转化为线性方程组的形式进行求解。