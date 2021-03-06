# Estimating Q(s,s') with Deep Deterministic Dynamics Gradients

<p align=center>
<img src="https://github.com/uber-research/D3G/blob/master/resources/trajectory.gif" width="200">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://github.com/uber-research/D3G/blob/master/resources/learned_pendulum.gif" width="200">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://github.com/uber-research/D3G/blob/master/resources/learned_reacher.gif" width="200">
</p>

<div align="center">
  Figure 1: Model predictions learned by D3G in a Gridworld, InvertedPendulum-v2, and Reacher-v2.
</div>
</br>
</br>

Official PyTorch implementation of Deep Deterministic Dynamics Gradients. Code is based heavily on the Twin Delayed DDPG [implementation](https://github.com/sfujim/TD3). For research purpose only. Support and/or new releases may be limited.

### Setup
Clone the repo: 
```
git clone https://github.com/uber-research/D3G.git && cd D3G
```

We use Python 3.6.2. Requirements for D3G can be installed by running:
```
pip install -r D3G/requirements.txt
```

### Running toy QSS problems
The stochastic action results can be reproduced by running:
```
cd toy_problems/stochastic_actions && python model_gridworld.py --stochasticity {rand}
```

The windy cliffworld results can be reproduced by running:
```
cd toy_problems/windy_cliffworld && python model_gridworld.py 
```

The redundant action results can be reproduced by running:
```
cd toy_problems/redundant_actions && python model_gridworld.py
```

The shuffled action results can be reproduced by running:
```
cd toy_problems/shuffled_actions && python model_gridworld.py && python model_gridworld.py --shuffled
```

### Running D3G
The paper results can be reproduced by running:
```
cd D3G && ./mujoco_experiments/run_D3G_experiments.sh
```

The model predictions for Reacher-v2 and InvertedPendulum-v2 can be visualized. To see this, run:
```
cd D3G && python main.py --policy D3G --env Reacher-v2 --visualize
```

### Running Learning from Observation
The paper results can be reproduced by running:
```
cd D3G && ./lfo_experiments/run_D3G_experiments
```

The model predictions for Reacher-v2 and InvertedPendulum-v2 can be visualized here too. To see this, run:
```
cd D3G && python learn_from_observation.py --policy D3G --env Reacher-v2 --visualize
```
