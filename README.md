# DeepRL

If you use Chrome, you can use **MathJax Plugin for Github** to see the mathmatical expressions

# Reinforcement Learning

## Key Concepts in RL

### Action Spaces:

Different environments allow different kinds of actions. Some environments, like Atari and Go, have **discrete action spaces**, where only a finite number of moves are available to the agent. Other environments, like where the agent controls a robot in a physical world, have **continuous action spaces**. In continuous spaces, actions are real-valued vectors. 

### Policies:

A **policy** is a rule used by an agent to decide what actions to take.(means how interact with environment)

Policy can be *deterministic*, usually denoted by $\mu$:

$$a_t=\mu(s_t)$$

or it may be stochastic ,usually denoted by $\pi$:

$$a_t\sim\pi(\cdot |s_t)$$











Two key computations are centrally important for using and training stochastic policies:

- sampling actions from the policy,
- and computing log likelihoods of particular actions, $log\pi_\theta(a|s)$.



**Stochastic Policy**:

- **Categorical policies**: a classifier over a discrete actions; you build the neural network for a categorical policy the same way you would for a classifier: the input is the observation,followed by some number of layers (convolutional or densely-connected), and then you have one final linear layer that gives you logits for each action, followed by a convert the logits into possibilities.

  **softmax:** Softmax is implemented through a neural network layer just before the output layer. The Softmax layer must have the same number of nodes as the output layer.

  <center>
  <img src="https://github.com/Mingy2018/Markdown-photoes/blob/master/22.PNG" width = "300" height = "250" >
  </center>

- diagonal Gaussian policies: are used in continuous action spaces.



## Advantage Functions:

Sometimes in RL, we don’t need to describe how good an action is in an absolute sense, but only how much better it is than others on average. That is to say, we want to know the relative **advantage** of that action. We make this concept precise with the **advantage function.**

The advantage function corresponding to a policy $\pi$ describes how much better it is to make a specific action $a$ in state $s$, over randomly selecting an action according to $\pi(\cdot|s)$, assuming you act according to $\pi$ forever after:

$$A^\pi(s,a)=Q^\pi(s,a)-V^\pi(s)$$



# Kinds of RL Algorithms

## Model-Free and Model-Based RL:

One of the most important branching point in an RL algorithms is the question of **whether the agent has access to (or learns) a model of the environment.** By a model of the environment, we mean a function which predicts state transitions and rewards.

**Model-Based RL:** The main upside to having a model is that **it allows the agent to plan** by thinking ahead, seeing what would happen for a range of possible choices, and explicitly deciding between its options.

The main downside is that **a ground-truth model of the environment is usually not available to the agent.**













































## Algorithms

### The On-Policy Algorithms

**VPG:** *Vanilla Policy Gradient* is the most basic, entry-level algorithm in the deep RL space because it completely predates the advent of deep RL altogether: **VPG$\rightarrow$TRPO$\rightarrow$PPO**.

**On-Policy:** It means that these algorithms don't use **old data**,which makes them weaker on sample efficiency.( $\rightarrow$ deficit on sample efficiency ), they directly optimize the objective you care about—policy performance. These Algorithms are always trading off sample efficiency in favor of stability.

### The Off-Policy Algorithms

**DDPG and Q-Learning:**

The theory of deterministic policy gradients $\rightarrow$ **DDPG**$\rightarrow$ TD3 $\rightarrow$ SAC;

Q-Learning: Q-function&Policy

**Off-Policy:**  reuse old data very effectively by exploiting Bellman's equation

But problematically, there are no guarantees that doing a good job of satisfying Bellman’s equations leads to having great policy performance$\rightarrow$makes algorithms in this class potentially brittle and unstable.





