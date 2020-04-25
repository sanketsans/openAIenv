### Cross Entropy Method
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
