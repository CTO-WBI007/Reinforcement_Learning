# Sarsa  

## Derive TD Target 

*Review Discounted Return*  
**Identity:** $U_{t} = R_{t} + \gamma * U_{t+1}$  
*Expansion:* $Q_{\pi}(s_{t},a_{t}) = E[R_{t} + \gamma * Q_{\pi}(S_{t+1},A_{t+1})]$, for all $\pi$  
And we have $E[R_{t} + \gamma * Q_{\pi}(S_{t+1},A_{t+1})] \approx y_{t}$  

**TD learning:** Encourage $Q_{\pi}(s_{t},a_{t})$ to approach $y_{t}$  

## Sarsa: Tabular Version  
1) Observe a transition ($s_{t},a_{t},r_{t},s_{t+1}$).
2) Sample $a_{t+1} ~ \pi( |s_{t+1})$, where $\pi$ is the policy function.
3) TD target: $y_{t} = r_{t} + \gamma * Q_{\pi}(s_{t+1},a_{t+1})$
4) TD error: $\delta_{t} = Q_{\pi}(s_{t},a_{t}) - y_{t}$
5) Update: $Q_{\pi}(s_{t},a_{t}) \longleftarrow Q_{\pi}(s_{t},a_{t}) - a * \delta_{t}$

As we use ($s_{t},a_{t},r_{t},s_{t+1},a_{t+1}$) for updating $Q_{\pi}$.  
So it's a State-Action-Reward-State-Action(**SARSA**)  

## Sarsa: Value Network Version  
1) Approximate $Q_{\pi}(s,a)$ by value network, $q(s,a;w)$
2) TD target: $y_{t} = r_{t} + \gamma * q(s_{t+1},a_{t+1};w)$.
3) TD error: $\delta_{t} = q(s_{t},a_{t};w) - y_{t}$
4) Loss: $\delta_{t}^{2}/2$.
5) Gradient: $\frac{\partial \delta_{t}^{2}/2}{\partial w} = \delta_{t} * \frac{\partial q(s_{t},a_{t};w)}{\partial w}$.
6) Gradient descent: $w \longleftarrow w - a * \delta_{t}*\frac{\partial q(s_{t},a_{t};w)}{\partial w}$.

## Summary  
**Goal:** Learning the action-value function $Q_{\pi}$  
**Tabular version**(directly learning $Q_{\pi}$).  
1) There are finite states and actions.
2) Draw a table, and update the table using Sarsa.
   
   
**Value network version**(function approximation).
1) Approximate $Q_{\pi}$ by the value network $q(s_{t},a_{t};w)$.
2) Update the parameter, w, using Sarsa.
3) Application: actor-critic method.
   


   


