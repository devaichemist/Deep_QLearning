# Deep Q-Learning - Lunar Lander

In this project, we implemented and trained a Deep Q-Learning (DQN) agent to solve the LunarLander-v2 environment from OpenAI's Gym library. The objective was to train an agent capable of landing a spacecraft on a designated landing pad on the lunar surface by maximizing cumulative rewards through trial and error.

To handle the challenges of continuous state space and sparse, delayed rewards, we incorporated two key enhancements to the standard Q-learning algorithm:

Experience Replay: A replay memory buffer was used to store past experiences (state, action, reward, next_state, done), which helped break correlations between sequential data and improved learning efficiency.

Target Network: A separate target Q-network was used to compute stable Q-value targets. The target network was periodically updated using a soft update mechanism to avoid rapid policy fluctuations.

The DQN architecture consisted of:

An input layer matching the 8-dimensional observation space.

Two fully connected hidden layers with 64 neurons each and ReLU activations.

An output layer with 4 neurons corresponding to the 4 discrete actions available to the agent (do nothing, fire left/right/main engine).

The agent followed an ε-greedy policy to balance exploration and exploitation, with ε decaying over time. The Q-network was trained using the mean squared error between predicted Q-values and target Q-values computed via the Bellman equation.

## Results

The agent was trained for a maximum of 2000 episodes or until it consistently achieved an average reward of 200 over the last 100 episodes, which is considered a solution threshold for this environment.

Key training outcomes:

The agent started with random actions due to high initial exploration (ε = 1.0), resulting in low and highly variable scores.

Over time, as ε decayed and the agent improved its policy, the reward per episode steadily increased.

The agent successfully solved the environment in 193 episodes, reaching an average reward of approximately 200 points over the last 100 episodes.

Final performance showed stable, controlled landings regardless of the initial force applied to the lander.

![lunar_lander](https://github.com/user-attachments/assets/2350d24a-74e5-4cae-9253-e56f78f073cf)

