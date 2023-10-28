# Landmark Detection & Tracking

In this project, we'll explore Simultaneous Localization and Mapping (SLAM) by developing a robot that localizes itself in a 2D grid world and senses landmarks. SLAM is a fundamental problem in robotics, involving the gathering of information from a robot's sensors and motions to construct a map of the world. The project will be divided into several notebooks to understand robot motion, sensor data, and constraint representation.

## Notebook 1: Robot Moving and Sensing

### Robot Class

In this notebook, you will explore the `robot` class that represents the robot in the 2D grid world. The robot has associated uncertainties in both motion and sensors. The class provides methods for moving the robot, but the `sense` function is left unimplemented. The primary goal of this notebook is to understand the robot's movement and how it keeps track of landmarks in the grid world.

### Uncertainty

Uncertainty is a critical aspect of robot motion and sensor data. This notebook explores the challenges posed by uncertainty in motion and how the robot's sensors can be affected. It also provides insights into how to account for measurement noise and a measurement range when the `sense` function is implemented.

## Notebook 2: Omega and Xi, Constraints

### Omega and Xi

In the second notebook, you will dive into the concept of Omega and Xi, which is introduced to implement Graph SLAM. Omega is a square matrix labeled with robot poses and landmarks, and Xi is a vector. These matrices represent constraints between poses and landmarks as numerical relationships. The notebook illustrates how these matrices evolve as robot observations and measurements are made.

### Solving for x

The process of solving for all robot poses is explained using linear algebra, where the vector `mu` is calculated as the product of the inverse of Omega and Xi. The notebook presents examples and solutions to help understand this concept.

### Motion Constraints and Landmarks

Motion constraints and landmark relationships are explored. The process of creating constraints and filling the Omega and Xi matrices is detailed. Landmark sensing and motion constraints are key components in the development of these matrices.

## 2D case

The project will extend the concepts to a 2D scenario, allowing representations of x and y positional values. The notebook offers guidance on how to adapt the Omega and Xi matrices to accommodate both x and y values for poses and landmark locations.

## Notebook 3: Landmark Detection and Tracking

### Project Overview

In the third notebook, we focus on implementing SLAM for a robot that moves and senses in a 2D grid world. SLAM allows localization of the robot and building a map of its environment in real-time. The project addresses computer vision problems as it relies on visual sensing of landmarks.

### Generating an environment

The world has been generated with randomly placed landmarks, robot motion has been created, and sensor measurements have been collected using the `make_data` function. This data will be used as input to the SLAM function. The provided helper functions and the `robot` class were instrumental in creating the data.

### SLAM Inputs

The SLAM function takes in data, the number of time steps (N), the number of landmarks (num_landmarks), the world's size (world_size), motion noise, and measurement noise. The data has been collected as the robot moves and senses in the world.

### Implementing Graph SLAM

In this section, we delved into the actual process of developing the SLAM (Simultaneous Localization and Mapping) functionality. We outlined the steps involved and the adjustments we made to the constraint matrices, Omega and Xi, to account for motion and measurement constraints. It's important to note that the outcome of these computations, represented by the matrix mu, encompassed both the trajectory of the robot and the positions of all landmarks, each defined by their (x, y) coordinates.
