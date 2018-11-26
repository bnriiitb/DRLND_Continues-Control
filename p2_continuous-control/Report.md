## Methodology

This work implements the DDPG algorithm (Deep Deterministic Policy Gradients) to the 20 agents Reacher environment, as described in [_Continuous Control with Deep Reinforcement Learning_][ddpg-paper] (Lillicrap et al). The foundation of this code-base is from the [Udacity DRL `ddpg-bipedal` notebook][ddpg-repo]

[ddpg-paper]: https://arxiv.org/pdf/1509.02971.pdf
[ddpg-repo]: https://github.com/udacity/deep-reinforcement-learning/blob/master/ddpg-bipedal/DDPG.ipynb

Deep DPG (DDPG) is a model-free approach which can learn competitive policies for all of our tasks using low-dimensional observations. In many cases, we are also able to learn good policies directly from pixels
A key feature of the approach is its simplicity: it requires only a straightforward actor-critic architecture and learning algorithm with very few “moving parts”, making it easy to implement and scale to more difficult problems and larger networks. DDPG can sometimes find policies that exceed the performance of the planner, in some cases even when learning from pixels (the planner always plans over the underlying low-dimensional state space).

## Implementation 

I have trained the network using DDPG algorithm. 
For Actor, I've used a three layer MLP with 128 and 128 neurons respectively in hidden layers. The state vector is the 33 dimensional vector. The output vector is of size 4. I've trained the network using Adam optimizer with an actor learning rate of 0.0002, critic learning rate of 0.0002 and batch size of 128 with a discount factor of 0.99.

## Results 

The agents were able to solve task in 216 episodes with a final average score of 58.76 after 300 episodes.
![chart](chart.png)


## Enhancements

- Improving results tunning the networks scructures (adding layers or units per layers, ...)
- Implement PPO, D3PG or D4PG that probably  would produce better results


