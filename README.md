# Deep-RL
My learning journey on Deep Reinforcement Learning.

## Reinforcement learning
Reinforcement learning is a framework for solving control tasks (also called decision problems) by building agents that learn from the environment by interacting with it through trial and error and receiving rewards (positive or negative) as unique feedback.
<br /><br />
Goal of agent is to maximize its expected cumulative reward (because of the reward hypothesis).

## Policy π
Given a state, a policy will output an action or a probability distribution over actions. That is, given an observation of the environment, a policy will provide an action (or multiple probabilities for each action) that the agent should take.
<br /><br />
Goal is to find an optimal policy π* , aka., a policy that leads to the best expected cumulative reward.

To find this optimal policy (hence solving the RL problem), there are two main types of RL methods:

<b>Policy-based methods:</b> Train the policy directly to learn which action to take given a state.<br />
<b>Value-based methods:</b> Train a value function to learn which state is more valuable and use this value function to take the action that leads to it.

## Value based method
In value-based methods, we learn a value function that maps a state to the expected value of being at that state.

Given a state, our action-value function (that we train) outputs the value of each action at that state. Then, our pre-defined Greedy Policy selects the action that will yield the highest value given a state or a state action pair.

In the case of value-based methods, you don’t train the policy: your policy is just a simple pre-specified function (for instance, Greedy Policy) that uses the values given by the value-function to select its actions.

## Deep RL agents
| Name | Description | Code | Model |
|:----:|:-----------:|:----:|:-----:|
| LunarLander-v2 | A Lunar Lander agent that will learn to land correctly on the Moon |  | https://huggingface.co/Loges/LunarLanderv2 |

## Learning materials
* Reinforcement Learning: An Introduction, Richard Sutton and Andrew G. Barto Chapter 1, 2 and 3 | [PDF book](http://incompleteideas.net/book/RLbook2020.pdf)
* Foundations of Deep RL Series, L1 MDPs, Exact Solution Methods, Max-ent RL by Pieter Abbeel | [Youtube](https://www.youtube.com/watch?v=2GwBez0D20A&ab_channel=PieterAbbeel)
* Spinning Up RL by OpenAI Part 1: Key concepts of RL | [Link](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)

## Other resources
* [Getting Started With OpenAI Gym: The Basic Building Blocks](https://blog.paperspace.com/getting-started-with-openai-gym/)
* [Make your own Gym custom environment](https://www.gymlibrary.dev/content/environment_creation/)

## References
* [Deep Reinforcement Learning Course](https://huggingface.co/deep-rl-course/unit0/introduction?fw=pt#introduction)
