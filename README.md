
# EPICS PID Controller for Goods Lift

This repository contains an EPICS PID controller implementation for a goods lift, along with associated components and documentation.

## Repository Contents

- `myPID.tgz`: EPICS project for the goods lift (EPICS version: 7.0.1)
- `PID.opi`: CSStudio Operator Interface (HMI) file
- `PID_EPICS_v4_20190718_1622.zap15`: TIA Portal PLC project with the implemented physical model

## Overview

The project implements a PID controller for a goods lift using the EPICS framework. A simple physical model of the goods lift has been developed and integrated into a SIEMENS PLC 1516. Preliminary testing has been performed using a Python program.

The physical model simulates gravity and inertial mass effects while lifting a load. The user can input the mass of the load, which influences the behavior of the model.

### PLC Variables

- `set point (SP)`: Desired altitude of the load
- `Y`: Current position of the load
- `force`: Control value to be sent to the goods lift's engine to reach the set point

In the actual scenario, the physical model is replaced by the real goods lift, and PLC inputs are obtained from field sensors.

### Communication

Communication between EPICS 7.0.1 and PLC 1516 is established using the s7plc driver. The User Interface is created using CSStudio .opi files.

## System Operation

The system operates as follows:

1. PLC reads the current position (`Y`) from the field, retrieved from the internal blocks containing the physical model.
2. A user requests a Set Point (`SP`) using the CODAC CS-Studio user interface.
3. EPICS calculates the required force to be sent to the engine to achieve the desired position. This calculation is performed through a PID control loop, taking inputs `Y` and `SP`.

## Video Recording

A video recording of the CS-Studio screen and its interaction with the EPICS PID controller has been provided. You can view the video [here](https://youtu.be/x-1jIvSAFhs).

## Source Files

The source files for this project are available in this GitHub repository.

For more information or inquiries, feel free to reach out.  
![schema](https://github.com/luciamarock/EPICS-PID-controller-of-a-goods-lift/assets/49598604/5cf20ac3-b812-4feb-8220-6dbc06a32874)

