# Lesson 01: Markov Decision Processes (MDPs)

## 🧠 What is an MDP?
A **Markov Decision Process (MDP)** is a formal framework for modeling decision-making in situations where outcomes are partly random and partly under the control of a decision-maker.

An MDP is defined by a 5-tuple:

$$ (S, A, P, R, \gamma) $$

Where:
- **S**: Set of states
- **A**: Set of actions
- **P(s'|s,a)**: Transition probability function – the probability of transitioning to state $s'$ from state $s$ by taking action $a$
- **R(s,a)**: Reward function – the immediate reward received after taking action $a$ in state $s$
- **$\gamma$**: Discount factor – determines how future rewards are valued ($0 \leq \gamma \leq 1$)

---

## 🎯 Objective
The goal in an MDP is to find a **policy** $\pi$, which maps states to actions:

$$ \pi(s) = a $$

This policy should maximize the expected **cumulative discounted reward** over time.

---

## 🔢 Value Functions

### State-Value Function:
$$
V^\pi(s) = \mathbb{E}_\pi \left[ \sum_{t=0}^\infty \gamma^t R(s_t, a_t) \mid s_0 = s \right]
$$

The expected return starting from state $s$ and following policy $\pi$.

### Action-Value Function:
$$
Q^\pi(s,a) = \mathbb{E}_\pi \left[ \sum_{t=0}^\infty \gamma^t R(s_t, a_t) \mid s_0 = s, a_0 = a \right]
$$

The expected return from state $s$, taking action $a$, and then following policy $\pi$.

---

## 🧮 Bellman Equations

### Bellman Expectation Equation:
$$
V^\pi(s) = \sum_a \pi(a|s) \left[ R(s,a) + \gamma \sum_{s'} P(s'|s,a) V^\pi(s') \right]
$$

### Bellman Optimality Equation:
$$
V^*(s) = \max_a \left[ R(s,a) + \gamma \sum_{s'} P(s'|s,a) V^*(s') \right]
$$

---

## ✅ Summary
- MDPs model decision-making in stochastic environments.
- The value function evaluates how good it is to be in a state (or take an action).
- The Bellman equations provide recursive definitions that are the foundation of most solution algorithms.

Coming up in Lesson 2: **Bellman Equations in Practice & Deriving Value Functions**