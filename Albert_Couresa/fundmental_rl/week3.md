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

**优化贝尔曼函数**
1. optimal value funciton & optimal policy 的含义

对于有限马尔可夫决策过程(MDP), 值函数的作用是用于评价状态的回报"Return"，存在一中策略"policy"，使每一个状态的值函数都比其他的大(>=)，这一策略就是*optimal policy* ，而获取该策略，通过的是 *greddy value function*，取每一个状态的贪婪值函数，获取当前最大的回报（由于马尔可夫性质，因此取当前最大即可）



## WEEK3 练习题

```latex
A policy is a function which maps ____ to ____.
Actions to probability distributions over values.
States to actions.
States to probability distributions over actions.
Actions to probabilities.
States to values.
```

> policy是策略，策略是将状态映射到动作的“函数”，其建立的是一种映射关系；但是这种映射关系分为两种，第一种是 *determinstic* ，也就是说是一种确定性的映射关系，将一种状态映射为一个确定的动作；但是如果动作的维度很多，有可能并不是将状态映射到动作，而是将其映射到一种"概率分布"，也就是动作的概率分布，在这种情况下，进行动作的选取。

```
Does adding a constant to all rewards change the set of optimal policies in episodic tasks?
Yes, adding a constant to all rewards changes the set of optimal policies.
No, as long as the relative differences between rewards remain the same, the set of optimal policies is the same.
```

> 上面一个问题讲的是策略的问题，而针对强化学习任务本身，其本身分为 *continuous task* 和 *episodic task*，对于 *episodic task* 来说，其时间步长是一定的；
>
> 首先要明确，策略是怎么获取的？—— *optimal policy* 的获取是从 *optimal value funciton* 中获得：

> 以下内容总结自《Introduction to RL》3.6章节：

:togo: 完成关于 *optimal policy* 和 *optimal function* 的相关总结和课后习题。