# Fire Fighting Robot 🚒🔥

A simple **Arduino-based fire fighting robot** developed in **C++** that detects a fire source using flame sensors, moves toward it, and activates a water pump system to extinguish the fire.

The robot uses three flame sensors to identify the direction of the fire, two DC motors for movement, one servo motor to sweep the water stream, and a pump to put out the flames.

This project was created for **learning purposes** to practice embedded programming, sensor reading, actuator control, and robotic decision-making.

---

# Technologies Used

* Arduino / C++
* Flame Sensors
* DC Motors
* Servo Motor
* Water Pump Module
* PWM Control
* Serial Monitor

---

# Project Overview

The robot is designed to:

* Detect fire using three sensors
* Move toward the fire source
* Adjust direction based on left, front, and right sensor readings
* Stop when the fire is very close
* Activate the pump system
* Sweep the servo motor to spread water across the fire area

---

# Components

* Arduino board
* 3 flame sensors
* 2 DC motors
* Motor driver
* 1 servo motor
* 1 water pump
* Chassis
* Battery / power supply
* Jumper wires

---

# Pin Configuration

## Motors

### Right motor
```cpp
#define enA 10
#define in1 9
#define in2 8
```

### Left motor
```cpp
#define enB 5
#define in3 7
#define in4 6
```

## Sensors

```cpp
#define sensor_F A1
#define sensor_E A2
#define sensor_D A0
```

## Other components

```cpp
#define bomba A5
#define SERVO_PIN A4
```

---

# How It Works

The robot continuously reads the three flame sensors:

* **Front sensor** detects fire straight ahead
* **Left sensor** detects fire on the left side
* **Right sensor** detects fire on the right side

Based on the sensor values, the robot follows this logic:

1. If the fire is very close, the robot stops and starts extinguishing
2. If the fire is detected in front but still far, the robot moves forward
3. If the fire is detected on the left, the robot adjusts slightly to the left
4. If the fire is detected on the right, the robot adjusts slightly to the right
5. If no fire is detected, the robot stops

---

# Logic and Behavior

## Fire very close
If one of the sensor readings reaches the close-fire threshold, the robot:

* Stops moving
* Turns on the pump
* Sweeps the servo from side to side
* Tries to extinguish the fire efficiently

## Fire detected ahead
The robot moves forward toward the flame.

## Fire detected on the left
The robot performs a short backward movement and then turns slightly left.

## Fire detected on the right
The robot performs a short backward movement and then turns slightly right.

## No fire detected
The robot remains stopped.

---

# Main Functions

## Movement functions

* `mov_fnt()` → move forward
* `mov_tras()` → move backward
* `mov_dir()` → turn right
* `mov_esq()` → turn left
* `parar()` → stop robot

## Fire suppression function

* `apagarFogo()` → stops the robot, activates the pump, and moves the servo in a sweep pattern

## Direction adjustment functions

* `smallLeft()` → short correction to the left
* `smallRight()` → short correction to the right

## Servo control

* `servoPulse()` → generates PWM pulses to position the servo motor

---

# Code Highlights

* Use of analog sensor reading
* Priority-based decision making
* Manual servo PWM pulse generation
* Motor speed control with PWM
* Efficient fire-extinguishing sweep motion
* Modular movement functions for easy maintenance

---

# Possible Improvements

* Add obstacle detection sensors
* Improve flame detection filtering
* Use a dedicated servo library
* Add autonomous search mode when no fire is detected
* Optimize movement precision
* Add Bluetooth or remote monitoring
* Use a stronger pump and better nozzle control

---

# Learning Goals

This project was created to practice:

* Embedded systems programming
* Arduino pin configuration
* Sensor integration
* Motor control
* Servo motor control
* Robotic movement logic
* Real-time decision making
* Automation concepts

---

# Author

Luis Filippe Reis Nogueira |
Analyce Correa Garcia Angelo |
Pedro Fonseca Martins |
Pedro Martinho
