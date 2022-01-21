# Acrobot with Reinforcement learning
### Acrobot Envirement
![](https://i.postimg.cc/3JDvJgrk/alii.png)



The envirement is two-dimensional and it consist of an Acrobot  game, in which a robotic arm is composed of two joints and two links and the joint between the two links is actued. In the beginning, the links are hanging downwards. The goal of the task is to move the end of the lower link up to a given height 
### Observation Space
The state of the agent can be indicated by the following variables :
- sin and cos of the two rotational joint angles (4 in total)
- the two angular velocities



### Actions and rewards
When the robotic arm chooses and performs an action, it may receive a reward or not. In each time step, it receives -1 as punishment until the goal is reached. Then, the agent’s task is to understand which actions can maximize the cumulative reward. There are three possible actions:
- Apply positive torque (-1)
- Apply negative torque (+1)
- Do nothing (0)


### Starting state
In the starting state , the links are hanging downwards: s = [1, 0, 1, 0, ..., ...]

### Episode termination
The episode ends when lower link of the arm reaches a given height , The episode may also terminate when it reaches the maximum number of steps (3000 used for training)

##Implementation
# The learning algorithm
# Reinforce
## Model architecture and  hyperparameters
The model is a neural network that takes as input the dimension of the state space and returns the optimal q-value corresponding to each possible action. Since there are three possible actions to move the robotic arm, the number of outputs returned are 3.
##### Hyperparameters
- Discount factor for target Q : GAMMA = 0.99
- Size of minibatch : batch_size=10
- Number of episodes : 3000
- Policy network : DQN

# The detailed results
![](https://i.postimg.cc/gcLVn9Nc/dsds.png)
In the beginning, the accumulated reward remains -500. After 3000 episodes, the score increases exponentially, remaining constant at around -100.








