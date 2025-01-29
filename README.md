# Bayes Filter-Based Robot Decision Making (C++)

## Overview
This project implements a **Bayes Filter** in **C++ with ROS** to estimate the probability of a door being open based on visual sensor data. By utilizing **Bayesian inference**, the system robustly handles noisy sensor measurements, enabling a mobile robot to make informed navigation decisions in uncertain environments.

## Features
- **Camera-Based Feature Detection**: Uses OpenCV's **Good Features to Track** algorithm to detect key visual features in the robot's environment.
- **Bayesian Inference for Decision Making**: Computes the probability of the door being open using multiple noisy sensor readings.
- **Full Bayes Filter Implementation**: Incorporates both prediction and measurement updates to model uncertainty in the door’s state.
- **Automated Door Handling**: The robot waits until the probability of an open door reaches **0.99** before proceeding.
- **Simulation in Gazebo**: Runs in a simulated environment using the **Jackal robot** model equipped with a camera.

## Repository Information
This project is built upon the repository: [prob_rob_labs](https://github.com/ihadzic/prob_rob_labs). Additional functionality, including improved uncertainty handling and sensor fusion, was added to enhance decision-making under noise.

## Installation & Setup
### Prerequisites
- **ROS (Robot Operating System) - Noetic/Melodic**
- **Gazebo** for simulation
- **OpenCV** for feature detection
- **C++ (ROS Nodes)**
- **catkin build system**

### Steps to Install & Run
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/bayes-filter-robot.git
   cd bayes-filter-robot
   ```
2. Install dependencies:
   ```bash
   sudo apt-get install ros-noetic-desktop-full
   sudo apt-get install ros-noetic-vision-opencv
   ```
3. Build the package:
   ```bash
   catkin_make
   source devel/setup.bash
   ```
4. Launch the simulation with the vision processor:
   ```bash
   roslaunch prob_rob_labs jackal_and_door.launch run_vision_processor:=true
   ```
5. Run the Bayes filter node:
   ```bash
   rosrun bayes_filter bayes_filter_node_2.cpp
   ```

## How It Works
1. **Feature Extraction**: The robot captures images and extracts visual features.
2. **Sensor Data Processing**: The feature coordinates are processed to determine an average signal level.
3. **Bayesian Inference**: The filter continuously updates the probability of the door being open.
4. **Decision Making**: The robot waits until the probability threshold (**0.99**) is met before proceeding.
5. **Handling Uncertainty**: Introduces robustness against false detections using probability modeling.

## Assignments from Lab
This project expands on the lab assignments by:
- Implementing **Bayesian filtering** for uncertain door detection.
- Estimating real-world probabilities for noisy sensor data.
- Integrating decision-making for an autonomous robot.

## Future Improvements
- **Multi-Sensor Fusion**: Combine LiDAR and camera inputs for improved robustness.
- **Kalman Filter Integration**: Compare performance with Kalman-based state estimation.
- **Real-world Deployment**: Test the filter on a physical robot beyond simulation.

## Credits
This project builds upon [prob_rob_labs](https://github.com/ihadzic/prob_rob_labs) and extends its functionality with a more comprehensive Bayes Filter-based decision-making system.

## License
MIT License.


