### DQN 

This is the evolved version of q-learning method. Read paper ![DeepMind Paper](https://web.stanford.edu/class/psych209/Readings/MnihEtAlHassibis15NatureControlDeepRL.pdf)
The q-table here is replaced with a neural network model. And the loss function(mostly MSE) is used to back-propagate the loss
in the network. 
A replay buffer is also used in the network - to sample the experiences in batches and to train the network on each batches. 

The agent have **two** neural network model - local & train. Since we are updating the model(can be every step or after a specific
number of time step) and predicting the model at every time step, the network will be all over the place. That's why we need 
two different neural network model - one for training and one for learning. 

Q_tar = reward + gamma*Q_val*(1-done)

loss_function = MSE(Q_exp, Q_tar)

Projects solved:
- **`1`** - LunarLander - For info on the environment - https://github.com/openai/gym/wiki/Leaderboard#lunarlander-v2
- **`2`** - Highway(Incomplete) - For info on the environment - https://github.com/eleurent/highway-env

