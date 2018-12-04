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
In this section, we add function for generate a random value for `value_table` and random value for `policy_table` but with the sum is one.

    def  generate_random_value_table(self, w,h):
	    value_table = [[round(random.random(), 2)] * w for _ in  range(h)]
	    return value_table
    
    def  generate_random_policy_table(self, w,h):
	    rand =  list(np.random.dirichlet(np.ones(4), size=1).ravel())
	    policy_table = [[rand] * w for _ in  range(h)]
	    return policy_table

After run the program, the result will be random too. So it's not recommended to run the program with set the value with random value. Because of the value is too random, the probability to reach the goal will be random too. It will be stochastic, not deterministic.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-ii-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-ii-2.PNG) |


### iii. Add 1 more triangle
In this section, we add one more triangle and set the reward to be -1 in the (3,4) with assumption the first value is row, and the second value is column.

    self.reward[3][2] = -1 # reward -1 for triangle

The result of First iteration is similar to section i (Original Code), but for this section it need 9 iteration to get the converge state.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-iii-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/1-policy-iteration/screenshots/3a-iii-2.PNG) |


## B. Value Iteration
This repository is provide answer for Machine Learning class Homework 3. The goal is to train agent to play **Grid World** using **value iteration**. This code is a modification from [RLCode Reinforcement Learning](https://github.com/rlcode/reinforcement-learning).

Value function is the expectation on how much rewards in the future. To do so, the agent will choose the state that maximize the rewards.

### i. Original Code
On the first iteration, the empty grid that next to the circle will get positive value, and the other will get zero value.

This algorithm is based on value, so if we did the calculate function without update the policy it will reach the goal anyway.

As we can see in the picture (Last iteration), the program will get the converge state at 6th iteration.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-i-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-i-2.PNG) |


### ii. Modified the value function
In this section, we add function for generate a random value for `value_table`.

    def  generate_random_value_table(self, w,h):
    	    value_table = [[round(random.random(), 2)] * w for _ in  range(h)]
    	    return value_table

As we setup the value_table with random value, we cannot predict in which iteration the program will get the converge state. So as well as we said in policy iteration, this way is not recommended too. When we try to run this section it comes up with 10 iteration most of the time until get the converge state.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-ii-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-ii-2.PNG) |

	    
### iii. Add 1 more triangle
In this section, we add one more triangle and set the reward to be -1 in the (3,4) with assumption the first value is row, and the second value is column.

    self.reward[3][2] = -1 # reward -1 for triangle

The result of First iteration is similar to section i (Original Code), but for this section it need 8 iteration to get the converge state.

| First Iteration | Last Iteration |
|--|--|
| ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-iii-1.PNG) | ![enter image description here](https://github.com/liz7124/Machine-learning-homework-3/blob/master/2-value-iteration/screenshots/3b-iii-2.PNG) |
