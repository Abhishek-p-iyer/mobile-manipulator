# MOBILE MANIPULATOR

This repository consists of the necessary files to run a robotic manipulator with a base with 4 wheels, the robotic arm has 5 degrees of freedom and can be manipulated using the GUI or the positions of the arm can be moved using the terminal. 

![robotic_manipulator_1](https://user-images.githubusercontent.com/67633494/151372304-93ed63ec-2749-4a9e-889b-e38e6b507764.png)


## RUNNING THE PACKAGE 

Step-1: Create a package with dependencies "std_msgs", "roscpp" and "rospy"


Step-2: You now should have a package with a CMakeLists.txt file and a package.xml file.


Step-3: Download all of the files in the folders from this repository and run catkin_make


Step-4: Run the launch files 
```
roslaunch mobile_manipulator_body arm_gazebo_control.launch
```

Step-5: Move the arm 
```
rostopic pub /arm_controller/command trajectory_msgs/JointTrajectory '{joint_names: ["arm_base_joint","shoulder_joint", "bottom_wrist_joint", "elbow_joint","top_wrist_joint"], points: [{positions: [-0.1, 0.5, 0.02, 0, 0], time_from_start: [1,0]}]}' -1
```

## USING THE GUI 

Step-6: To steer the bot 
```
rosrun rqt_robot_steering rqt_robot_steering
```
You will need to change the topic inside the GUI to: 
```
/robot_base_velocity_controller/cmd_vel
```

## REFERENCE 
I used this article for building this robotic manipulator 
[Robotic Manipulators](https://automaticaddison.com/how-to-build-a-simulated-mobile-manipulator-using-ros/)
