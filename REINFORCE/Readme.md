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
- **`3`** - Acrobot - For info on the environment - https://gym.openai.com/envs/Acrobot-v1/
