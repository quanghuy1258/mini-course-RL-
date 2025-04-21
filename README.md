# mini-course-RL-2025
Mini-course "Reinforcement Learning: From the Foundations to Learning with Human Feedback and DeepSeek-R1" - 2025

- Speaker: Prof. Tran Thanh Long, Department of Computer Science, University of Warwick (UK)
- Abstract: In this mini-course, the lecturer will cover the foundations of reinforcement learning such as Markov decision process, model-free learning, and model based learning, then discuss the newest research trends such as RLHF (RL with Human Feedback) and their recent applications in LLMs.

# some notes

### Books, references, materials, etc.
- Richard S. Sutton, Andrew G. Barto. (2018). Reinforcement Learning, second edition: An Introduction (2nd edition).  
  http://www.incompleteideas.net/book/RLbook2020.pdf
- Shie Mannor, Yishay Mansour, Aviv Tamar. Reinforcement Learning: Foundations.  
  https://sites.google.com/view/rlfoundations/home

Others can be found in the slides, so they will not be mentioned here.
However, the two above are the most important ones (should read).

Some miscellaneous readings:
- Richard S. Sutton, Michael Bowling, and Patrick M. Pilarski. The Alberta Plan for AI Research.  
  https://arxiv.org/abs/2208.11173  
  http://incompleteideas.net/Talks/AlbertaPlan.pdf

### Questions

1. What is the (multi-armed) bandit theory?
   What is it related to reinforcement learning (RL)?
2. What is the essence of dynamic programming?  
   Many CS students are familiar with dynamic programming as a technique for solving problems in competitive programming contests.  
   However, dynamic programming should be considered a method in the context of optimization, i.e. it is used to solve optimization problems, similar to linear programming.
3. What are Online and Offline RL?  
   In what ways does Offline RL differ from other data-driven learning approaches, such as supervised and unsupervised learning?
4. What is a metric space?
5. Deep Q-Network (DQN) for Atari Games: How to optimize the policy 𝜋? What is Experience Replay and how to exploit it to train RL?

### Topics, keywords, etc.

1. Markov decision process (MDP): might be the simplest model for describing systems that involve states, actions, and rewards.
   
   To put it simply: MDP = Markov reward process (MRP) + actions,  
   where a MRP simply extends a Markov chain by assigning a reward to each state.

   Keywords: control theory (maybe one application of MDP?), markovian (I don't know why I noted that 😞)

   If we fix the policy 𝜋 (which determines how actions are chosen based on states), then MDP reduces to MRP.  
   Now, we need to find the best MRP, i.e. optimize the MDP: Bellman equation, dynamic programming.
   
2. Model-free approaches:

   - Monte Carlo policy.
   - ***Temporal difference.***
   - SARSA.
   - Q-learning.
  
   Among the four methods mentioned above, temporal difference (TD) is considered the most important one (I'm not entirely sure, but I remember the speaker mentioning that Prof. Sutton said so).

3. Function approximation:

   The state-value function $V^\pi(s)$ is the expected discounted return starting with state $s$ and successively following policy $\pi$.  
   The action-value function $Q^\pi(s, a)$ is the expected discounted return associated with first taking action $a$ in state $s$ and following policy $\pi$.

   Some problems:
   - Large state / action space.
   - Defining a policy $\pi$ as a table is hard (lack of memory, cannot visit every state or state-action pair, etc.).

   → approximation:  
   $V^\pi(s) \approx \hat{v}(s, w)$  
   $Q^\pi(s, a) \approx \hat{q}(s, a, w)$  
   where $w$ is a parameter vector characterizing the policy $\pi$.

   Some function approximators:
   - linear combinations of features.
   - neural networks.
   - decision trees.
   - nearest neighbors.
   - fourier / wavelet bases.
   - ...

   However, sigmoid is not used because of the vanishing gradient problem.
