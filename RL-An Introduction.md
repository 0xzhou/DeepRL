# RL-An Introduction



## Chapter 3 - Finite Markov Decision Processes



**finite MDPs:** finite Markov Decision Processes, is the problem involves evaluative feedback, but also an associative aspect - choosing different actions in different situations.

***dynamics*** of MDPs

four-argument function: $S\times R\times S\times A \to[0,1]$

$p(s',r|s,a) = Pr(S_t=s',R_t=r|S_{t-1}=s,A_{t-1}=a)$

Obviously:  $\sum_{s'\in S} \sum_{r\in R}p(s',r|s,a)=1$

***state-transition probabilities:***

