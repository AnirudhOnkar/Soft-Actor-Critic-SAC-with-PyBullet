# Soft Actor-Critic (SAC) with PyBullet

## Overview
This repository contains an implementation of the **Soft Actor-Critic (SAC) algorithm**, a state-of-the-art reinforcement learning (RL) method. SAC is an off-policy actor-critic method designed for continuous action spaces, optimizing for both **maximizing rewards** and **exploration efficiency**.

The implementation is based on **PyTorch** and is designed to work with **PyBullet environments**, making it useful for robotics and physics-based simulation tasks.

## Features
- **Implemented in PyTorch** for efficient GPU acceleration
- **Uses Replay Memory** for stable training
- **Supports automatic entropy tuning** for adaptive exploration
- **Utilizes Q-Networks and Gaussian Policy Networks**
- **Designed for continuous control tasks**

## Repository Structure
```
|-- model.py               # Defines the Q-Network and Gaussian Policy Network
|-- sac_agent.py           # Implements the SAC algorithm, including action selection and policy updates
|-- replay_memory.py       # Implements the replay buffer for storing past experiences
|-- utils.py               # Contains utility functions for soft and hard updates of neural network parameters
|-- AbtPyBulletEnv-SAC_lr001-sc2500.ipynb  # Jupyter notebook for training and evaluating the SAC agent
|-- README.md              # Documentation for this repository
```

## How It Works
The SAC algorithm follows these key steps:
1. **Action Selection**: The agent selects an action using a stochastic Gaussian policy.
2. **Experience Storage**: The agent stores `(state, action, reward, next_state, done)` in the replay buffer.
3. **Sampling & Learning**: The agent samples a mini-batch from the replay buffer and updates:
   - The **Q-Networks** using mean squared error loss.
   - The **Policy Network** using the reparameterization trick.
   - The **Entropy Temperature (alpha)** to balance exploration and exploitation.
4. **Target Network Update**: The target Q-Network is updated using soft updates.

## Installation & Setup
```sh
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
pip install -r requirements.txt
```

## Running the Training
```sh
jupyter notebook AbtPyBulletEnv-SAC_lr001-sc2500.ipynb
```

## Usage
- Modify hyperparameters like learning rate, batch size, and reward scaling inside `sac_agent.py`.
- Use the `select_action()` method to obtain actions for any given state.
- Train the agent in PyBullet environments and monitor performance.

## Author
Your Name

## License
This project is licensed under the MIT License.

