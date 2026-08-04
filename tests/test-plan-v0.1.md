# SolarCore V0.1 Test Plan

## Pump Control Tests

- Pump starts only when commanded
- Pump stops after the maximum runtime
- Pump remains off after ESP32 restart
- Manual pump control also follows the timeout limit

## Water Protection Tests

- Low water level prevents pump startup
- Low water level during operation stops the pump

## Power Tests

- Low battery prevents new irrigation tasks
- Normal operation resumes only after battery voltage recovers

## Sensor Tests

- Soil moisture values can be read
- Disconnected sensor is detected
- Sensor failure cannot cause continuous pumping

## Network Tests

- Wi-Fi loss does not stop local control
- Web page disconnection does not leave the pump running
