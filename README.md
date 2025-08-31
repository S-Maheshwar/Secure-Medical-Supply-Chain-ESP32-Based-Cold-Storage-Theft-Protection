# Secure Medical Supply Chain: ESP32-Based Cold Storage & Theft Protection

## Overview

This project delivers a **cost-effective, portable, and IoT-enabled cold chain monitoring system** designed for secure transportation of perishable goods and medical supplies. By integrating multiple sensors with an ESP32 microcontroller and Blynk cloud connectivity, the system enables **real-time monitoring, access control, and instant alerts** to ensure the safety and integrity of goods in transit.

---

## Features

- **Real-Time Environmental Monitoring**  
  Continuously tracks temperature and humidity using the DHT11 sensor to maintain optimal storage conditions.

- **Live Location Tracking**  
  Utilizes a GPS (NEO-6M) module to transmit live coordinates and timestamps to the Blynk cloud for end-to-end logistics visibility.

- **Secure RFID Access Control**  
  Employs the MFRC522 RFID module to restrict access to authorized personnel, with a 15-second sensor disable logic after valid entry.

- **Tamper & Theft Detection**  
  Light (LDR) and ultrasonic sensors detect unauthorized box openings and package presence, triggering buzzer alarms and cloud alerts.

- **Remote Cloud Dashboard**  
  All sensor data and device status are visualized in real-time through the Blynk mobile app, enabling remote monitoring and notifications.


---

## System Architecture

| Component         | Functionality                                        |
|-------------------|-----------------------------------------------------|
| ESP32             | Central controller with Wi-Fi and BLE                |
| DHT11             | Temperature & humidity monitoring                    |
| NEO-6M GPS        | Live location tracking                               |
| MFRC522 RFID      | Secure access control                                |
| LDR Module        | Detects box opening/tampering                        |
| HC-SR04 Ultrasonic| Object presence and box status                       |
| Buzzer            | Audible alerts for breaches or abnormal conditions   |
| Blynk Cloud       | Real-time dashboard and mobile notifications         |



## Schematic Diagram

![image](https://github.com/user-attachments/assets/2dc7ff80-0ac4-4dc0-b1b6-17f9e9e16d67)

---

## How It Works

1. **Sensor Initialization**: ESP32 initializes all sensors and connects to the Blynk cloud.
2. **Continuous Monitoring**: Reads temperature, humidity, light, ultrasonic, and GPS data at regular intervals.
3. **Access Control**: RFID scans control access; after valid entry, other sensors are disabled for 15 seconds to avoid false alarms.
4. **Alert Logic**: Unauthorized access or abnormal readings trigger buzzer alarms and instant cloud notifications.
5. **Remote Visualization**: All data and status updates are pushed to the Blynk app for real-time monitoring.



## Dashboard Showcase

![image](https://github.com/user-attachments/assets/f048287e-3028-4241-9ea8-b3535c4fd7c9)

---

## Getting Started

### Hardware Requirements

- ESP32 Development Board
- DHT11 Temperature & Humidity Sensor
- NEO-6M GPS Module
- MFRC522 RFID Module + RFID Tags
- LDR (Light Dependent Resistor) Module
- HC-SR04 Ultrasonic Sensor
- Buzzer
- Breadboard, jumper wires, and power supply

### Software Requirements

- Arduino IDE (with ESP32 board support)
- Blynk IoT Platform (mobile app and authentication token)
- Required Arduino libraries:  
  `WiFi.h`, `BlynkSimpleEsp32.h`, `DHT.h`, `SPI.h`, `MFRC522.h`, `TinyGPS++.h`

---

## Installation & Usage

1. **Clone this repository** and open the main code file in Arduino IDE.
2. **Configure your Wi-Fi credentials and Blynk authentication token** in the code.
3. **Upload the code** to your ESP32 board.
4. **Connect the sensors** as per the schematic.
5. **Monitor and control** the system via the Blynk mobile app.

---

## Results

- Stable and accurate environmental monitoring (±1°C, ±5% RH)
- Reliable live GPS tracking with cloud updates
- Fast and secure RFID-based access control
- Effective tamper detection and alerting
- User-friendly real-time dashboard for remote oversight


## Working Video

https://youtu.be/VkGJgjt75Lw
---

## Troubleshooting & Known Issues

- **Sensor read failures**: Ensure stable power supply and correct wiring.
- **RFID/GPS issues**: Use high-quality tags and place modules away from interference.
- **Connectivity loss**: Implement local logging or reconnection logic for critical events.

## Future Scope
- **Orientation and Shock Detection with MPU6050**: Add an MPU6050 accelerometer to detect box orientation and shock events.

- **SMS Alerts via SIM800L GSM Module**: Integrate a SIM800L GSM module for SMS alerts when Wi-Fi is unavailable.

- **Data Logging to SD Card**: Enable onboard data logging to an SD card for offline record-keeping.
---

## License

This project is open-source and available under the MIT License.
