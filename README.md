# ⚡ Smart Energy Conservation System (ESP32 + IoT)

An intelligent IoT-based power control system that automatically manages AC electrical loads based on human presence detection and real-time energy monitoring. Built to reduce energy wastage caused by idle appliances and improve awareness of power consumption.

---

## 🚀 Core Idea

The system dynamically controls an AC load (bulb/appliance) using motion detection while continuously monitoring electrical parameters (V, I, P, E) and streaming them to a cloud dashboard.

It combines:
- Real-world automation (PIR-based presence detection)
- Power analytics (INA219 sensor)
- Cloud IoT monitoring (Thinger.io)
- Safe relay-based AC switching

---

## ⚙️ System Architecture


[PIR Sensor] ─┐
├──> ESP32 ───> Relay Module ───> AC Load
[INA219] ─┘ │
└──> WiFi ───> Thinger.io Cloud Dashboard


---

## 🧠 Working Logic

- PIR sensor detects motion → triggers state change
- ESP32 processes signal using **non-blocking millis() logic**
- Relay toggles AC load based on occupancy logic
- INA219 continuously measures:
  - Voltage
  - Current
  - Power
  - Energy consumption
- Data is pushed to cloud every few seconds

### Control Behavior
- Motion detected → Load ON / maintained ON
- No motion for threshold time → Load OFF
- Random trigger noise handled using debounce + stability delay

---

## 🧩 Features

- 🔄 Automatic load switching based on motion
- 📊 Live energy monitoring (V, I, P, Wh)
- ☁️ Cloud dashboard integration (Thinger.io)
- ⚡ Stable non-blocking firmware (millis-based)
- 🧠 Noise-resistant PIR handling
- 🔌 Multi-relay support (4-channel module ready)
- 💰 Ultra low-cost implementation (~₹500)

---

## 🛠️ Hardware Used

- ESP32 Dev Board
- PIR Motion Sensor (HC-SR501)
- INA219 Current/Voltage Sensor (I2C)
- 4-Channel Relay Module
- AC Bulb / Load

---

## 💻 Software Stack

- Arduino Framework (C/C++)
- Thinger.io IoT Platform
- I2C Communication Protocol
- WiFi Connectivity (ESP32)
- IoTMP Telemetry Protocol

---

## 🧪 Key Engineering Concepts

- Embedded systems timing using `millis()`
- Sensor fusion (motion + electrical telemetry)
- Relay isolation for AC switching
- Cloud-based IoT telemetry streaming
- Real-time system state management

---

## 🛡️ Safety & Precautions (IMPORTANT)

⚠️ This project interfaces with 230V AC mains.

- Use proper electrical insulation for relay wiring  
- Never touch live AC terminals during operation  
- Enclose relay module in insulated casing  
- Ensure proper grounding of AC load  
- Do NOT test AC wiring on breadboard  
- Always disconnect power before modification  

This project is for **educational and prototyping purposes only**.

---

## 📡 IoT Dashboard

The system streams live data to Thinger.io dashboard:
- Voltage (V)
- Current (A)
- Power (W)
- Energy consumption (Wh)

Update interval: ~3 seconds (configurable)

---

## ⚠️ Challenges Faced

- Random relay triggering due to noise coupling
- PIR false positives in unstable environments
- Timing drift in blocking code (fixed using millis logic)
- I2C instability with INA219 under load switching
- Debugging AC switching safety issues

---

## 📈 Outcome

A fully functional smart automation system that:
- Reduces unnecessary energy usage
- Provides real-time electrical insights
- Demonstrates real-world embedded + IoT integration

---

## 🧠 What This Project Demonstrates

- Real-world embedded systems engineering
- IoT cloud integration pipeline
- Hardware-software co-design
- Debugging under electrical noise conditions
- Practical AC load control system design

---

## 👨‍💻 Author

Built by an ECE undergraduate exploring real-world embedded systems, IoT, and automation.

---

## 📌 Future Improvements

- ML-based occupancy prediction
- Mobile app control panel
- OTA firmware updates
- Energy billing estimation module
- Multi-room expansion system

---

## ⭐ If you like this project

Star the repo and feel free to fork it for learning or improvement.
