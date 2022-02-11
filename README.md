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

In this project, the code was generated using the second version of the environment (with 20 Agents) using DDPG algorithm. Because it has been shown that having multiple copies of the same agent sharing experience can accelerate learning. [You can find more information from here.](https://ai.googleblog.com/2016/10/how-robots-can-acquire-new-skills-from.html) 

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically, after each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.This yields an average score for each episode (where the average is over all 20 agents). The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 

<h2>Getting Started</h2>

- In order to activate the environment, please follow the instructions in the [DRLND GitHub repository](https://github.com/udacity/deep-reinforcement-learning#dependencies) of Udacity to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels.

- For this project, you will not need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below for twenty (20) agents. You need only select the environment that matches your operating system:

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

(For Windows users) Check out this [link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use this [link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to enable a virtual screen, and then download the environment for the Linux operating system above.)

<h2>Insructions for training an agent</h2>

After you have followed the instructions above, open Continuous_Control.ipynb (located in the p2_continuous-control/ folder in the DRLND GitHub repository) and follow the instructions to learn how to use the Python API to control the agent.
