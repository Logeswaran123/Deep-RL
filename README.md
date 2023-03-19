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

* <b>Policy-based methods:</b> Train the policy directly to learn which action to take given a state.<br />
* <b>Value-based methods:</b> Train a value function to learn which state is more valuable and use this value function to take the action that leads to it.

## Value based method
In value-based methods, we learn a value function that maps a state to the expected value of being at that state.

In the case of value-based methods, you don’t train the policy: your policy is just a simple pre-specified function (for instance, Greedy Policy) that uses the values given by the value-function to select its actions.

In value-based methods, you’ll use an <b>Epsilon-Greedy Policy</b> that handles the exploration/exploitation trade-off.

Types:<br />
* <b>State-value function</b><br />
For each state, the state-value function outputs the expected return if the agent starts at that state and then follows the policy forever afterward.

* <b>Action-value function</b><br />
In the action-value function, for each state and action pair, the action-value function outputs the expected return if the agent starts in that state and takes action, and then follows the policy forever after.

In either case, whatever value function we choose (state-value or action-value function), the returned value is the expected return.

However, the problem is that it implies that to calculate EACH value of a state or a state-action pair, we need to sum all the rewards an agent can get if it starts at that state.

This can be a computationally expensive process, and that’s where the <b>Bellman equation</b> comes to help us.

### Bellman equation
Instead of calculating each value as the sum of the expected return, which is a long process, we calculate the value as the sum of immediate reward + the discounted value of the state that follows.

### Monte Carlo: learning at the end of the episode
Monte Carlo waits until the end of the episode, calculates return and uses it as a target for updating value of state t.

So it requires a complete episode of interaction before updating our value function.

### Temporal Difference Learning: learning at each step
[![Temporal difference learning](https://img.shields.io/badge/Temporal%20difference%20learning-Wiki-white.svg)](https://en.wikipedia.org/wiki/Temporal_difference_learning)<br />
Temporal difference (TD) learning refers to a class of model-free reinforcement learning methods which learn by bootstrapping from the current estimate of the value function. These methods sample from the environment, like Monte Carlo methods, and perform updates based on current estimates, like dynamic programming methods.

While Monte Carlo methods only adjust their estimates once the final outcome is known, TD methods adjust predictions to match later, more accurate, predictions about the future before the final outcome is known. This is a form of bootstrapping.

### Q-Learning
Q-Learning is an off-policy value-based method that uses a TD approach to train its action-value function. Q-Learning is the algorithm we use to train our Q-function, an action-value function that determines the value of being at a particular state and taking a specific action at that state.

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
* [Deep Reinforcement Learning Course](https://huggingface.co/deep-rl-course/unit0/introduction?fw=pt#introduction) - Big thanks to the creators of the course. Most of the explanations are taken from this course.
