# [Projects](http://vlarko.com/Projects)
# Autonomous Space Junk Collector

<img src="/Photos/space junk 1.png" height="400" style="border:7px solid black">

# Overview
A deep Reinforcement Learning (RL) approach to grasping objects in zero gravity, in order to collect and deorbit space junk.

The goal of this project is to use an existing robotic arm platform (Sawyer) to collect space junk. It is assumed that the robot would be hypothetically mounted on some sort of satellite, & would be put in an orbit where it would encounter space junk.

A Deep RL based grasp estimation approach can be used to create a solution to this problem. The camera feed from Sawyer’s built in arm camera would be fed to a trained Deep RL model, which would output a 6 DoF antipodal grasp position for the Sawyer robot to execute. From there doing Deep RL in a simulated space environment in CoppeliaSim would solve the grasp estimation problem, and a trained net could be produced.

Full IEEE format paper here: [Paper](https://github.com/jmay137/James-May-Engineering-Portfolio/blob/main/Robotics/JamesMay-EEEE784-Final-Report.pdf)

# Specifications
- Sawyer used as robotic arm platform
- Stable Baselines3 implementation of Proximal Policy Optimization is used to perform RL
- Simulated space environment (zero gravity) in CoppeliaSim
- Partial observation of environment, relying solely on 2 RGB cameras & current robot joint state

# Final Results
After training the model for about a week, I was able to evaluate and see how well it had performed. It was not able to properly grab an object, but it did show some interesting behavior. A summary of the actions learned can be seen in the video below:

[Space Junk Summary Video](https://www.youtube.com/watch?v=UMbzJc0y_CM)

For future works, I'm actively working on training this model further, to see if it could achieve grasping with enough training time.
