# Hydroponics Core PCB Documentation

## Overview
The Hydroponics Core PCB is the central electronic system responsible for powering, sensing, and controlling the hydroponics unit.  
It ensures stable operation of pumps, sensors, and communication modules, while providing clean and reliable measurements of critical parameters such as **pH, EC (electrical conductivity), temperature, and nutrient delivery**.

This design is based on a tested open-source PCB (rev C) with modifications and integration into our hydroponics system goals.  
Robotics functions are excluded here (they will be used separately for harvesting and cleaning).

---



## Functional Blocks

### 1. **Microcontroller Core (ESP32)**
- The ESP32 acts as the brain of the system.
- Handles sensor acquisition, control logic, and communication (WiFi/Bluetooth).
- Ensures remote monitoring via dashboard or app.

### 2. **Power Regulation (LM2596 Switching Regulator)**
- Converts input supply (typically 12V) into stable 5V and 3.3V rails.
- Supports pumps, sensors, and the ESP32.
- Pulldown resistors prevent floating voltages under light loads.

### 3. **pH & EC Measurement**
- High-impedance input stage ensures accurate readings from pH probes.
- Passive low-pass filters reduce noise caused by long probe wires.
- EC measurement supported via analog signal conditioning.

### 4. **Environmental Sensors**
- Supports temperature sensors and humidity probes.
- Inputs conditioned for stable analog-to-digital conversion.

### 5. **I/O Expansion for Hydroponics**
- Pump and valve driver outputs (to control nutrient dosing and irrigation).
- Sensor headers for pH, EC, water level, and temperature.
- Communication headers for future expansions.

---

## How It Fits Our Hydroponics Project
This PCB is the **core control hub** of our hydroponics system. It ensures:
- **Stable power distribution** to pumps, valves, and sensors.
- **Accurate water quality monitoring** (pH, EC, temperature).
- **Remote monitoring and logging** through ESP32’s wireless connectivity.
- **Modular expansion** for additional dosing pumps or future sensors.

While robots will handle **harvesting and cleaning**, this PCB focuses solely on **system operation and nutrient control**.

---

## Technical Specs
- **Board Type:** 2-layer, 1.6mm FR4, 1 oz copper
- **Microcontroller:** ESP32-WROOM
- **Power Input:** 12V DC
- **Power Rails:** 5V, 3.3V regulated
- **Interfaces:** pH probe (BNC), EC probe, temperature sensors, pump drivers
- **Noise Reduction:** Passive low-pass filter on pH lines
- **Form Factor:** Compact, fits standard hydroponics control enclosures

---

## Conclusion
The Hydroponics Core PCB provides a reliable, noise-optimized, and expandable foundation for running automated hydroponics.  
It integrates sensing, power management, and control into a single board — making it the **heart of our Agriculture 4.0 hydroponics project**.
