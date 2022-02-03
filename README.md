# gridworld-rl

Author: Joshua Sia
Date: 2020-10-21

## About
Reinforcement learning (RL) is used to solve a grid-like maze comprised of 29 grids as shown in the image below. There are two terminal states: (i) a reward state which yields +10 reward, and (ii) a penalty state which yields -100 reward. To randomise the location of the reward state, the single digit number *x* is used. The location of the reward state is given by ((*x* + 1) mod 3) + 1 (i.e. when *x*=5, the reward state is 1). The penalty state is state 11.

![gridworld-img](https://github.com/joshsia/gridworld-rl/blob/main/gridworld.png)

Possible actions in this grid world are moving North, East, South or West by one state. However, the actions are not deterministic. Actions only succeed with probability *p* which is given by 0.25 + 0.5 * (*y*+1)/10. In the event that the action fails (e.g. North fails), the true action taken is randomly chosen from the remaining set of possible actions (e.g. East, South or West) with equal probability. After the true action is determined, if a wall blocks the agent's path, the agent simply stays at the same state. There is a movement cost of -1 associated with each action except for movements which lead to a terminal state.

The discount factor for rewards, *gamma*, is given by 0.2 + 0.5 * *z*/10. The variables *x*, *y* and *z* which control the location of the reward state, the probability of an action succeeding, and the discount factor respectively, can be changed at the top of the notebook.

Three different RL methods are used to find the optimal set of actions to reach the reward state:
1. Dynamic programming (with full world knowledge)
2. Monte Carlo learning
3. Temporal Difference learning

The three methods are compared and discussed in the notebook.

## Usage

To rerun the notebook and explore different parameters, clone this repository, install the dependencies listed below, and run the notebook.

## Dependencies
- numpy=1.21.2
- matplotlib=3.4.3
