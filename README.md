# openAIenv
# openAIenv : Solving openAI gym environment with mulitple Reinforcement learning algorithm

## Introduction

For this repo, I have used multiple algorithm and I try to solve each gym's environment with them. 
For every project, I have also added a video on how the agent behaves after the training is complete.

### 1. Simple Method

This is a pretty straight forward method - where I simple instantiate a weight matrix and multiple with the states to get 
rewards over a period and then try to maximise the reward.
For discrete state and action space. 

Projects solved:
- **`1`** - Cartpole - For info on the environment - https://github.com/openai/gym/wiki/CartPole-v0 

### 2. Cross Entropy Method
Here I use, CEM method to solve the environment. In this method, a small noise is added to weights to the neural network
instead on the actions taken by the agent. It is an off policy reinforcement learning method.
It uses a tanh activation function in the final layer - **it can be used for continouse state action space.**
- Instantiate a weight matrix.
For every episode, a small amount of noise is added to the weight matrix and rewards are evaluated. Its like 
genetic evolution method - 
- For every episode, you take a set of weights(by adding noise everytime to the weight matrix) and calculate the rewards obtained 
using those weights.
- Then you sort those rewards and only take the top 10/ whatever the elite number and get the best weights
corresponding to those rewards. 
- In the end, you take the mean of those top weights and then calculate the reward with that mean weight. 
- Repeat step 2-4 for number of episodes, with the mean weight and add noice to it to get correct set of weights. 

Projects solved:
- **`1`** - MountainCar_Continous - For info on the environment - https://github.com/openai/gym/wiki/MountainCarContinuous-v0

### 3. Deep Deterministic Policy Gradient

This is quite a complex RL algorithm - can be used for continous state and action space. It is a kind of Actor - Critic method(Atleast that's what the founders call it), but it is somewhat similar to supervised learning. 
**It can be used for continous state action space.**
The actor takes the actions and is evaluated with the Q values generated using the critic. So, here actor acts as the output variable and the q values by the critic - we can call them, the labels. 

- For every action taken by the actor model - you get state, action, reward, new_state, done(if task is done). So, you can create a tuple of { S, A, R, S', D } and store it in the replay buffer. 
- Take a sample from the reply buffer and train the network from the experiences stored. 
## Make a note that for a critic network, the first hidden layer's input is fcs1_units + action_size, 
so self.fc2 = nn.Linear(fcs1_unit + action_size, fcs2_unit)
<p align="center">
  <img width="460" height="400" src="https://github.com/sanketsans/openAIenv/blob/master/hidden_layer_explanation.png">
</p>
- I have tried to explain how DDPG works with both actor - critic model in thebelow diagram.

<p align="center">
  <img width="460" height="400" src="https://github.com/sanketsans/openAIenv/blob/master/DDPG/ddpg_explained.jpeg">
</p>

Projects solved:
- **`1`** - Pendulum - For info on the environment - https://github.com/openai/gym/wiki/Pendulum-v0

### 4. REINFORCE 

REINFORCE is a policy based RL algorithm. It collects couple of episodes and then generate a loss function to be 
back-propagated along the network. **I mostly use it for continous/discrete state space but only discrete action space.**
Algorithm : 
- For an episode, we generate a categorical distribution of probabilites and then collect the log probabilities of each action taken. 
- After an episode is over, we mulitply the log probabilities with the associated reward for that action.
- The main aim is to give more preference to those actions which generates more reward. 
- The loss function is calculated by taking the sum of all the product of log probabilites with total reward. 

Projects solved:
- **`1`** - CartPole - For info on the environment - https://github.com/openai/gym/wiki/CartPole-v0
- **`2`** - LunarLander - For info on the environment - https://github.com/openai/gym/wiki/Leaderboard#lunarlander-v2



