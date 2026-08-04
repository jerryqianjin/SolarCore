# SolarCore V0.1 Architecture

## Prototype Objective

SolarCore V0.1 will validate a reliable, single-zone solar irrigation system.

The first prototype will use a water tank and an external DC pump controlled by an ESP32.

The main goal is not to build every planned feature at once. The goal is to verify that a solar-powered irrigation controller can operate locally, safely, and reliably.

## System Overview

SolarCore V0.1 consists of four main parts:

1. Solar power and battery storage
2. ESP32 local controller
3. Sensors and safety inputs
4. External water pump and irrigation tubing

## Water System

```text
Water tank
    ↓
External DC pump
    ↓
Water filter
    ↓
Irrigation tubing
    ↓
Drippers
    ↓
Plants

```

The first prototype uses an external pump because the water tank does not provide enough pressure by itself.

Power and Control System

```text
Solar panel
    ↓
Solar charge controller
    ↓
Battery
    ↓
ESP32 controller
    ↓
MOSFET pump driver
    ↓
External DC pump
```

The battery powers both the controller and the water pump.

The ESP32 does not power the pump directly. It sends a control signal to the MOSFET driver, which switches the pump power.

Water-Source Configurations

Commercial solar irrigation systems commonly use three different configurations.

1. Integrated Pump

A small pump is installed inside the irrigation controller.

This design is compact and easy to install, but the pump may be difficult to replace or upgrade.

2. External Pump

A separate pump is connected to a water tank or rain barrel.

This design is more modular and allows users to choose different pumps based on flow, pressure, tubing length, and elevation.

SolarCore V0.1 will use this configuration.

3. Pressurized Water and Valve

A controller opens and closes a valve connected to a household tap or another pressurized water supply.

This design does not require a pump because the water supply already provides pressure.

A future SolarCore Home version may support this configuration.

Why SolarCore V0.1 Uses an External Pump

An external pump allows us to:

Replace or upgrade the pump
Test different flow rates
Test different lift heights
Measure pump current
Observe dry-run behavior
Add overcurrent protection
Add timeout protection
Keep the system modular and repairable

The pump should remain replaceable instead of being permanently built into the controller.

V0.1 Hardware Components

The first prototype will use:

ESP32 development board
External DC water pump
MOSFET pump driver
Solar panel
Solar charge controller
Battery
Capacitive soil moisture sensor
Low-water-level switch
Battery-voltage measurement circuit
Water filter
Irrigation tubing
Drippers
Sensor Inputs

SolarCore V0.1 will monitor:

Soil Moisture

Used to determine whether the soil is dry enough to allow irrigation.

The first version will focus on calibrated raw values and moisture trends instead of claiming a perfectly accurate percentage.

Water Tank Level

A low-water-level switch prevents the pump from running when the tank is empty or nearly empty.

Battery Voltage

Battery voltage is monitored to prevent irrigation when the remaining energy is too low.

Local Control Functions

The ESP32 will be responsible for:

Reading sensor data
Starting and stopping the pump
Manual irrigation control
Automatic irrigation decisions
Maximum pump runtime
Low-water shutdown
Low-battery lockout
Safe startup behavior
Safe reset behavior
Local web control
Basic event logging

All critical irrigation and safety functions must run locally.

V0.1 Irrigation Logic

Irrigation may start only when all required conditions are satisfied:

```text

Automatic mode is enabled
+ Soil is below the dry threshold
+ Water tank level is safe
+ Battery voltage is safe
+ No active fault exists
= Pump may start
```

The pump must stop when any stop condition occurs:

```text

Maximum runtime reached
OR low water detected
OR low battery detected
OR sensor fault detected
OR manual stop requested
OR controller enters a fault state
= Pump stops
```

Safety Requirements

SolarCore V0.1 must follow these safety rules:

The pump must remain off after startup.
The pump must remain off after an ESP32 reset.
Every pump activation must have a maximum runtime.
Manual pump operation must also have a maximum runtime.
Low water level must prevent the pump from starting.
Low water level detected during operation must stop the pump.
Low battery voltage must prevent new irrigation tasks.
Sensor failure must never cause continuous pumping.
Wi-Fi failure must not disable safety protection.
Internet failure must not affect local irrigation control.
The system must return to a safe state after a software error.
V0.1 Scope

The first prototype includes:

One irrigation zone
One external pump
One soil moisture input
One low-water-level input
Battery-voltage monitoring
Local automatic irrigation
Manual pump control
Maximum runtime protection
Local web interface
Offline operation
Features Not Included in V0.1

The following features are intentionally postponed:

Multiple irrigation zones
LoRa wireless sensor nodes
MQTT
Home Assistant integration
Native mobile application
Weather forecasting
Flow meter
Custom PCB
Solar tracking
AI plant recognition
Future Expansion

Later SolarCore versions may support:

Integrated micro-pump modules
External high-flow pumps
Pressurized household water
Solenoid valves
Latching solenoid valves
Multiple irrigation zones
Flow monitoring
Water-pressure monitoring
Wireless soil sensor nodes
MQTT
Home Assistant
Rainwater collection
Greenhouse ventilation
Outdoor lighting
