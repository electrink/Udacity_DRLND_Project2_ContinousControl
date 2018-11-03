[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"


# Udacity_DRLND_Project2_ContinuousControl
In this repository, I provide source codes for implementing a deep deterministic policy gradient (DDPG) algorithm to solve the continuous control (Reacher) problem in the Unity ML-Agents environment. This is the second project of the Udacity's Deep Reinforcement Learning Nano Degree (DRLND) program.

![Trained Agent][image1]

## Environment
The environment is provided by DRLND’s course website. In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of my agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

Note that my project submission need only solve one of the two versions of the environment. 

#### Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  my agent must get an average score of +30 over 100 consecutive episodes.

#### Option 2: Solve the Second Version

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents.  In particular, my agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).  Specifically,
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent.  This yields 20 (potentially different) scores.  We then take the average of these 20 scores. 
- This yields an average score for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 

## Getting Started
### Prerequisites
- tensorflow==1.7.1
- Pillow>=4.2.1
- matplotlib
- numpy>=1.11.0
- jupyter
- pytest>=3.2.2
- docopt
- pyyaml
- protobuf==3.5.2
- grpcio==1.11.0
- torch==0.4.0
- pandas
- scipy
- ipykernel
- pickle
- collections
- unityagents

Note that to work properly in the Windows 7 64-bit environment, one has to mannualy place the following three folders - *unityagents*, *communicator_objects*, and *Banana_Windows_x86_64* - at the root of this working directory. This may or may not be the case for other operating systems.  

## Instructions
### Training
Open *P2_Continuous_Control_Jing Zhao_Final.ipynb* to start training an AI agent. This script interacts with the Unity ML-Agents environment to gain experience which is defined by visiting a new state and receiving a reward from the previous action. In addition, the script also uses the DDPG learning algorithm implemented in *ddpg_agent_v2.py* and *model_v2.py* to improve the agent's performance over time.    

### Viewing the Result
After training is done, one can view the agent's performance across total episodes in *P2_Continuous_Control_Jing Zhao_Final.ipynb*. This result is stored in the *zipScore_solved.pickle* file. The 100-point moving average of the score is also provided to illustrate that the 20 agents environment is solved in 80 episodes. The weights of trained networks are saved in files *checkpoint_actor_SOLVED_180.pth* and *checkpoint_critic_SOLVED_180.pth* respectively.

## Author
Jing Zhao. Implementation of the DDPG algorithm is inspired by the [Deep Deterministic Policy Gradient Algorithms (DDPG)](https://github.com/electrink/deep-reinforcement-learning/tree/master/ddpg-bipedal) project in the DRLND program.
