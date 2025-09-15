# RL Snake Game

A reinforcement learning implementation of the classic Snake game using Deep Q-Network (DQN) with PyTorch.

## Overview

This project implements an AI agent that learns to play Snake using deep reinforcement learning. The agent uses a neural network to make decisions about which direction to move based on the current game state.

## Files

- `game.py` - Snake game implementation using Pygame
- `agent.py` - RL agent with DQN algorithm
- `model.py` - Neural network model and training logic
- `helper.py` - Plotting utilities for training visualization

## Requirements

```bash
pip install torch pygame numpy matplotlib
```

For interactive plotting, also install:
```bash
sudo apt install python3-tk  # Ubuntu/Debian
```

## Usage

Run the training:
```bash
python agent.py
```

The agent will start playing and learning. Training progress is displayed in the console and plotted in real-time.

## How it Works

1. **State Representation**: 11-dimensional state vector including:
   - Danger detection (straight, left, right)
   - Current direction (4 directions)
   - Food location relative to head (4 directions)

2. **Action Space**: 3 possible actions:
   - Go straight
   - Turn right
   - Turn left

3. **Reward System**:
   - +10 for eating food
   - -10 for collision/game over
   - 0 for normal moves

4. **Neural Network**: 3-layer network (11 → 256 → 3) with ReLU activation

## Training

The agent uses:
- Experience replay with memory buffer
- Epsilon-greedy exploration strategy
- Q-learning with target network updates
- Batch training for stability

Model weights are automatically saved when a new high score is achieved.