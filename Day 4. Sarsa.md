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




   


