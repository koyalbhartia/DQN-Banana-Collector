An agents is trained to solve the task of collecting as many yellow bananas as possible, while avoiding blue bananas. 
The environment is implemented in unityagents.

### Environemntal Details :
```
Observation space type: continuous
Observation space size (per agent): 37
Stacked Vector Observation: 1
Action space type: discrete
Action space size (per agent): 4
```

### Action space :
```
0 - forward
1 - backward
2 - left
3 - right
```

### Observation Space :

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction. 

### Reward :
A reward of +1 is provided for collecting a yellow banana, 
and a reward of -1 is provided for collecting a blue banana.

### Neural Network Architecture :
The Neural Network architrcture consists of:
Input layer of 37 neurons : Environemnt observation space
64 neurons first hidden layer - followed by ReLU activation functions
64 neurons second hidden layer - followed by Re:U activation functions
Output layer - 4 neurons : 4 possible actions

The above is based on a feed-forward neural network used to approximate Q(s,a).


### Agent hyperparameters to learn and interact with the environment :
```
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR = 5e-4               # learning rate 
UPDATE_EVERY = 4        # how often to update the network
```

### Hyperparameters used in DQN Network
```
Number of episodes=2000, 
Maximum time step per episode =1000,
Epsilon Initial value =1.0 (Complete exploration)
Min Epsilon = 0.01 (Greedy at the end by 0.99)
Decay factor = 0.995
```
### Implementation

DQN is used to train the RL agents. 
The agent interacts with the environment and receives rewards.
This improves the estimate of the state-action value function Q(s,a). 
When the estimate converges to the true state-action value function, 
the optimal policy is easily recovered by always choosing the action with the largest expected return.

The Agent that hekps to learn has the following implementation:

1. The replay buffer maintains a tuple of [State , Action , Reward , Next state , Done ]
2. Optimizer used for back propagation is Adams.
3. E- greedy algorithm is impelemented to choose actions.
4. Two networks are maintained in order to have a smooth learnings.
5. The Tau parameter is used to update the network slowly so that we so not overshoot in gradient descent and function learned by the neural network is better.

Every training step is saved in the reply buffer and after every 4 episodes after minimum 64 steps we take randomly 64 samples and train the network.
So if a eposide goes for 1000 time steps that means our network will update 250 times in an episode.

## Final Results :

![Screenshot from 2021-07-05 17-28-20](https://user-images.githubusercontent.com/40532456/124521890-c42cf880-ddb6-11eb-9f26-eec90535f74e.png)


**Hence the problem can be solved with an average score of +13 bananas in 400 episodes over an average of 100 episodes.**


### Future Work and Ideas to improve results.
1. Prioritized experience replay: Experience replay has been used in the project, but prioritized rpelay might have the most considerable effect. 
This can be achieved easy way is to achieve it is to scale the probabilities by the TD error.
2. Dueling DQN : This architectures decouple the values of states and actions. As certain states are better than others, the dueling architecture allows the network to take advantage of this.
3. Actor Critic : This method might try to decrease the variance and improve the speed of learning.
