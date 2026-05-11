# VALUE ITERATION ALGORITHM

## AIM
Implement value iteration algorithm to find optimal policy for the altered frozen lake environment.

## PROBLEM STATEMENT
Make an alterations in the default frozen lake environment like changing the starting state, goal state and holes in the environment. Further find optimal policy using value iteration.


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
![alt text](image.png)
## optimal value function 
![alt text](image-1.png)
## success rate for the optimal policy.
![alt text](image-2.png)

## RESULT:

Thus, value iteration algorithm to find optimal policy for the altered frozen lake environment is successfully implemented.

