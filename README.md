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


## Instructions

To run the agent simply follow the instructions in each cell to download dependencies, choose the environment (1 or 20 agents learning together), see the state statistics and take a random action in the environment. To train the agent run the cell with "ddpg" method which is a runner function for the agent. 

Implementation of the agent can be found in file `agent.py` along with hyperparameters and Replay Buffer function. 

Actor and Critic models can be found in file `model.py`.

Saved weights for actor and critic network are saved in `actor_checkpoint.pth` and `critic_checkpoint.pth`.

The solution is described in detail in file `Project-report.PDF`.


## Testing the saved model

To test the trained agent using saved weights in files `actor_checkpoint.pth` and `critic_checkpoint.pth` simply run these lines of code:
```
test_agent = Agent(state_size=3, action_size=4)
test_agent.actor_local.load_state_dict(torch.load('actor_checkpoint.pth'))
test_agent.critic_local.load_state_dict(torch.load('critic_checkpoint.pth'))
```
and then run cell #5 replacing `train_mode=True` to `train_mode=False` and replacing 
```
actions = np.random.randn(num_agents, action_size)
```
to 
```
actions = test_agent.act(state)
```
the follwing line of code clipping the action values between -1 and 1 is also redundant, since the agent is doing the clipping.
