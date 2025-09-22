Engineering materials
====

This repository contains engineering materials of a self-driven vehicle's model participating in the WRO Future Engineers competition in the season 2024.

## Content
this is information about our participate in WRO , there is pictures , videos , some resources for our design and the code . 

* `Obstacles Challenge` contains the video of Obstacles Challenge and the link of the video on our team's YouTube Channel 
* `t-photos` contains 2 photos of the team (an official one and one funny photo with all team members)
* `v-photos` contains 6 photos of the vehicle (from every side, from top and bottom)
* `video` contains the video of Open Challenge and the link of the video on our team's YouTube Channel 
* `schemes` contains one or several schematic diagrams in form of JPEG, PNG or PDF of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other.
* `src` contains code of control software for all components which were programmed to participate in the competition
* `models` is for the files for models used by 3D printers, laser cutting machines and CNC machines to produce the vehicle elements. If there is nothing to add to this location, the directory can be removed.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It may include documentation how to connect to a SBC/SBM and upload files there, datasets, hardware specifications, communication protocols descriptions etc. If there is nothing to add to this location, the directory can be removed.

## Introduction

Welcome to the WRO Future Engineers competition! In this exciting challenge, participants aged 15 to 19 will design and build a self-driving vehicle model. The goal is to create a car equipped with electromechanical components that can autonomously navigate a track while avoiding obstacles. Let's delve into the key aspects of our project.

## The car's design features include:

- **Ackermann steering**: It is a geometric arrangement in the car's steering system that addresses the issue of wheels tracing different radii circles on turns.
- **Gearbox**: This component converts the brushless motor's speed into torque.
- **Wheels and gears**: Designed using SolidWorks and produced through 3D printing.

These elements combine to ensure excellent maneuverability and performance on the road. The meticulous design process, from Ackermann steering to gearbox conversion, reflects a dedication to efficiency and innovation. The utilization of SolidWorks for the design of wheels and gears, along with advanced 3D printing, results in a product that pushes the boundaries of automotive engineering. Each part working in unison provides a driving experience that is not only smooth and controlled but also demonstrates the capabilities of modern manufacturing techniques.

## Components Used

### 1. Ultra Sonic Sensors

- **Purpose**: To measure distances by emitting ultrasonic sound waves and measuring the time it takes for the waves to reflect back after hitting an object.

- **define the sensors**:
- ----------------------
```
#define TRIGGER_PIN_R1 52  // first right sensor 
#define ECHO_PIN_R1 A14

#define TRIGGER_PIN_L1 20  // first left sensor 
#define ECHO_PIN_L1 A0

#define TRIGGER_PIN_R2 50  // second right sensor 
#define ECHO_PIN_R2 A13

#define TRIGGER_PIN_L2 40 //// second left sensor 
#define ECHO_PIN_L2 A15

#define TRIGGER_PIN_F 46   //// front sensor 
#define ECHO_PIN_F A11
```
- **Functions**:
    - `sensor()`: it measure distancees and assigning values ​​to variables.
L1 = sonar_L1.ping_cm(); //read the distance from all ultra sonic sensors
L2 = sonar_L2.ping_cm();
R1 = sonar_R1.ping_cm();
R2 = sonar_R2.ping_cm();
F = sonar_F.ping_cm();

### 2. Gyro Sensor (Motion Processing Unit - MPU)

- **Purpose**: Provides information about orientation, acceleration, and rotation.
- **Functions**:
    - `mpu_setup()`: Configures the MPU sensor during setup.
    - `mpu_loop()`: Processes data from the MPU sensor in the main loop.
    - `calibrateGyro()`: Calibrates the gyro sensor to ensure accurate readings.
    - `P_id_gyro()`: Applies a PID controller using gyro data for stabilization.

### 3. Servo Motor
- There is some commands to configures the servo motor during setup.
- in the loop the servo will do it's assignment to turn right or left .

### 4. Brushless Motor
- There is some commands to configures the brushless motor during setup.

## Code Structure

1. **Libraries**: Import necessary libraries (e.g., Arduino, sensor libraries).
2. **Objects**: Define any objects (e.g., motor objects).
3. **Variables**: Declare global variables (e.g., sensor readings, motor speeds).
4. **Functions**:
    - Implement functions for each component (e.g., gyro, ultrasonic).
    - Organize code for readability and modularity.
5. **void setup()**:
    - Initialize components (e.g., sensors, motors).
    - Set initial conditions.
6. **void loop()**:
    - Continuously read sensor data.
    - Apply control algorithms (e.g., PID) for autonomous navigation.
    - Avoid obstacles based on sensor inputs.
