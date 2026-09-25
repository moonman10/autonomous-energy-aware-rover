# Autonomous Energy-Aware Delivery Rover

## Project purpose

Design and build a low-voltage autonomous indoor delivery rover that combines electric-vehicle battery systems, embedded controls, automotive-style CAN communication, and ROS 2 robotics. The rover will carry a small payload between defined indoor stations while monitoring its electrical and thermal condition and responding safely to faults.

The project is intended to develop practical skills in EV systems, embedded firmware, motor control, autonomy, PCB design, mechanical packaging, and engineering validation.

## Year 1 definition of done

The Year 1 rover is complete when it can:

- Carry a small payload between two or more known indoor stations.
- Navigate autonomously at low speed using LiDAR, wheel encoders, and ROS 2.
- Use an STM32-based controller to read sensor data, command motors, and execute safety logic.
- Monitor battery voltage, current, temperature, and smart-BMS fault/status data.
- Communicate battery, motor, thermal, mission, and fault status over CAN.
- Log operating data for later analysis.
- Derate motor power or enter a safe stop when battery, thermal, sensor, or communication limits are exceeded.
- Evaluate whether a requested mission is feasible using available energy and basic thermal limits.

## System concept

The rover uses two computing layers. An STM32 handles time-sensitive sensing, motor commands, CAN communication, and safety behavior. A Raspberry Pi runs ROS 2 navigation, LiDAR processing, mission planning, logging, and the operator dashboard.

The propulsion battery is protected by a purchased smart BMS. A custom Battery Supervisory Controller / Vehicle Control Unit PCB will read BMS information, collect pack-level sensor data, communicate with the rover network, and support vehicle-level decisions without replacing the BMS's independent cell protection or balancing functions.

## Major subsystems

1. Mechanical platform: chassis, motor mounts, electronics enclosure, payload tray, sensor mounts, and wiring supports.
2. Energy system: low-voltage battery, purchased smart BMS, fuse, emergency stop, service disconnect, power distribution, DC-DC conversion, and wiring harness.
3. Drive system: two encoder-equipped geared motors, wheels, purchased motor driver, and embedded closed-loop speed control.
4. Embedded control: STM32, sensor interfaces, motor commands, fault state machine, CAN transceiver, and custom control PCB after prototype validation.
5. Robotics/autonomy: Raspberry Pi, ROS 2, 2D LiDAR, IMU, wheel odometry, indoor map, waypoint navigation, and obstacle handling.
6. Battery and thermal supervision: voltage/current/temperature measurement, BMS status acquisition, fan control, power derating, and event logging.
7. Modeling and validation: MATLAB/Simulink energy and thermal predictions correlated with measured rover data.

## Safety boundaries

- Low-voltage propulsion system and low-speed indoor operation only.
- Purchased smart BMS remains the independent battery protection layer.
- Fused power distribution, emergency stop, rated connectors, strain relief, and clear wiring labels are required before powered driving tests.
- Battery charging and testing will follow applicable Cal Poly Racing and campus safety procedures.
- Early motor and autonomy tests will be conducted without a payload and with an accessible manual shutdown method.
- Thermal experiments will use a heater-based mock battery module rather than intentionally overheating lithium-ion cells.

## Year 1 exclusions

The following features are intentionally outside the required Year 1 scope:

- Designing a cell-level BMS from scratch.
- Custom BLDC inverter design.
- Regenerative-braking hardware.
- Autonomous charging dock.
- Liquid-cooling loop.
- Camera-based perception or advanced machine-learning vision.
- High-voltage vehicle operation.

## Planned engineering deliverables

- System block diagram and electrical architecture.
- NX chassis, mounts, enclosure, and harness-routing design files.
- Altium schematic and PCB for the Battery Supervisory Controller / Vehicle Control Unit.
- STM32 firmware, CAN message definitions, ROS 2 nodes, and Python/MATLAB analysis scripts.
- Test plans for battery monitoring, motor control, navigation, thermal behavior, and fault response.
- Logged data sets, model-correlation plots, photos, and a final demonstration video.

## Professional summary

This project develops an autonomous low-voltage delivery rover that integrates EV battery supervision, embedded motor control, CAN communication, thermal-aware power management, and ROS 2 indoor navigation. The platform is designed to demonstrate how a mobile robot can make safe, energy-aware operating decisions based on real battery and system data.
