Report

# Learning Algorithm Description
## Algorithm
The Deep Q Learning (DQN) algorithm is used for this implementation, which is a value-based reinforcement learning algorithm. The DQN algorithm estimates the value of taking an action in a given state using a neural network as a function approximator. The algorithm is based on the Q-learning algorithm, but instead of maintaining a table of Q-values, the Q-values are approximated using a neural network. The DQN algorithm was originally introduced in the paper Human-level control through deep reinforcement learning.

## Implementation
The implementation of the DQN algorithm is adapted from an exercise in the Udacity course. A multilayer perceptron with 2 hidden layers of 64 nodes each is used as the neural network. The activation function used is the rectified linear unit (ReLU).

### Hyperparameters:

The hyperparameters used for the DQN algorithm are as follows:

```python
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR = 5e-4               # learning rate 
UPDATE_EVERY = 4        # how often to update the network
```
While the activation function, hidden layer size, and number of hidden layers are not listed here as hyperparameters, they are often treated as such and tuned in other implementations.  

### Model Architecture
The neural network used for function approximation in the DQN algorithm is a multilayer perceptron with 2 hidden layers of 64 nodes each. The input to the network is the observation (state) of the environment, and the output is the Q-value for each action in that state. The activation function used in the hidden layers is the rectified linear unit (ReLU).

# Ideas for Future Work
While the DQN algorithm was able to solve the Banana environment without hyperparameter tuning, there are several ways to improve its performance and efficiency. Some possible future ideas for improving the DQN algorithm and the agent's performance in this environment are:

* Hyperparameter tuning
  * Modify hyperparameters such as the learning rate, discount factor, and replay buffer size to improve the agent's learning and performance.
  * Experiment with different activation functions, hidden layer sizes, and number of hidden layers.
  * Search for similar tasks in published work on ML-Agents and try to adapt the hyperparameters used in those tasks to this environment.
  * Manually tune a few of the hyperparameters and run a lot of experiments to track results.
* Implement improvements from the Rainbow paper
  * The Rainbow paper combines various improvements made in the DQN algorithm and does ablation studies to determine the importance of each change. Start with the most important changes or implement all of them to see if there is a significant improvement in performance.
* Use multiple seeds
  * Run the same training process with different random seeds to see how the results vary and whether the agent is robust to changes in the initial conditions.
* Update the environment to be used with up-to-date ML-Agents packages
  * This would allow using other implementations of DQN, such as those from Stable Baselines 3, CleanRL, and Sample Factory.
  * Having a known good implementation to compare against is useful for evaluating the effectiveness of changes made to the algorithm.
* Experiment with other algorithms
  * Try other value-based or policy-based algorithms to see if there is a better fit for this environment.

# Plot of Rewards
* As shown in the jupyter notebook, training was done for 2000 episodes.  
* an episode is defined as x timesteps or y
* rewards are accumulated for blah and shown as the score
![Episode rewards](2000_episode_rewards_plot_3.png "Episode rewards")

