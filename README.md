# Deep Reinforcement Learning - Continuous Control

## Project Overview
The environment for this project is a world filled with 20 identical agents. Each agent is a double-jointed arm, and the joint values can be controlled to place the agent's hand at a specific position. The agent gets a reward of +0.1 whenever its hand is in the goal location specified by the environment.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector is a number between -1 and 1.

The environment is considered solved when the agents get an average score of +30 (over 100 consecutive episodes, and over all agents). To be more specific, all 20 agents concurrently play episodes which all end together after every 1000 time-steps. So after every 1000 time-steps, the episodic rewards for all 20 agents are aggregated and averaged, and this average is considered to be the episodic reward for the current episode. When a sequence of 100 such (averaged) episodic rewards, on being aggregated and averaged again, provides a mean reward of at least +30, the environment is considered solved.

## Getting Started
The following are the dependencies for this project:
  
  * Python 3.6 (installed using MiniConda in my case).
  * OpenAI gym (https://github.com/openai/gym) with the classic control (https://github.com/openai/gym#classic-control) and box2d (https://github.com/openai/gym#box2d) environments installed.
  * The python packages listed at https://github.com/udacity/deep-reinforcement-learning/blob/master/python/requirements.txt (can be installed using pip).
  * The dependencies specified at https://github.com/ShangtongZhang/DeepRL/blob/master/requirements.txt. On my setup, I found that torchvision, opencv-python and tensorboardX were required to be installed over-and-above what was already present. But please install the entire requirements.txt in case you face missing package issues.
  * The project Unity environment. In my case, I used the multi-agent Linux environment with 20 agents. A copy of this is present within the submission itself. In case your environment is different please remove the existing Reacher_Linux folder, copy the appropriate zip to the folder containing Continuous_Control.ipynb and extract it there. Again, please remember to use version two of the environment (the one with 20 agents).
  
## Instructions
All the code for the project is inside the Continuous_Control.ipynb notebook. Stepping through the notebook should be sufficient to train the agent from scratch and reproduce my results. The only thing which might need to be changed (depending on the reviewer's environment) is the file path with which the Unity environment is initialized.

Also, the weights of the final model are provided as winning_model.bin within the submission. This was saved using the mechanism provided by the ShangtongZhang DeepRL code (agent.save(file_name)). The weights should be restorable using the corresponding load API (agent.load(file_name)). 
