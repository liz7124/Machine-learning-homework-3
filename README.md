# Homework 3 - Machine Learning
## A. Policy Iteration
This repository is provide answer for Machine Learning class Homework 3. The goal is to train agent to play **Grid World** using **policy iteration**. This code is a modification from [RLCode Reinforcement Learning](https://github.com/rlcode/reinforcement-learning).

### i. Original Code
The iteration cycle will be (according to this code) move -> evaluation -> improvement (back to move again). After I did some evaluation -> improvement, the agent will explore the environment, so it will increase the knowledge of the agent and make improvement on the next phase.

As we can see in the picture (first iteration), the empty grid that next to the triangles will get negative value, and than the other empty grid that next to circle will get positive value, and the other will get value zero.

After every cycle/iteration, the value of each empty grid will increase or decrease. This algorithm is based on policy, so after doing the evaluation we must do the improvement for updating the policy. Policy determines what the agent will do (action) for every states. If we just doing the evaluation without update the policy, this iteration will not reach the goal.

As we can see in the picture (Last iteration), for the original code, the program will get the converge state after 7 iteration/cycle.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-i-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-i-2.PNG) |

### ii. Modified the value function


### iii. Add 1 more triangle

## B. Value Iteration
This repository is provide answer for Machine Learning class Homework 3. The goal is to train agent to play **Grid World** using **value iteration**. This code is a modification from [RLCode Reinforcement Learning](https://github.com/rlcode/reinforcement-learning).

### i. Original Code

### ii. Modified the value function

### iii. Add 1 more triangle