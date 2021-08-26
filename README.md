[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"


## Project 2: Continuous Control (Reacher)

![Trained Agent][image1]

For this project, we had to build an AI agent to conduct a continous task for keeping the robotic hand (blue nob) in zone of the moving target with the aim of reaching a score greater than 30 for 100 episodes in a row. An episode constists of 1000 timesteps. In each timestep the agent receives a reward of +0.01 for staying in the zone. The robotic arm can be moved by adjusted 4 continous actions that determine the force exerted on the joints of the robotic arm thereby determining its location in space. The actions range in between the values of -1 and +1. The selected environment for this project was the more challenging 20 robotic arm environment


## Installing the Agent
1. The environment is included in the repository with a Windows environment. The environmnet can also be downloaded from the following links for your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

2. Run an environment of python 3.6.8 natively or with the use of Anaconda
3. Using pip install the `requirements.txt`


## Running the Agent

Simply start up the notebook and run each cell

## Solving the Environment

A single agent was implemented using the D4PG architecture to solve the environment in a parallel manner where the 33 state variables for each of the 20 agents are processed by the neural network in a batched manner in a parallelized fashion taking full advantage of the GPU power available and allowing the timesteps to proceed faster.

The agent manages to solve the environment in record speed reaching a score greater than 30 in 119 episodes. 
