# Reinforcement-Learning-Basics
CartPole Project - Balancing the cartpole with only two discrete actions - action space - left or right. There are also 4 Box variables that act as the environment space. PPO algorithm is being used for this project. 
The project served as an introductory project to Reinforcement Learning. 

Reinforcement Learning

Focuses on teaching agents through trial and error. 
Actively engaging with the environment.

Agent – Action –> Environment – Reward+Observations → Agent

Applications
1. Autonomous Driving
2. Securities Trading
3. Neural Network Architecture Search
4. Simulated Training of Robots

Limitations/Considerations
1. For simple problems, RL can be overkill
2. Assumes environment is Markovian - Future states of environment are based on current observations, ignores random acts.
3. Training can take a long time and is not always stable 
Exploration exploitation trade-off -> Might exploit too early, might take too long. Hyperparameter adjustment

## 1. Setup
https://stable-baselines3.readthedocs.io/en/master/

## 2. Import Dependencies
import gymnasium instead of gym. Gym is outdated. 
https://stable-baselines3.readthedocs.io/en/master/modules/base.html

RL Algorithms
1. Base RL Class
2. A2C
3. DDPG
4. DQN
5. HER
6. PPO
7. SAC
8. TD3

## 3. Environments
Environments can be real or simulated
Simulated Environments - ability to trial and train in a safe and cost-effective manner.

OpenAI Gym - Provides easy way to build environments for training RL agents

https://www.gymlibrary.dev/


OpenAI Gym Spaces

https://www.digitalocean.com/community/tutorials/getting-started-with-openai-gym

OpenAI Gym Env class - Implements a simulator that runs the environment that the agent needs to be trained on. 

Observation Space defines the structure as well as legitimate values for observation of state of the env. 
Example - Screenshots, certain characteristics of the env described in vector form

Spaces
Action Space and Observation Space

action_space, which describes the numerical structure of the legitimate actions that can be applied to the environment.
observation_space defines the structure as well as the legitimate values for the observation of the state of the environment. 

Box - n dimensional tensor. For continuous values. Range of values. Ex- Box(0,1,shape=(3,3))
Discrete - Set of items. Ex- Discrete(3), like 3 types of actions 0,1,2.
Tuple - Tuple of other spaces. Ex- Tuple((Discrete(2), Box(0,100,shape=(1,))))
Dict - Dictionary of spaces. Ex- Dict({‘height’:Discrete(2), ‘speed’:Box(0,100,shape=(1,))})
MultiBinary - One hot encoded binary values. Ex- MultiBinary(4) 4 positions, 4 bits
MultiDiscrete - Multiple discrete values. Ex- MultiDiscrete([5,2,2]) first value will be 0-4, second 0-1, third 0-1

Environment functions
1. Reset - Resets env to initial state and returns observation of env corresponding to initial state. 
2. Step - Takes an action as an input and applies it to the environment, which leads to the environment transitioning to a new state. Output of this is below
Observation.
Reward.
Done.
Info. 
3. Render - To see how the environment looks in the current state.
4. Close - Closing the pop up window of current state. 


Classic Control 
https://www.gymlibrary.dev/environments/classic_control/

CartPole
https://www.gymlibrary.dev/environments/classic_control/cart_pole/

## 4. Training
Two types - Model-Based RL and Model-Free RL 
Model-Free RL only uses current state values to make predictions. 
Model-Based RL predicts the future state of the model to try to generate best possible action. 

Algorithms must be chosen based on the action space. 
There are different algorithms that work good for different action space type
- Box works well with A2C, DDPG, HER, PPO, SAC, TD3. Not DQN
- Discrete works well with A2C, DQN, HER, PPO
- MultiDiscrete works well with A2C, PPO
- MultiBinary works well with A2C, PPO
- MultiProcessing works well with A2C, PPO

Evaluation Metrics
Average reward - How well the model is going to perform in that particular environment using that particular reward
Average episode length - How long the agent lasts in that particular environment. For environments that dont have a fixed environment length, ex - breakout env, self driving env 
There are also others for the training mterics and also the time metrics.

Training strategies
Train for longer - see if it improves performance 
Hyperparameter tuning - can yield significant results
Try different algorithms - check state of the art training

 
## 5. Callbacks, Alt Algorithms and Architectures
Callbacks - to log out data or save the model under certain conditions

Modifying Neural Network Architecure

Using Different Algorithm 
