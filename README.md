# Kasırga-AI: Simulation-Based Wargame Learner

**Kasırga-AI** is a reinforcement learning-based simulation environment where an autonomous military agent learns to make tactical decisions in a grid-based battlefield. This project demonstrates how artificial agents can be trained to interact with dynamic combat environments using Deep Q-Learning and similar RL techniques.

## Project Goals

The main objective is to build a basic 2D environment where an agent learns to:

- Navigate around obstacles,
- Approach or neutralize a static or moving enemy,
- Reach a defined strategic target zone.

The learning is driven by a reward system based on tactical success, penalizing aimless or self-destructive behavior.

## Technologies Used

- Python
- Custom OpenAI Gym-style Environment
- PyTorch (for implementing RL agents)
- NumPy (for grid and matrix operations)
- matplotlib (for visualization of agent performance)

## Environment Description

- Grid Size: 10x10
- Entities:
  - 1 Agent (our autonomous unit)
  - 1 Enemy (stationary or optionally mobile)
  - Randomly placed static obstacles (e.g., walls, mines)
- Agent Actions:
  - Move: Up, Down, Left, Right
  - Optional: Fire (with damage logic)
- Observations:
  - Agent position
  - Enemy position
  - Obstacle map

## Reward Function Design

- +0.1 for moving closer to the enemy
- +1 for successfully hitting the enemy (if firing enabled)
- -0.5 for colliding with an obstacle
- -0.1 for random movement
- +2 for reaching the goal region

These values can be adjusted to shape agent behavior during training.

## RL Algorithm

- Phase 1: **Deep Q-Learning (DQN)** for discrete actions and environments
- Phase 2 (Optional): **Proximal Policy Optimization (PPO)** for continuous improvement and stability

## Development Roadmap

1. Define a 10x10 grid environment class (similar to Gym)
2. Implement entity placement: agent, enemy, obstacles
3. Design state, action, and reward representations
4. Implement and train a DQN agent
5. Visualize agent behavior using matplotlib
6. (Optional) Add advanced enemy logic and alternative scenarios

## Getting Started

Clone the repository and install the required packages:

```bash
git clone https://github.com/yourusername/kasirga-ai.git
cd kasirga-ai
pip install -r requirements.txt
```

Then, run the environment and train the agent:

```bash
python train_dqn.py
```

## Folder Structure

```
kasirga-ai/
│
├── environment/
│   └── battlefield.py        # Grid world and environment logic
├── agent/
│   └── dqn_agent.py          # Deep Q-Learning agent
├── train_dqn.py              # Training loop and logging
├── utils/
│   └── visualization.py      # Graphing and environment rendering
├── requirements.txt
└── README.md
```

## License

This project is licensed under the MIT License.

---

For contributions or suggestions, feel free to open an issue or a pull request.
