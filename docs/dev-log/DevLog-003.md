# SolarCore Dev Log #003

**Date:** August 5, 2026

## Repository and Licensing Update

Today we continued organizing the SolarCore GitHub repository and completed the initial open-source licensing setup.

## Work Completed

- Reorganized project documentation into clearer folders
- Moved the V0.1 bill of materials into the hardware directory
- Added the SolarCore V0.1 architecture document
- Added an initial safety test plan
- Added the Apache License 2.0
- Updated the repository structure for future hardware, firmware and test documentation

## Product Research

We also reviewed several commercial water-control and solar-irrigation products.

The research confirmed that irrigation systems commonly use three different water-control configurations:

1. An integrated micro pump
2. An external replaceable pump
3. A valve connected to a pressurized water supply

We also reviewed an automatic water-level controller designed for large AC pumps and residential water tanks.

Although this product serves a different market, it reinforced an important SolarCore principle:

> Users are willing to pay for reliable pump protection, automatic shutdown and reduced manual supervision.

## SolarCore V0.1 Direction

SolarCore V0.1 will continue using an external low-voltage DC pump.

The initial prototype will focus on:

- Safe ESP32 pump control
- Mandatory pump timeout
- Safe startup and reset behavior
- Soil moisture measurement
- Low-water protection
- Battery-voltage monitoring
- Local operation without mandatory cloud services

## Current Repository Structure

```text
SolarCore/
├── README.md
├── LICENSE
├── docs/
│   ├── architecture-v0.1.md
│   ├── Roadmap.md
│   ├── TODO.md
│   └── dev-log/
├── hardware/
│   └── BOM-v0.1.md
└── tests/
    └── test-plan-v0.1.md
```
## Next Milestone

The next technical milestone is to validate the solar charging and battery power system before connecting the pump load.

The test will verify:

- Solar-panel output
- Battery charging
- Stable ESP32 power
- Battery-voltage monitoring
- Transition between solar charging and battery operation
- Initial low-voltage protection thresholds

Pump-control testing will begin after the power system has been verified.
