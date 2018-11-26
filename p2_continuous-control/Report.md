## Methodology

This work implements the DDPG algorithm (Deep Deterministic Policy Gradients) to the 20 agents Reacher environment, as described in [_Continuous Control with Deep Reinforcement Learning_][ddpg-paper] (Lillicrap et al). The foundation of this code-base is from the [Udacity DRL `ddpg-bipedal` notebook][ddpg-repo]

[ddpg-paper]: https://arxiv.org/pdf/1509.02971.pdf
[ddpg-repo]: https://github.com/udacity/deep-reinforcement-learning/blob/master/ddpg-bipedal/DDPG.ipynb

* Deep DPG (DDPG) is a model-free approach which can learn competitive policies for all of our tasks using low-dimensional observations. In many cases, we are also able to learn good policies directly from pixels

* A key feature of the approach is its simplicity: it requires only a straightforward actor-critic architecture and learning algorithm with very few “moving parts”, making it easy to implement and scale to more difficult problems and larger networks. 

* DDPG can sometimes find policies that exceed the performance of the planner, in some cases even when learning from pixels.

## Implementation 



The network comprises of 2 networks:

Actor: 256 -> 256
Critic: 256 -> 256 -> 128

Hyperparameters:

replay buffer size = 1e6
minibatch size = 128
discount factor = 0.99
tau for soft update of target parameters = 1e-3
learning rate of the actor = 2e-4
learning rate of the critic = 2e-4
L2 weight decay = 0.0001

I've trained the network using DDPG algorithm with the state vector of size 33 and the output vector is of size 4 using Adam optimizer.

## Results 

The agents were able to solve task in 216 episodes with a final average score of 58.76 after 300 episodes.
![chart](chart.png)


## Enhancements

- Improving results tunning the networks scructures (adding layers or units per layers, ...)
- Implement PPO, D3PG or D4PG that probably  would produce better results


