Report

# Learning Algorithm Description
## Algorithm
The Deep Q Learning (DQN) algorithm is used for this implementation, which is a value-based reinforcement learning algorithm. The DQN algorithm estimates the value of taking an action in a given state using a neural network as a function approximator. The algorithm is based on the Q-learning algorithm, but instead of maintaining a table of Q-values, the Q-values are approximated using a neural network. The DQN algorithm was originally introduced in the paper Human-level control through deep reinforcement learning.

## Implementation
The implementation of the DQN algorithm is adapted from an exercise in the Udacity course. A multilayer perceptron with 2 hidden layers of 64 nodes each is used as the neural network. The activation function used is the rectified linear unit (ReLU).

### Hyperparameters:

The hyperparameters used for the DQN algorithm are as follows:

```python

##### dqn_agent.py #####
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR = 5e-4               # learning rate 
UPDATE_EVERY = 4        # how often to update the network

##### Other tuneable parameters #####
HIDDEN LAYER SIZE = 64
NUMBER OF HIDDEN LAYERS = 2
eps_start = 1
eps_end = 0.01
eps_decay= 0.995
```

### Model Architecture
The neural network used for function approximation in the DQN algorithm is a multilayer perceptron with 2 hidden layers of 64 nodes each. The input to the network is the observation (state) of the environment, and the output is the Q-value for each action in that state. The activation function used in the hidden layers is the rectified linear unit (ReLU).

# Ideas for Future Work
While the DQN algorithm was able to solve the Banana environment without hyperparameter tuning, there are several ways to improve its performance and efficiency. Some possible future ideas for improving the DQN algorithm and the agent's performance in this environment are:

1. Hyperparameter tuning: The current implementation of the DQN algorithm does not include hyperparameter tuning, which could significantly improve the agent's performance. The report suggests several methods for tuning hyperparameters, including manually modifying a few hyperparameters, looking for similar tasks in published work on ml-agents, and using existing RL baselines.
2. Implementing improvements from the Rainbow paper: The Rainbow paper introduces several improvements to the DQN algorithm, including prioritized experience replay, double Q-learning, and dueling networks. These improvements have been shown to significantly improve performance on a variety of tasks, and implementing them could help improve the agent's performance in the current environment.
3. Running with multiple seeds: The agent's performance may be affected by the random initialization of the neural network weights and other stochastic components of the DQN algorithm. Running the algorithm with multiple seeds and comparing the results could help identify more robust and consistent hyperparameters and architecture choices.
4. Increasing speed of training: The current implementation trains the agent for 2000 episodes, which may take a significant amount of time. Finding ways to speed up training could allow for more experiments and iterations on the agent's performance.
5. Integrating with tensorboard and/or weights and biases: More detailed logging and visualization of the agent's learning metrics could provide insights into the agent's behavior and performance during training. Tensorboard and weights and biases are popular tools for visualizing and tracking machine learning experiments.

# Plot of Rewards
* As shown in the jupyter notebook, training was done for 2000 episodes.  
* an episode is defined as x timesteps or y
* rewards are accumulated for blah and shown as the score
![Episode rewards](2000_episode_rewards_plot_3.png "Episode rewards")

