# 🌡️ Arduino IoT Smart-Home System for Temperature & Fire Protection

This Arduino-based IoT system monitors and controls temperature and humidity, detects fires, and responds by triggering fans, alarms, and a water pump. The project integrates with Arduino IoT Cloud, allowing remote monitoring and control.

---

## 🧩 Components

- **🌡️ DHT11 Sensor** - Measures temperature & humidity
- **🔥 Flame Sensor** - Detects fires
- **💨 Fan (Motor)** - Cools the environment
- **🚰 Water Pump** - Activates for fire suppression
- **🔔 Buzzer** - Alarm for fire alerts
- **📟 LCD Display** - Shows sensor readings & statuses

---

## ⚙️ Features

- **Real-Time Monitoring**: Tracks temperature & humidity.
- **Automated Fan Control**: Adjusts fan speed based on temperature range.
- **Fire Detection & Suppression**: Detects fire, activates alarm & water pump.
- **IoT Cloud Integration**: Remotely monitor and control through Arduino IoT Cloud.

---

## 🔌 Setup

1. **Hardware Connections**:
   - DHT11 to `A0`
   - Flame Sensor to `2`
   - Fan control (ENA: `8`, IN1: `9`, IN2: `10`)
   - Relay 1 (Fan) to `4`, Relay 2 (Pump) to `5`
   - Buzzer to `6`
   - LCD via I2C

2. **Arduino IoT Cloud Setup**:
   - Define these variables:
     - `temperature` 🌡️
     - `humidity` 💧
     - `fire` 🔥
     - `supression` 🚰
     - `fanspeed` 💨

3. **Libraries**:
   - [DHT](https://github.com/adafruit/DHT-sensor-library)
   - [LiquidCrystal_I2C](https://github.com/johnrickman/LiquidCrystal_I2C)
   - [Arduino IoT Cloud](https://www.arduino.cc/en/IoT/HomePage)

---

## 📈 Cloud Variables

| Variable      | Type                  | Description                              |
|---------------|-----------------------|------------------------------------------|
| 🌡️ `temperature` | CloudTemperatureSensor | Current temperature in °C       |
| 💧 `humidity`    | CloudRelativeHumidity | Humidity percentage             |
| 🔥 `fire`        | bool                  | Fire detection status            |
| 🚰 `supression`  | bool                  | Fire suppression status          |
| 💨 `fanspeed`    | int                   | Fan speed (0-100%)               |

---

## 💻 Code Functions

- **`onTemperatureChange()`**: Actions on temperature update
- **`onHumidityChange()`**: Actions on humidity update
- **`onFanspeedChange()`**: Adjusts motor based on `fanspeed`
- **`onFireChange()`**: Activates alerts if fire is detected
- **`onSupressionChange()`**: Controls water pump for suppression

---

## 📋 Quick Overview

- **Temp Range Control**: Fan speed varies between minTemp (25°C) and maxTemp (35°C).
- **Fire Detected**: Fan off, buzzer and pump on.
- **Display Info**: Shows fan, temperature, and humidity status on LCD.

This IoT project provides real-time monitoring and an automated response to environmental changes, ideal for smart home automation.

---
