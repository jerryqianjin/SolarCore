# SolarCore

**Reliable Solar-Powered Garden Automation**

SolarCore is an open hardware project focused on building a reliable, solar-powered irrigation and outdoor automation system for gardens, balconies, greenhouses, and small farms.

Unlike cloud-dependent irrigation products, SolarCore is designed to continue operating safely when Wi-Fi, the Internet, or external servers are unavailable.

## Core Principles

- Solar-powered and suitable for outdoor deployment
- Local-first control
- Safe operation without Internet access
- Low-power wireless sensor nodes
- Automatic irrigation with fail-safe protection
- No mandatory cloud subscription
- Home Assistant and MQTT compatibility
- Modular and expandable hardware

## Current Prototype

**Current phase: SolarCore V0.1 single-zone prototype**

The first prototype uses an ESP32-controlled external DC pump connected to a water tank.

V0.1 is focused on validating safe and reliable local irrigation before adding multiple zones, wireless sensor networks, or cloud features.

### Planned V0.1 Functions

- One irrigation zone
- ESP32 pump control
- External replaceable DC pump
- MOSFET pump driver
- Solar charging and battery storage
- Soil moisture sensing
- Low-water-level protection
- Battery-voltage monitoring
- Maximum pump-runtime protection
- Local web control
- Offline safety operation

## Project Status

**Current phase: SolarCore V0.1 single-zone prototype**

The initial product architecture, repository structure and open-source licensing have been established.

SolarCore V0.1 will use an ESP32-controlled external DC pump connected to a water tank.

The current technical milestone is to implement safe pump control with:

- Safe startup and reset behavior
- Mandatory maximum runtime
- Low-water protection
- Low-battery lockout
- Local offline operation
  
## Roadmap

### Phase 1 — Solar Prototype

- Control a water pump using ESP32
- Read soil moisture data
- Test solar charging and battery operation
- Complete the first automatic watering cycle

### Phase 2 — Reliable Irrigation Controller

- Two irrigation zones
- Latching solenoid valves
- Flow monitoring
- Water tank level detection
- Local scheduling and safety protection

### Phase 3 — Wireless Sensor Network

- Solar-powered wireless soil sensor nodes
- LoRa communication
- Multiple irrigation zones
- Home Assistant and MQTT integration

### Phase 4 — Outdoor Solar Automation Platform

- Irrigation
- Mist cooling
- Greenhouse ventilation
- Outdoor lighting
- Water level management
- Environmental monitoring

## Documentation

- [V0.1 Architecture](docs/architecture-v0.1.md)
- [Roadmap](docs/Roadmap.md)
- [V0.1 Bill of Materials](hardware/BOM-v0.1.md)
- [V0.1 Test Plan](tests/test-plan-v0.1.md)
- [Development Logs](docs/dev-log/)
## License

SolarCore software and firmware are currently licensed under the Apache License 2.0.

Future hardware design files and project documentation may use additional open licenses appropriate to their content.
