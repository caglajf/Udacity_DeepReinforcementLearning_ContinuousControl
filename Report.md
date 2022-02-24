<h1>Udacity Deep Reinforcement Learning Nanodegree Program</h1>
<h1>Project 2: Continuous Control Report</h1>

<h2>Problem Statement</h2>

In the second project of Udacity Deep Reinforcement Learning Nanodegree Program, I worked with the Reacher environment. In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1. 

<h2>Solving the Environment</h2>

The goal of this project is to train the agents to get an average score of +30 (over 100 consecutive episodes, and over all agents). After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).

In this project, I preferred to use distributed training which contains 20 identical agents, each with its own copy of the environment.The advantage of my approach is use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.

<h2>Learning Algorithm</h2>
In this project, I implemented an off-policy method called [Deep Deterministic Policy Gradient (DDPG)](https://arxiv.org/pdf/1509.02971.pdf). This method is an actor-critic, model-free algorithm based on the deterministic policy gradient that can operate over continuous action spaces. This method was developed to provide modifications to deterministic policy gradient (DPG), inspired by the success of Deep Q-Network (DQN), which allow it to use neural network function approximators to learn in large state and action spaces online. 

The pseudocode of DDPG algorith can be found below. 

<img width="413" alt="image" src="https://user-images.githubusercontent.com/51778059/154117715-e74d8f58-e755-47ba-9e3c-158d0f90628b.png">

  <h4>Hyperparameters</h4>
 Replay buffer size: 1000000<br />
 Batch size: 128<br />
 Gamma (discount factor): 0.99<br />
 Tau (soft update of target parameters): 0.001<br />
 Learning rate for actor: 0.0001<br />
 Learning rate for critic: 0.001<br />
 Weight decay: 0<br />
 Noise: 1
 Noise decay: 0.999999<br />

   <h4>Model</h4>
- Actor<br />
  The Neural Network has two hidden layers with 400 and 300 neurons, respectively. The activation function used is ReLU for the input and first layer and tanh for the output The output layer has 4 values which corresponds to the dimension of each action.<br />
 - Critic<br />
  The Neural Network has two hidden layers with 400 and 300 neurons, respectively. The activation function used is ReLU for the input and first layer and none for the output. The output layer has just one value which corresponds to the assesment made by the critic of the action chosen by the actor.<br />
    

<h2>Results</h2>
After implementing DDPG method, the score evolution can be seen below:

The environment has been successfully solved in 2311 episodes.

<h2>Ideas for Future Work</h2>
  I implemented DDPG method and solved the environment. In order to improve the performance of the agents, some other methods and improvements can also be tried. <br />
- More effort can be spent for hyperparameter optimization to improve results.<br />
- Different algorithms can be implemented such as [A2C](https://medium.com/deeplearningmadeeasy/advantage-actor-critic-a2c-implementation-944e98616b), [A3C](https://medium.com/emergent-future/simple-reinforcement-learning-with-tensorflow-part-8-asynchronous-actor-critic-agents-a3c-c88f72a5e9f2), [PPO](https://openai.com/blog/openai-baselines-ppo/) or [D4PG](https://arxiv.org/pdf/1804.08617.pdf) to compare the performance of training. <br />
- Prioritized experience replay can also be tried to see if it improves the training time.<br />

