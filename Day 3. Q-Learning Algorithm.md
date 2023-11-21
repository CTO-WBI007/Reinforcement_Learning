# The Principal Of Q-Learning And The Applied Codes  

## Sarsa VS Q-Learning  

*Sarsa is for training action-value function*, $Q_{\pi}$(s,a). 

We used Sarsa for updating value-network.  

*Q-Learning is for training the optimal action-value function, so we use it for updating DQN*  

## Derive TD Target 

**Identity**:  $Q_{max}(s_{t},a_{t}) = E[R_{t} + \gamma Q_{max}(S_{t+1},A_{t+1})]$. 

Thus $Q_{max}(S_{t+1},A_{t+1}) = max_{a}Q_{max}(S_{t+1},a).$

**Updated Identity**:  $Q_{max}(s_{t},a_{t}) = E[R_{t} + \gamma max_{a}Q_{max}(S_{t+1},a)]$.  

$R_{t}\longrightarrow r_{t},S_{t+1}\longrightarrow s_{t+1}.$ 

Thus $R_{t} + \gamma max_{a}Q_{max}(S_{t+1},a)\approx r_{t} + \gamma max_{a}Q_{max}(s_{t+1},a)$  
We call it **TD target** $y_{t}$

## Q-Learning: Tabular Version  
*We will use TD target to study maximum value function*  

1) Observe a transition with 4 elements ($s_{t}, a_{t}, r_{t}, s_{t+1}$).
2) TD target: $y_{t} = r_{t} + \gamma max_{a}Q_{max}(s_{t+1},a)$.
3) TD error: $\vartheta_{t} = Q_{max}(s_{t},a_{t}) - y_{t}$.
4) 













