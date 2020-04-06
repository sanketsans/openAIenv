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
- **`0`** - Cartpole - For info on the environment - https://github.com/openai/gym/wiki/CartPole-v0 

### 2. Cross Entropy Method
Here I use, CEM method to solve the environment. In this method, a small noise is added to weights to the neural network
instead on the actions taken by the agent. It is an off policy reinforcement learning method.
It uses a tanh activation function in the final layer - it can be used for continouse action space.

For every episode, a small amount of noise is added to the weights and rewards are evaluated. Its like 
genetic evolution method - 
- For every episode, you take a set of weights(by adding noise everytime) and calculate the rewards obtained 
using those weights.
- Then you sort those rewards and only take the top 10/ whatever the elite number and get the best weights
corresponding to those rewards. 
- In the end, you take the mean of those top weights and then calculate the reward with that mean weight. 
- Repeat step 1- 3 for number of episodes, to get correct set of weights. 

Projects solved:
- **`0`** - MountainCar_Continous - For info on the environment - https://github.com/openai/gym/wiki/MountainCarContinuous-v0
