<h1>Udacity Deep Reinforcement Learning Nanodegree Program</h1>
<h1>Project 2: Continuous Control</h1>

<h2>General Description</h2>
This project is the second project of Udacity Deep Reinforcement Learning Program. The aim of this project is to train an agent to maintain a double-jointed arm's position at the target location for as many time steps as possible. Repository contains the code that I used for training an agent, along with the trained model weights and a report describing my learning algorithm in which I described the details of my implementation, along with ideas for future work.

<h2>The Environment</h2>
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

![image](https://user-images.githubusercontent.com/51778059/153588788-a2db6eda-d5cd-4714-b91a-d54092368e79.png)

<h4>The Distributed Training</h4>

For this project, two separate versions of the Unity environment was provided by Udacity:

- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment.

In this project, the code was generated using the second version of the environment (with 20 Agents) using DDPG algorithm.

