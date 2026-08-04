# SolarCore Dev Log #002

**Date:** August 4, 2026

## Product Research

Today we reviewed several commercial solar-powered irrigation systems and clarified how different products deliver water.

We identified three common configurations:

1. A micro pump integrated inside the controller
2. An external replaceable pump connected to a water tank
3. A valve connected to an existing pressurized water supply

## Architecture Decision

SolarCore V0.1 will use an external DC pump connected to a water tank.

This approach allows us to:

- Replace or upgrade the pump
- Test different flow rates and lift heights
- Measure pump current
- Study dry-run behavior
- Develop an open pump interface
- Keep the system modular and repairable

## Confirmed V0.1 Scope

The first prototype will include:

- One irrigation zone
- ESP32 pump control
- External DC water pump
- MOSFET pump driver
- Solar charging and battery storage
- Soil moisture sensing
- Low-water protection
- Battery-voltage monitoring
- Maximum pump runtime
- Local web control
- Offline safety operation

## Features Postponed

The following features are intentionally postponed:

- Multiple irrigation zones
- LoRa sensor nodes
- MQTT
- Home Assistant
- Native mobile application
- Custom PCB
- Weather prediction
- Solar tracking
- AI plant recognition

## Next Milestone

Verify that the ESP32 can safely start and stop the external pump.

The pump must always stop when the configured maximum runtime is reached.
