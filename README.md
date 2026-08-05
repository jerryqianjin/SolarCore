# SolarCore

**Reliable Solar-Powered Garden Automation**

SolarCore is an open hardware project focused on building reliable, solar-powered irrigation and outdoor automation systems for gardens, balconies, greenhouses, and small farms.

Unlike cloud-dependent irrigation products, SolarCore is designed to continue operating safely when Wi-Fi, the Internet, or external servers are unavailable.

## Core Principles

- Solar-powered and suitable for outdoor deployment
- Local-first control
- Safe operation without Internet access
- Automatic irrigation with fail-safe protection
- No mandatory cloud subscription
- Modular and replaceable hardware
- Open interfaces and documentation
- Future Home Assistant and MQTT compatibility

## Current Prototype

**Current phase: SolarCore V0.1 single-zone prototype**

The first prototype will use an ESP32-controlled external DC pump connected to a water tank.

V0.1 is focused on validating the complete power and control chain:

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
Planned V0.1 Functions
One irrigation zone
ESP32 pump control
External replaceable DC pump
MOSFET pump driver
Solar charging and battery storage
Soil moisture sensing
Low-water-level protection
Battery-voltage monitoring
Maximum pump-runtime protection
Local web control
Offline safety operation
Project Status

The initial product architecture, repository structure, and open-source licensing have been established.

The current technical milestone is to validate the solar charging and battery power system before connecting the pump load.

The next test phase will verify:

Solar-panel output voltage
Solar charge-controller operation
Battery charging behavior
Stable ESP32 operation from battery power
Transition between solar charging and battery-only operation
Battery-voltage monitoring
Initial low-voltage protection thresholds

Pump-control testing will begin after the power system has been verified.

Roadmap
Phase 1 — Solar Power and Single-Zone Prototype
Validate solar-panel output
Validate battery charging and power stability
Power the ESP32 from the battery system
Control an external DC pump using the ESP32
Add mandatory pump-runtime protection
Read soil-moisture data
Add low-water and low-battery protection
Complete the first automatic watering cycle
Phase 2 — Reliable Irrigation Controller
Two independent irrigation zones
Latching solenoid valves
Flow monitoring
Water-tank level detection
Local scheduling
Fault logging
Pump and valve safety protection
Phase 3 — Wireless Sensor Network
Solar-powered wireless soil sensor nodes
LoRa communication
Multiple irrigation zones
Home Assistant integration
MQTT support
Phase 4 — Open Outdoor Solar Automation Platform
Irrigation
Mist cooling
Greenhouse ventilation
Outdoor lighting
Water-level management
Rainwater collection
Environmental monitoring
Documentation
V0.1 Architecture
Roadmap
V0.1 Bill of Materials
V0.1 Test Plan
Development Logs
License

SolarCore software and firmware are currently licensed under the Apache License 2.0.

Future hardware design files and project documentation may use additional open licenses appropriate to their content.
