# GPS-Denied Navigation System for UAVs

A robust multi-sensor position estimation module designed for autonomous drone operation in GPS-denied environments, developed during a 2-month internship at AVIONAV.

## Overview

This project addresses the critical challenge of maintaining precise navigation when GPS signals are unavailable or compromised. The system combines multiple sensor inputs through an advanced Unscented Kalman Filter (UKF) to provide continuous, accurate position estimation for unmanned aerial vehicles (UAVs).

## Key Features

- **Multi-sensor fusion**: Integrates IMU, aerial cameras, celestial cameras, and GPS data
- **GPS-independent operation**: Maintains navigation accuracy without GPS signals
- **Real-time processing**: Optimized for embedded systems with limited computational resources
- **Outlier detection**: Uses Mahalanobis distance to identify and filter anomalous sensor readings
- **Modular architecture**: Built on ROS2 for scalability and maintainability

## Technical Architecture

<img width="1155" height="411" alt="finalDiag" src="https://github.com/user-attachments/assets/8a98be20-b882-46b6-9a32-02b97fc3342c" />

The system employs a distributed architecture with specialized modules:

- **Data Acquisition Module**: Collects raw sensor data
- **Celestial Navigation Module**: Processes sky imagery for astronomical positioning
- **Aerial Navigation Module**: Analyzes ground imagery for visual odometry
- **Inertial Navigation Module**: Integrates accelerometer and gyroscope data
- **Data Processing Module**: Corrects and adjusts sensor readings based on drone orientation
- **Position Estimation Module**: Fuses all navigation data using UKF
- **Control Module**: Provides flight parameter adjustments based on estimated position

## Hardware Configuration

**Processing Unit**: NVIDIA Jetson Nano
- ARM Cortex-A57 processor
- Maxwell GPU with 128 cores
- Optimized for real-time AI and computer vision tasks

**Sensor Suite**:
- High-precision IMU for motion sensing
- Dual camera system (aerial and celestial vision)
- GPS module for reference positioning
- Wi-Fi communication module

## Algorithm Implementation

### Unscented Kalman Filter (UKF)
The core estimation algorithm uses sigma point sampling to handle non-linear system dynamics without linearization, providing superior accuracy compared to Extended Kalman Filters.

### Security Features
- DDS Security-based node authentication
- Transmission error detection and correction
- Checksum verification for data integrity

### Performance Metrics
- **RMSE**: 0.55
- **MAE**: 0.44
- **Error Standard Deviation**: 0.48

## Technologies Used

- **Framework**: ROS2 (Robot Operating System 2)
- **Programming**: Python with NumPy and SciPy
- **Development Environment**: WSL2 Ubuntu 22.04
- **Hardware Platform**: NVIDIA Jetson Nano
- **Version Control**: Git


## Testing and Validation

Comprehensive simulation testing using:
- Non-linear trajectory generation with noise injection
- 15% outlier data simulation
- Multi-subsystem performance evaluation
- Real-time processing capability verification

<img width="1536" height="754" alt="Figure_1" src="https://github.com/user-attachments/assets/c991d17a-cf66-44aa-ae8e-71d3b553797c" />


## Applications

This navigation system is particularly valuable for:
- Urban canyon navigation where GPS signals are blocked
- Indoor drone operations
- Emergency response scenarios
- Research and exploration missions

## Future Enhancements

- Real-time user interface for monitoring and manual corrections
- Advanced intrusion detection systems
- Adaptive UKF parameter optimization
- Extended sensor integration capabilities
- Machine learning-based anomaly detection

## Technical Achievements

- Successfully implemented multi-sensor data fusion in real-time
- Achieved sub-meter accuracy in GPS-denied environments
- Created a secure, distributed navigation architecture
- Optimized algorithms for embedded system deployment

This project demonstrates the practical application of advanced filtering techniques, sensor fusion, and embedded systems development in solving real-world navigation challenges for autonomous vehicles.
