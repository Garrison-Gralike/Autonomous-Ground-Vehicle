# Autonomous-Ground-Vehicle
Autonomous ground vehicle integrating ArduRover flight control, ROS2 Humble perception/autonomy (YOLO detection, A* planning, Pure Pursuit), and skid-steer hardware



## About the Project
This is an autonomous ground robot built as a capstone project. It was developed with a joint Electrical Engineering and Mechanical Engineering team over the course of the year at the FAMU-FSU College of Engineering. The goal was a fully functional autonomous ground vehicle that integrates perception, autonomy, and hardware control into one working stack and can actually navigate on its own. Our mission was to design a robot that could be given a set of waypoints and navigate to the objective on its own, overcoming any adverse terrain or obstacles it may face.

The architecture can be thought of in three layers

# I NEED A PARTS USED SECTION HERE

### Control Layer (Pixhawk 4 / Ardurover)
 Low-level flight control and motor output, communicating over a Herelink air/ground radio link with GPS positioning from an M9N module. This "layer" of the build focused on normal radio communication. It allowed for manual steering and made sure we could connect our herelink and flight controllers to the motors.

### Autonomy Layer (Dell MiniPC / ROS 2 HUMBLE)
This layer hadled all the perception and decision-making. It runs the full ROS2 driver stack (LiDAR, rangefinder, four IP cameras), a YOLOv8 object detection pipeline (INT8 quantized for real-time inference), MAVROS as the bridge to the flight controller, and a C++ navigation stack handling A* path planning, Pure Pursuit control, and occupancy grid mapping.

### Physical Layer
Here we have the body of the robot, along with the all of the components neccesary to make it run. This includes wiring, motors, wheels, and even the PWM signals sent between the flight controller and motor controllers.
