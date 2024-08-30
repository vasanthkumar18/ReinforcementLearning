# ReinforcementLearning
A Reinforcement Learning bot Playing Pong game based on Atari Video Game

## About Pong
> Pong is one of the earliest arcade video games, featuring basic two-dimensional graphics in a table tennis sports format. The game was first produced by Atari and released in 1972.


![Uploading image.png…]()

## Implemenation
> 1. Implementation leverages TF-Agents, focusing on selecting an efficient optimizer and the appropriate replay buffer size.
> 2. The pong.ipynb file implements a deep reinforcement learning algorithm using Deep Q-Network (DQN) combined with an experience replay algorithm (Mnih et al., 2015).
> 3. This implementation works directly with raw pixel observations to learn policies for playing the Atari game Pong.

## Application
> 1. This demonstration showed how a deep learning model could learn to play 1970s Atari 2600 games from scratch.
> 2. The model not only learned to play the games but also matched or exceeded the performance of the best human experts.
> 3. The Jupyter notebook implementation uses the TF-Agents RL library for Python, which can simulate various environments, including Atari games.
> 4. This library is based on TensorFlow and developed by Google.
> 5. The settings in the notebook are similar to those in (Mnih et al., 2015), but with improved choices for the optimizer, loss function, and replay buffer settings.

## Adding Replay Buffer 

1. I have introduced a new hyper-parameter here (REPLAY MEMORY BUFFER SIZE) which has to be carefully tuned.
2. Since the replay buffer functions as a fixed-size circular storage for transitions, its size directly impacts the age of the oldest policy in the buffer.
3. Given that the policy is updated every four steps taken in the environment, the age of the oldest policy in the buffer corresponds to the number of environment steps divided by four gradient updates.
4. In this setting, buffer size of 50000 seems to work the best.

<img width="560" alt="image" src="https://github.com/user-attachments/assets/d713d36b-2ff8-4d29-862e-2ad70afdfb1b">


## Function - Adam Optimiser, MSE Loss abd Huber Loss 

1. Functions
   a. Adam Optimiser
   b. MSE Function
   c. Huber Loss Function by RMSProper optimiser
2. For DQN and Pong environment, Adam optimiser with MSE loss function seems to work much better. It converges nicely already after 400,000 iterations to approximately 19 average return while showing reasonably stable behaviour
3.  The model with RMSProp and Huber loss, on the other hand, takes a long time to learn, and even after 1.6 million iterations, it had only managed to reach a mean return of only approximately 10.

<img width="559" alt="image" src="https://github.com/user-attachments/assets/5cc662de-2c9f-49b6-b944-217915a0943c">


## References:

1. [Deep Reinforcement Learning: Pong from Pixels](http://karpathy.github.io/2016/05/31/rl/)
2. [TensorFlow and deep reinforcement learning, without a PhD (Google I/O '18)](https://www.youtube.com/watch?v=t1A3NTttvBA&t=873s)
3. Geron, A. (2019). Hands-on machine learning with scikit-learn, keras, and tensorflow
4. Luostari R. (2021). Playing Atari Pong with Deep Q-Network: Implementation using TF-Agents, se-lecting efficient optimiser, and right replay buffer size.

## Packages
The package.txt is added. The code is running without issues on Ubuntu 20.4 with Python 3.7.9.






