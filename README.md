# VALUE ITERATION ALGORITHM

## AIM
Implement value iteration algorithm to find optimal policy for the altered frozen lake environment.

## PROBLEM STATEMENT
The OpenAI Gym FrozenLake environment is a gridworld problem where an agent navigates a slippery frozen surface to reach the goal state while avoiding holes, and the fenced boundaries prevent the agent from leaving the grid. In this modified FrozenLake environment, alterations such as changing the starting state, goal state, and hole positions are made, and the optimal policy is then determined using the value iteration algorithm

## VALUE ITERATION ALGORITHM
# Step 1:
Import required libraries for the program.
# Step 2:
Load the frozen lake environment and make changes. 
# Step 3: 
Define the value iteration function.
# Step 4:
Run the function and display the results.

## VALUE ITERATION FUNCTION
### Name: VARNIKA P
### Register Number: 212223240170
```PYTHON
def value_iteration(P, gamma=1.0, theta=1e-10):
    V = np.zeros(len(P), dtype=np.float64)
    while True:
      Q=np.zeros((len(P),len(P[0])),dtype=np.float64)
      for s in range(len(P)):
        for a in range(len(P[s])):
          for prob, next_state, reward, done in P[s][a]:
            Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
      if np.max(np.abs(V-np.max(Q,axis=1)))<theta:
        break
      V=np.max(Q,axis=1)
    pi=lambda s: {s:a for s,a in enumerate(np.argmax(Q,axis=1))}[s]
    return V, pi
```

## OUTPUT:
## optimal policy
<img width="437" height="127" alt="image" src="https://github.com/user-attachments/assets/23b3770a-3af2-40c7-85be-fb21653b3a8f" />

## optimal value function 
<img width="561" height="30" alt="image" src="https://github.com/user-attachments/assets/ea658392-2771-411b-9040-1b665f4c376e" />

## success rate for the optimal policy
<img width="396" height="103" alt="image" src="https://github.com/user-attachments/assets/1e03e5d3-9bd5-4415-9a88-024c9294213e" />


## RESULT:

Thus, value iteration algorithm to find optimal policy for the altered frozen lake environment is successfully implemented.

