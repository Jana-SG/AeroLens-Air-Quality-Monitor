# 🌿 AeroLens – ESP32 Air Quality Monitoring System

An IoT-based environmental monitoring system built using **ESP32**, multiple gas sensors, temperature & humidity sensing, and cloud integration via **ThingSpeak**.

This system continuously monitors environmental conditions and provides real-time alerts through LEDs, buzzer, LCD display, and cloud logging.

---
## The system monitors:
- LPG Gas (MQ-6)
- Air Quality / Smoke (MQ-135)
- Flame detection
- Temperature & Humidity (DHT11)
  
## And provides
-  Flame detection safety override
-  Traffic light alert system (Green / Yellow / Red)
-  Intelligent buzzer alert patterns
-  Real time 16x2 I2C LCD display 
-  Cloud logging via ThingSpeak
-  WiFi auto-reconnect handling
-  Moving average sensor smoothing

---

## System Architecture

Sensors → ESP32 → Alert Logic (Traffic Light + Buzzer) → LCD Display → ThingSpeak Cloud Logging  

---

## 📷 Hardware Overview
### 🔧 Internal Wiring

<p align="center">
  <img src="images/wiring.jpeg" width="400"/>
</p>

Main Components:
- ESP32 Microcontroller  
- MQ-6 Gas Sensor (LPG)  
- MQ-135 Air Quality Sensor  
- Flame Sensor Module  
- DHT11 Temperature & Humidity Sensor  
- I2C LCD Module  
- Power Regulation Circuit  

---

## 🔌 Hardware Connections

| Component | GPIO |
|------------|-------|
| MQ-6 (AO) | GPIO 34 |
| MQ-135 (AO) | GPIO 35 |
| Flame Sensor (D0) | GPIO 14 |
| DHT11 | GPIO 4 |
| LCD SDA | GPIO 21 |
| LCD SCL | GPIO 22 |
| Green LED | GPIO 25 |
| Yellow LED | GPIO 26 |
| Red LED | GPIO 27 |
| Buzzer | GPIO 32 |

---

### Font Panel

<p align="center">
  <img src="images/enclosure_1.jpeg" width="400"/>
</p>

---

##  Alert Logic

| Status | Condition |
|--------|------------|
| 🟢 GREEN | Safe gas levels |
| 🟡 YELLOW | Moderate gas detected |
| 🔴 RED | High gas, flame detected, or high temperature |

### Overrides
- 🔥 Flame detection forces RED
- 🌡 High temperature forces RED

---

## ☁️ Cloud Integration (ThingSpeak)

Data uploaded every 15 seconds:
- Gas sensor readings
- Temperature
- Humidity
- Flame status
- Overall system level

---

## 📂 Repository Structure

```
/
├── Arduino/
│   └── air_quality_monitor.ino
│
├── Docs/
│   ├── Air Quality Monitoring system Report.pdf
│   ├── Air Quality Monitoring system Report.pptx
│   ├── Air_quality_monitoring_analysis.pdf
│   
├── images/
│    ├── wiring.jpeg
│    ├── enclosure_1.jpeg
│    ├── enclosure_2.jpeg
│    ├── enclosure_3.jpeg
│    ├── enclosure_4.jpeg
│
├── README.md
```

---

## 🛠 Required Libraries

Install in Arduino IDE:

- `DHT`
- `hd44780`
- `WiFi`
- `HTTPClient`

---

## 🔧 Setup Instructions

1. Clone this repository
2. Open the `.ino` file in Arduino IDE
3. Update:
   - WiFi SSID & password
   - ThingSpeak API key
4. Install required libraries
5. Upload to ESP32
6. Power system
7. Monitor Serial output

---


## 📘 Documentation

Full documentation included in `/docs/`:
- 📄 Technical Report
- 📊 Presentation Slides
- 📑 further images of the final product
