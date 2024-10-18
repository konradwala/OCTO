# OCTO

# 6-Axis Robotic Arm

## Project Overview

This project involves the design, construction, and control of a 6-axis robotic arm primarily intended for demonstration purposes. The robot is designed to perform precise movements rather than lifting heavy objects. It is built using 3D-printed parts and driven by stepper motors, all controlled through a Raspberry Pi with communication over a CAN bus network.

### Key Features:
- 6 degrees of freedom.
- Built with 3D-printed components.
- Stepper motors controlled via custom driver boards.
- Real-time control via a Raspberry Pi with ROS (Robot Operating System).
- Precision magnetic angle sensors for feedback on each joint.
- Portable design with a 20 cm reach from the center of the base, operating over a working area of 25 cm x 17 cm.

## Mechanical Design

- **Structure**: The robotic arm is composed of four main components: a carousel (base), rocker (shoulder), jib (elbow), and gripper.
- **Motors**:
  - 3 x **NEMA 17** stepper motors (0.5A per coil).
  - 3 x **NEMA 11 JK28HS32-0674** stepper motors (0.67A per coil, 3.8V).
- **Transmission**: Stepper motors are coupled with timing belt mechanisms, using a 1:6 gear reduction for smoother and more precise movements.
- **Material**: The arm's parts are printed using a **Bambu Lab A1** 3D printer.

## Electronics

- **Custom Stepper Drivers**: Each stepper motor is controlled via custom PCBs based on the following components:
  - **ATmega328P** as the microcontroller.
  - **A4988** stepper motor drivers.
  - **AS5600** magnetic angle sensors for positional feedback.
  - **MCP2515** and **MCP2551** for CAN communication.
- **Power Supply**:
  - 12V for the stepper motors.
  - 5V for the microcontroller and other ICs.
  - Power is distributed across the six PCBs in a daisy-chained manner, ensuring each board receives both 5V and 12V.
- **Communication**: The PCBs communicate over the CAN bus with the Raspberry Pi acting as the master controller.

## Software

- **Control System**: The robotic arm is controlled via **Raspberry Pi 5** running **ROS (Robot Operating System)** on Ubuntu. The control software communicates with the stepper drivers over the CAN bus to send position commands and receive feedback.
- **Kinematic Modeling**: The arm's kinematics are modeled using Python and the **Robotics Toolbox** library. The live 3D model of the robot is generated and controlled using sliders:
  - 6 sliders for the individual axes.
  - 1 slider for the carousel height.
  - 3 sliders for the lengths of the arm's sections.
  
## Current Status

- **Mechanical**:
  - The first two degrees of freedom (carousel and rocker) are fully assembled, and the third is under construction.
  - The remaining three degrees of freedom are expected to be completed by early November.
- **Electronics**:
  - Six custom driver PCBs are designed and connected in series using power lines (5V, 12V) and CAN lines.
  - Stepper motors and driver boards are being tested with prototype boards before final implementation.
  
## Future Work

- Finalizing the assembly of all six degrees of freedom.
- Completing and testing the full electronic control system.
- Improving the kinematic model and integrating more advanced motion control algorithms.

## Repository Structure

