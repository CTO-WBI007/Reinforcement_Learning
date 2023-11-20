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
                        
*P* : p(s', r | s, a) == $P_{r}{{S_{t+1} = s', R_{t+1} = r|S_{t} = s, A_{t}} = a}$  
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

## **Value Function**  

As $G_{t}$ only represents one route in the backtracking graph, we need to calculate the weighted average number:  

$V_{\pi} = E_{\pi} [G_{t}|S_{t} = s]$  

*We will use backtracking graph to calculate value function*  


# MDP 4 Bellman Expectation Equality  

## **Review: Value Function**  

As $G_{t}$ only represents one route in the backtracking graph, we need to calculate the weighted average number:  

$V_{\pi} = E_{\pi} [G_{t}|S_{t} = s]$  

*We can get several column vectors according to value function*  

$q_{\pi}(s,a) = E_{\pi} [G_{t}|S_{t} = s, A_{t} = a]$

*In the above function, q has not restriction towards s, but V has that*  

## Relationship & Difference  

$V_{\pi}$(s) ? $q_{\pi}$(s,a)  
$\pi(a1|s) * q_{\pi}(s,a1)$ + $\pi(a2|s) * q_{\pi}(s,a2)$ + $\pi(a3|s) * q_{\pi}(s,a3)$ = $V_{\pi}$(s)  

*Conclusion 1* : $V_{\pi}(s) = \sum_{{a\in A}} \pi(a|s) * q_{\pi}(s,a)$  
*Conclusion 2* : $q_{\pi}(s,a) = \sum_{{r,s'}} p(s', r|s, a) [r+\gamma V_{\pi}(s')]$  
*Conclusion 3* : $V_{\pi}(s) = \sum_{{a\in A}} \pi(a|s) * \sum_{{r,s'}} p(s', r|s, a) [r+\gamma V_{\pi}(s')]$  
*Conclusion 4* : $q_{\pi}(s,a) = \sum_{{r,s'}} p(s', r|s, a) [r+\gamma\sum_{{a'}} \pi(a'|s) * q_{\pi}(s',a')]$

*Conclusion 3,4 are what we called Bellman Expectation Equation*  

















