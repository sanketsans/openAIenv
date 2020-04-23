## Acrobot-v1 using REINFORCE

Model Architecture: 

```
NEWModel(
  (fc1): Linear(in_features=6, out_features=32, bias=True)
  (fc2): Linear(in_features=32, out_features=64, bias=True)
  (fc3): Linear(in_features=64, out_features=3, bias=True)
  (dropout): Dropout(p=0.2, inplace=False)
)
```
 
I used Adam optimizer with a learning rate of 0.01.
I was able to achieve an **average reward(<-100.0)** over 100-episodes in less than 500 episodes, and an **average reward(<-90.0)** was achieved by 787th episode.

Epochs:
```
Episode 0 	Loss -500.0 
Episode 100 	Loss -361.97
Episode 200 	Loss -169.2  
Episode 300 	Loss -122.71 
Episode 400 	Loss -113.5  
Episode 500 	Loss -99.46  
Episode 600 	Loss -96.55  
Episode 700 	Loss -98.38 
Episode 787 	Loss -89.29 
```
Here is the model performance : 

## With Dropout layers

![Performace](https://github.com/sanketsans/openAIenv/blob/master/REINFORCE/Acrobot/with_dropout.png)

## Without Dropout layers

![Performance](https://github.com/sanketsans/openAIenv/blob/master/REINFORCE/Acrobot/without_dropout.png)

