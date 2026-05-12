# Flight Architecture

# Overview:
OctoFly uses a Pixhawk-based flight control architecture that stabilizes, navigates and monitors the hexacopter during it's flight operartions 

# The flight system consists of :
sensor fusion,

motor control,

gps navigation, telemetry communication,

autonomous flight capabilities.

The system is made up with 6-motor hexacopter that improves staybility and payload capacity.


# 1. Stabilization System:
Flight Controller
# The drone uses :
Pixhawk 2.4.8 running ArduPilot Firmware.

Pixhawk continuously read the onboard sensors like gyroscope, compass, accelerometer,etc

Usong these sensorsit calculates the roll, yaw, altitude, etc.

Pixhawk dynamically adjusts motor speed through the ESCs to maitain flight stability,.


# Hexacopter Stabilization Principle

The six motors are arranged in alternating CW and CCW directions.

This configuration:

balances torque,

improves yaw stability,

reduces rotational drift.

Motor stabilization is achieved through real-time PWM control signals sent from Pixhawk to the ESCs.



# 2. Autonomous Flight Modes

The drone supports autonomous operation using GPS and ArduPilot flight modes.

GPS System

# The drone uses:

NEO-M8N GPS Module

GPS data enables:

location tracking,

waypoint navigation,

autonomous positioning.

Return-To-Launch (RTL)

If:

signal is lost,

battery becomes critically low,

failsafe activates,

the drone can automatically:

climb to safe altitude,

navigate to launch coordinates,

land safely.

This improves operational safety.

# 3. Telemetry Monitoring System

The drone includes a telemetry communication system using:

433MHz Telemetry Module

Telemetry enables real-time wireless communication between:

Pixhawk,

Ground Control Station (Mission Planner/QGroundControl).

Ground Control Station

Telemetry data can be viewed in:

Mission Planner,

QGroundControl.

# This allows:

live monitoring,

flight tuning,

mission planning,

diagnostics.


# Control Signal Flow :
Receiver Input

      ↓
      
Pixhawk Processing

      ↓
      
Sensor Fusion + Stabilization Logic

      ↓
      
PWM Output Signals

      ↓
      
ESCs

      ↓
      
Motors


# 6. Design Rationale

A hexacopter configuration was selected because it provides:

higher thrust capacity,

improved stability,

motor redundancy,

smoother autonomous flight behavior,

better payload capability compared to quadcopters.
