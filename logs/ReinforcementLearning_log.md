# Reinforcement Learning Log

**Name:** Abdulaziz Aloufi  
**Student ID:** C00266252  
**Module:** Data Science & Machine Learning 2  

## Notebook / Topic
`ReinforcementLearning.ipynb` – Q-learning with FrozenLake

## Purpose
This notebook implements a reinforcement learning example using Q-learning on the FrozenLake environment. The aim was to demonstrate how an agent can learn through interaction, actions, rewards, and repeated experience.

## Work Completed
The following work has been completed:

- created the FrozenLake environment using Gymnasium
- checked the number of states and actions
- defined the meaning of the four possible actions
- created and initialised the Q-table
- set learning parameters such as:
  - learning rate
  - discount factor
  - epsilon
  - epsilon decay
  - number of episodes
- trained the agent using Q-learning
- updated the Q-table during each episode
- tracked rewards over training episodes
- calculated average reward over time
- tested the trained agent without exploration
- visualised the learned Q-table with a heatmap

## Changes / Alterations Made
During development, I made the following choices and adjustments:

- used FrozenLake as a simple reinforcement learning environment
- used Q-learning rather than a more advanced RL method
- used `is_slippery=False` to make the environment easier to learn
- added reward tracking and test episodes to better evaluate learning
- added a Q-table heatmap for easier interpretation

The first training setup did not work well:
- the Q-table remained all zeros
- the overall success rate was 0
- the agent never reached the goal during testing

To improve this, I changed:
- `epsilon_decay` from `0.995` to `0.999`
- `num_episodes` from `2000` to `10000`
- `epsilon_min` from `0.01` to `0.05`
- action selection by adding very small random noise when using `argmax`

## Practical Impact of Changes
These changes improved the notebook in the following ways:

- more training episodes gave the agent more chances to discover the goal
- slower epsilon decay kept exploration active for longer
- a higher minimum epsilon prevented exploration from ending too early
- random tie-breaking helped avoid repeatedly choosing weak actions when Q-values were equal

As a result, the agent successfully learned a useful policy.

## Results
Final results after improving the setup:

- successful training episodes: **8572**
- overall success rate: **0.8572**
- average test reward: **1.0**

In the final testing phase, the agent succeeded in all 20 test episodes.

The reward graph showed strong learning progress, rising from near zero to consistently high rewards over time.

## Analysis / Reflection
This notebook gives me a clear reinforcement learning implementation for the semester 2 portfolio. It is very different from the supervised and unsupervised notebooks because the agent learns through trial and error rather than labelled data.

This notebook also showed the importance of tuning reinforcement learning parameters. The first version failed completely, but after improving exploration and training settings, the model learned successfully.

## Next Steps
Before the final submission, I plan to:

- improve the written explanation of the Q-learning update rule
- refine the interpretation of the reward graph
- improve notebook presentation where needed