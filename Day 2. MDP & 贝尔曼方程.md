# MDP 1 Background of MDP:

## Several basic definitions:

(1)Random Variable  
(2)Stochastic Process  //stochatic: (过程与系统上) 随机的  
(3)Markov Chain/Process:具有Markov Property的随机过程  P（St+1 | St, St-1, ..., S1) = P(St+1 | St)是Markov Property的描述  
(4)State Space Model：（HMM, Kalman Filter, Particle Filter）Markov Chain  
(5)Markov Reward Process: Markov Chain + Reward  
(6)Markov Decision Process: Markov Chain + Reward + Action  

*S* ：state set  
*A* ：action set $\forall s \in S$, $A(s) \longrightarrow At$  
*R* : reward set $\longrightarrow Rt, R_{t+1}$


# MDP 2 Dynamic Property of MDP

## Definitions:

(1)MC : S  
(2)MRP : S, R  
(3)MDP : S, A(s), R, P; P has the dynamic property  

## Functions:  

*P* : p(s', r | s, a) == Pr{St+1 = s', Rt+1 = r | St = s, At = a}  
状态转移函数：  
p(s' | s, a) = $\sum$ p(s', r | s, a)  


# MDP 3 Value Function

*When meeting different options and facing different stochastic schemes, how will we make decision?*  

## We use $\pi$ to represent policy:  
确定性策略： a = $\pi$ (s)  
随机性策略： $\pi$ (a|s) = Pr{At = a|St = s}  

## Reward:  
$G_{t}$ = $R_{t+1}$ + $r^{2}R_{t+1}$ + ... + $r^{r-1}R_{r}$  
${r\in [0,1]}$

## **Value Function**:  

$V_{\pi} = E_{\pi} [G_{t}|S_{t} = s]$  

*We will use backtracking graph to calculate value function*  










