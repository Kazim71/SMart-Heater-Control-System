# IoT Heater Control System with OLED Display & Safety Alerts

## 📌 Overview
This project is an **IoT-based Heater Control System** built using an **ESP32**, **DS18B20 temperature sensor**, **OLED display**, **LED indicators**, and a **buzzer**.  
It monitors temperature, displays real-time data, and controls outputs based on predefined heating and overheat thresholds using a **finite state machine (FSM)**.

---

## 🛠 Features
- **Real-Time Temperature Monitoring** via DS18B20 sensor  
- **OLED Display** for temperature, system state, and progress bar  
- **State Machine Control** with four states:
  - `IDLE` – Temperature below ideal  
  - `HEATING` – Normal heating range  
  - `OVERHEAT` – Over temperature, activates safety alarm  
  - `ERROR` – Sensor failure detected  
- **LED Indicators**:
  - **Red LED** – Overheat warning  
  - **Green LED** – Normal heating  
- **Buzzer Alarm** when overheating  
- **Serial Monitoring** for debugging  
- **Simulation Mode** (heating/cooling cycles for testing without hardware)

---

## 📷 Hardware Components
- **ESP32 Devkit-C V4**
- **DS18B20 Temperature Sensor** (with 4.7kΩ pull-up resistor)
- **0.96" I2C OLED Display (SSD1306)**
- **2 LEDs** (Red & Green) + Resistors
- **Buzzer**
- Breadboard & Jumper Wires

---

## 🔌 Pin Configuration

| Component       | ESP32 Pin | Description           |
|----------------|-----------|-----------------------|
| DS18B20 Data   | GPIO 15   | OneWire Data Line     |
| Heater LED     | GPIO 12   | Red LED               |
| Status LED     | GPIO 13   | Green LED             |
| Buzzer         | GPIO 14   | Piezo Buzzer          |
| OLED SDA       | GPIO 21   | I2C Data              |
| OLED SCL       | GPIO 22   | I2C Clock             |

---

## 📊 System States

| State       | Temperature Range      | LED/Buzzer Behavior |
|-------------|------------------------|----------------------|
| **IDLE**    | `< 48°C`               | All OFF              |
| **HEATING** | `48°C - 100°C`         | Green LED ON         |
| **OVERHEAT**| `> 100°C`              | Red LED + Buzzer ON  |
| **ERROR**   | Sensor not detected    | LEDs flash alternately |

---

## 🖥 OLED Display Output
- **Line 1:** Project title ("Heater")  
- **Line 2:** Current Temperature in °C  
- **Line 3:** System State text  
- **Progress Bar:** Indicates relative heating level  
- **Icon:** Visual status indicator (!, +, ., X)  

---

## 🔧 Libraries Used
Install these Arduino libraries:
- [`OneWire`](https://github.com/PaulStoffregen/OneWire)
- [`DallasTemperature`](https://github.com/milesburton/Arduino-Temperature-Control-Library)
- [`Adafruit_GFX`](https://github.com/adafruit/Adafruit-GFX-Library)
- [`Adafruit_SSD1306`](https://github.com/adafruit/Adafruit_SSD1306)

---

## 🚀 Setup Instructions
1. **Connect Hardware** as per pin configuration above.
2. **Install Required Libraries** in Arduino IDE.
3. **Upload Code** to your ESP32 board.
4. **Open Serial Monitor** at `115200 baud` to view logs.
5. **Observe OLED Display** and LED/buzzer indicators.

---

## 🛡 Safety
- The system is designed to **cut off heating** in case of overheating.  
- Always use proper resistors for LEDs.  
- Do not power heating elements directly from ESP32 pins.

---

## 📷 Circuit Diagram
*(This diagram matches your Wokwi simulation setup)*

![Circuit Diagram](Circuit_Diagram.png)  

---

## 📌 Author
**Mohammad Kazim** – B.Tech ECE (2025)  
Simulation & Testing done in **Wokwi**.

---
