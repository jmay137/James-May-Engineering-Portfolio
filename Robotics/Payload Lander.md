# Overview
Mayload was my final project for my Principles of Robotics class during my 4th year as an electrical engineering student. The project was to create a robot to solve a problem. My problem was creating a robot capable of returning a CubeSat payload back to earth after the mission was completed.   
  
Goals:

- Create a 4-legged robot capable of landing a 1U cubesat payload safely  
    
- **Keep robot upright for a wide variety of landing angles**
    - **​**Actively updates all 4 legs (8 joints) so that the 4 feet will land simultaneously on the ground, regardless of descent angle
- Use ROS to solve inverse kinematics, communicate sensor data and servo positions over wireless link
- Detect landing w/ micro switches mounted to feet
- Robot descends on a parachute or similar recovery mechanism (simulated)

  
Assumption:

- Robot would land on a smooth, flat surface (ie: landing pad)
    - This simplified the inverse kinematics

# Software
General Software Flow:

- Robot sends sensor data to web server, which is read by a laptop running ROS 2 on Ubuntu  
    
- ROS program determines servo positions by applying inverse kinematics equations
- ROS program sends servo positions back to robot, robot updates servos
- Inverse kinematics routine continues until robot detects landing

  
The inverse kinematics equations were solved by hand, and then implemented into the Mayload ROS package.  
  
Final I.K. Equations:  
1. ϴ3 = ATAN2[ ((Px- B*cos(ϴ1))/L) , ((-Py- B*sin(ϴ1) -L)/L) ]  
2. ϴ2 = ϴ3 - ϴ1


# Hardware
The robot's construction was entirely 3d-printed components & COTS hardware. The 3d-printed components were modelled in Fusion 360, as well as the rest of the assembly.  
  
The electronics used were as follows:

- MPU-6050 3-Axis Gyroscope Accelerometer sensor module
- ESP-32 microcontroller
- PCA9685 servo driver board
- 8x SG-90 micro servos

​  
Since this robot was a prototype, its looks definitely reflect that. All electronics and wiring is exposed, and there is no shielding or covers whatsoever to give it an aesthetic appeal. This was largely due to the constraint of getting the robot done in a semester. My focus was almost purely on functionality, over aesthetic appeal/having a "finished" look. Given more time, I would have worked to improve on these issues.



# Final Results
Below is a video demonstrating the robot's capabilities, which was a requirement of the project.  
  
Moving forward if I were to continue working on this robot, here are some of the changes that would be made:

- Add a third hip joint to allow quadpod locomotion after landing
    - This would complicate the inverse kinematics somewhat, but ROS has some tools that could help make this process easier
    - Constructing a URDF & using IK solvers would be a more elegant solution  
        
- Make the construction more robust by swapping some of the 3d-printed components for stronger materials from more conventional manufacturing methods
- Do actual parachute based testing
- Clean up wiring and properly house electronics