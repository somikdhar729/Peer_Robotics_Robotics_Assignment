# Path Planning in a Multi-Robot Environment

## Given assumptions:
* Two robots
* Each robot has the knowledge of another robot in the surrounding environment

## Approach 

Some approaches for path planning
* Potential Fields Method
* Velocity Obstacles
* Dynamic Window Approach
* Reciprocal Velocity Obstacles
* Multi-agent RL
  
Given real-time path planning and collision avoidance, a <b>Reciprocal Velocity Obstacles (RVO)</b> approach is most suitable.

### Reasons
* Decentralized nature: Each robot plans its path independently but communicates with nearby robots to share position and velocity information.
* Scalable to multiple robots
* Balances computational efficiency with effective collision avoidance
* RVO assumes other robots are also using RVO, leading to smoother, more cooperative motions.

