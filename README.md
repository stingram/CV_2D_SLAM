# CV_2D_SLAM
Implementation of Graph SLAM for Robot in 2D environment

##  Summary

This project implements Graph SLAM for a robot in a 2D environment. Graph SLAM uses noisy measurements  of known landmarks within visibility range and noisy movements to estimate the robot's position in the world over time and the final estimated pose of the robot and the landmarks. 

The image below shows the visualized output of the Graph SLAM algorithm. It marks the estimated landmark positions and the final estimated pose of the robot in the 2D world space. The robot is marked by a red circle and each landmark is represented by a purple X.

![Example Output](images/robot_world.png)

This repository includes three main files: robot_class.py, helpers.py and SLAM.ipynb. The main driver logic and more detailed information of the main process  can be found in SLAM.ipynb.

robot_class.py creates an instance of a robot in 2D space. It is initially pointed in a random direction and moves in a straight line until it comes close to a wall and stops. For measurements, the robot senses the x-distance and y-distance to landmarks. The robot class provides a move function, which attempts to mvoe the robot by dx, dy. The sense function for the robot class returns the x-distances and y-distances to landmarks within visibility range. Not all landmarks may be in this range and the list of measurements is of variable length.

helpers.py contains a display_world function, which displays the world that a robot is in it assumes the world is a square grid of some given sizeand that landmarks is a list of landmark positions. It also has a make_data function, which makes the robot data the data is a list of measurements and movements: [measurements, [dx, dy]] collected over a specified number of time steps, N.