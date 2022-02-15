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
In this project, I implemented an off-policy method called Deep Deterministic Policy Gradient (DDPG). This method is an actor-critic, model-free algorithm based on the deterministic policy gradient that can operate over continuous action spaces. [REF]   This method was developed to provide modifications to deterministic policy gradient (DPG), inspired by the success of Deep Q-Network (DQN), which allow it to use neural network function approximators to learn in large state and action spaces online. 

The pseudocode of DDPG algorith can be found below. 

<img width="413" alt="image" src="https://user-images.githubusercontent.com/51778059/154117715-e74d8f58-e755-47ba-9e3c-158d0f90628b.png">
