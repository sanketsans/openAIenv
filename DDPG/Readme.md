### Deep Deterministic Policy Gradient

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
