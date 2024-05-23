# Intelligent Path Planning for Self-Driving UGV





## Abstract
This project aims to advance intelligent path planning for self-driving Unmanned Ground Vehicles (UGVs) through the application of Deep Reinforcement Learning (DRL). We employ algorithms such as Deep Deterministic Policy Gradient (DDPG) and Twin Delayed Deep Deterministic Policy Gradient (TD3) to enhance the decision-making capabilities of UGVs.
We used CARLA Simulator for training purpose.CARLA requires 8GB VRAM to run. As of sensors, we kept our model simple due to the lack of high configuration workstatione as we were using rtx 2070 (8GB VRAM), which was fulfilling only minimum requirements. Following are the sensors we used to get the state of the environment

1. Camera
2. GNSS
3. IMU

We passed these sensors values to our models as representation of state.


## Block Diagram
The system block diagram includes components such as IMU, GPS, Model, Camera, and more to facilitate intelligent path planning.

![Block Diagram](./images/block_diagram.png)

## Algorithms
### DDPG Algorithm
- Actor-Critic framework
- Utilizes historical experiences to update the model


![DDPG Architecture](./images/DDPG.png)



### TD3 Algorithm
- Improved version of DDPG with twin critics to mitigate overestimation bias

![DDPG Architecture](./images/TD3.png)



## Network Architectures
### Actor Network
- Input: State (18 dimensions)
- Layers: Relu (256, 128, 64, 32), Tanh (3 - Actions)

![DDPG Architecture](./images/actor.png)


### Critic Network
- Input: State (18 dimensions), Action (3 dimensions)
- Layers: Relu (256, 128, 64, 32), Linear (1 - Q value)

![DDPG Architecture](./images/critic.png)




## Canny Edge Detection & PCA
- Canny edge detection is used for detecting footpaths, oncoming traffic, and pedestrians.
- PCA is applied for feature reduction to enhance performance.

## Carla Simulator
- Open-source simulator for autonomous driving research.
- Provides realistic environments, varied weather, urban layouts, and traffic scenarios.
- Supports integration with RL frameworks and a wide range of sensors.


## PyQT GUI
- Main window for autonomous and manual control.


## Results
### Training Process
- Training graphs and data showing the performance of DDPG and TD3 models.

### Tensorboard
- Reward per episode graphs for DDPG and TD3.

## Limitations
- Reduced replay buffer size.
- Slow training due to frame rate issues.
- Power outages and system crashes.

## Conclusion
- Implemented and compared DDPG and TD3 algorithms.
- Manual control through WebSocket and sensor fusion using Arduino UNO.
- Deployed the trained actor model on Raspberry Pi.

## Future Work
- Further training and utilization of more powerful hardware.
- Testing on drone simulators.
- Integration of LiDAR for enhanced environmental perception.
- Improved image processing capabilities.

## References
- Fujimoto, S., Hoof, H., & Meger, D. (2018). Addressing Function Approximation Error in Actor-Critic Methods. arXiv:1802.09477
- Lillicrap, T.P., Hunt, J.J., Pritzel, A., Heess, N., Erez, T., Tassa, Y., Silver, D., & Wierstra, D. (2016). Continuous control with deep reinforcement learning. arXiv:1509.02971
- Dosovitskiy, A., Ros, G., Codevilla, F., López, A., & Koltun, V. (2017). CARLA: An Open Urban Driving Simulator. arXiv:1711.03938
- Sen Wang, Daoyuan, Xinshuo Weng Jia Deep Reinforcement Learning for Autonomous Driving. TORCS: arXiv:1811.11329v3 (2019)


## Institution
- CEME NUST

## Authors
- Awais Raza
- Syed Shuhood
- Zawar Khan
- Syed Shabih Ahmad

## Supervisor
- Dr. Fahad Mumtaz

