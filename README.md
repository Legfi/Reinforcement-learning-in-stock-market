# Reinforcement-learning-in-stock-market

## Description
This project implements a custom OpenAI Gym environment for simulating Bitcoin trading using reinforcement learning. It allows users to train reinforcement learning agents to make trading decisions (buy, sell, or hold) based on historical Bitcoin price data.

## Features
- Custom Gym environment (`BitcoinTradingEnvironment`) for Bitcoin trading simulation.
- Support for various reinforcement learning algorithms via the Stable Baselines3 library.
- Visualization of trading actions taken by the RL agent.
- Evaluation of net worth and profit/loss percentage.

## Requirements
- Python 3.x
- [Stable Baselines3](https://github.com/DLR-RM/stable-baselines3)
- [yfinance](https://github.com/ranaroussi/yfinance)
- [matplotlib](https://matplotlib.org/)

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Legfi/Reinforcement-learning-in-stock-market.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Run the `train_model.ipynb` notebook to train the reinforcement learning model on the Bitcoin trading environment.
2. Once trained, use the trained model to make trading decisions and simulate trading.
3. Customize the environment and experiment with different reinforcement learning algorithms and hyperparameters as needed.

## Example
```python
# Training the RL model
import numpy as np
from stable_baselines3 import PPO
from stable_baselines3.common.vec_env import DummyVecEnv

# Create an instance of BitcoinTradingEnvironment
env = BitcoinTradingEnvironment(bitcoin_data)

# Wrap the environment in a VecEnv
env = DummyVecEnv([lambda: env])

# Define and train the RL model (PPO in this case)
model = PPO("MlpPolicy", env, verbose=1)
model.learn(total_timesteps=10000)

# Save the trained model
model.save("bitcoin_trading_model")
```

## License
This project is licensed under the [MIT License](LICENSE).

## Acknowledgments
- Inspiration from OpenAI Gym and Stable Baselines3.

## Contributors
- [Dadmehr Berahmandzadeh](https://github.com/Legfi)

## Support
For any questions or issues, please open an [issue](https://github.com/Legfi/Reinforcement-learning-in-stock-market/issues) on GitHub.

---
