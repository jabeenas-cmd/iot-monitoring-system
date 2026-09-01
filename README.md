Embedded Microcontroller-Based Industrial Monitoring and Safety Control System Using Secure MQTT with Digital Twin Integration

STM32 + ESP32 + Secure MQTT + Edge Computing + Predictive Maintenance + Node-RED Digital Twin

---

📌 Overview

An embedded industrial monitoring and safety control system that combines microcontroller-based data acquisition, secure MQTT communication, edge computing, predictive maintenance, and real-time visualization.

The system uses STM32 and ESP32 nodes for machine-data acquisition and communication. A Python-based edge server performs data processing, historical trend analysis, machine-health assessment, Random Forest Regressor-based Remaining Useful Life (RUL) estimation, and on-demand health report generation with maintenance recommendations.

Node-RED provides a Digital Twin interface for real-time machine monitoring and visualization.

---

✨ Key Features

- STM32-based embedded data acquisition
- ESP32-based MQTT communication gateway
- UART communication between embedded nodes
- Secure MQTT using TLS 1.2 and mutual TLS (mTLS)
- X.509 certificate-based authentication
- ECC P-256 based PKI
- MQTT topic-level Access Control Lists (ACLs)
- Python-based edge processing
- Historical machine-data and sensor trend analysis
- Multi-sensor abnormality analysis
- Random Forest Regressor-based RUL estimation in days
- On-demand machine health report generation
- Condition-based maintenance recommendations
- MQTT-based control communication
- Node-RED Digital Twin and real-time visualization

---

🔧 Hardware

Microcontrollers

- STM32F407G-DISC1
- ESP32-WROOM-32D

Machine Parameters

The system works with parameters including:

- Temperature
- Humidity
- Voltage
- Current
- Power
- RPM
- Vibration
- Flame
- IR / Motion

Actuators & Outputs

- Motor Driver
- DC Motors
- Relay
- Cooling System / Pump
- Buzzer

---

💻 Software & Technologies

Embedded

- Embedded C / C++
- STM32CubeIDE
- STM32 HAL
- Arduino IDE

Communication

- UART
- MQTT
- Wi-Fi
- Publish/Subscribe Architecture

Security

- TLS 1.2
- Mutual TLS (mTLS)
- X.509 Certificates
- ECC P-256
- OpenSSL
- Mosquitto ACL

Edge Computing & Predictive Maintenance

- Python 3.x
- Paho-MQTT
- Pandas
- Scikit-learn
- Matplotlib
- Random Forest Regressor

Visualization

- Node-RED
- JavaScript
- Node-RED Dashboard

---

📡 MQTT Communication

The system uses an MQTT publish/subscribe architecture for communication between embedded nodes, the edge server, and the visualization layer.
Communication Flow:
IoT Device 1
     ↓
MQTT Publisher
     ↓
Mosquitto MQTT Broker
     ↓
     ├──→ Python Edge Server
     │
     ├──→ Node-RED
     │
     └──→ IoT Device 2
Example MQTT Topics
factory/machine1/data
factory/machine2/data
factory/control

---

🔐 Secure MQTT

MQTT communication is secured using TLS 1.2 and mutual TLS (mTLS).

The certificate infrastructure follows:

Root CA
   │
   ▼
Sub CA
   │
   ▼
Client Certificates

Security Mechanisms

- TLS 1.2 encryption
- Mutual authentication
- X.509 certificates
- ECC P-256 cryptography
- Certificate Authority hierarchy
- MQTT topic-level ACLs

MQTT ACLs restrict clients to authorized publish and subscribe topics.

---

🖥️ Python Edge Server

The Python edge server acts as the local processing and analytics layer.

Main Functions

- MQTT data subscription
- Telemetry processing
- Data logging
- Historical data analysis
- Sensor trend analysis
- Multi-sensor abnormality analysis
- RUL prediction
- Health report generation
- Maintenance recommendations
- Control-command publishing

---

🤖 Predictive Maintenance & RUL

A Random Forest Regressor-based predictive maintenance module is implemented to estimate machine Remaining Useful Life (RUL) in days.

Model Parameters

The model uses machine parameters such as:

- Temperature
- Humidity
- Voltage
- Current
- Power
- RPM
- Vibration

Predictive Maintenance Pipeline

Historical Machine Data
          │
          ▼
    Data Processing
          │
          ▼
  Sensor Trend Analysis
          │
          ▼
Multi-Sensor Abnormality Analysis
          │
          ▼
Random Forest Regressor
          │
          ▼
    Estimated RUL
       (Days)
          │
          ▼
 Machine Health Report
          │
          ▼
Maintenance Recommendation

---

📄 On-Demand Machine Health Reports

The system generates health reports for a selected machine and time period.

Report Includes

- Current machine condition
- Estimated RUL in days
- Historical sensor trends
- Multi-sensor abnormalities
- Condition analysis
- Manual inspection recommendations
- Maintenance recommendations

The analysis considers the current operating condition and historical trends to provide condition-based recommendations.

For example, if the observed degradation trend continues, the report can estimate the expected time toward a critical or failure condition and recommend appropriate inspection or maintenance.

---

📊 Node-RED Digital Twin

Node-RED provides a real-time Digital Twin interface for machine monitoring and visualization.

Dashboard Displays

- Temperature
- Humidity
- Voltage
- Current
- Power
- RPM
- Vibration
- Machine condition
- Historical trends
- Alerts

The Digital Twin and dashboard were developed as a team contribution.

My primary contribution was firmware, embedded communication, edge processing, and predictive-maintenance implementation.

---

⚙️ Control Communication

The system also demonstrates MQTT-based control communication between the edge server and the actuator-side embedded node.
Control Flow:
Python Edge Server
        ↓
MQTT Control Command
        ↓
   IoT Device 2
        ↓
   MCU Control Logic
        ↓
   ┌────┼────┐
   ↓    ↓    ↓
 Motor Buzzer Relay

---

📁 Repository Structure

Industrial-Monitoring-System/
│
├── ESP32_1/
├── ESP32_2/
├── STM32_1/
├── STM32_2/
├── ML_MODEL/
├── server/
├── Node-RED/
├── docs/
└── README.md

Folder Description

Folder| Contents
"ESP32_1/"| ESP32 MQTT publisher/gateway firmware
"ESP32_2/"| ESP32 MQTT subscriber/control firmware
"STM32_1/"| STM32 firmware
"STM32_2/"| STM32 control-side firmware
"ML_MODEL/"| RUL model and predictive-maintenance code
"server/"| Python MQTT server, data processing and report generation
"Node-RED/"| Digital Twin flows and dashboard
"docs/"| Supporting documentation and diagrams

---

⚡ Quick Start

1. Flash Firmware

Open the STM32 projects in STM32CubeIDE and ESP32 projects in Arduino IDE.

Flash the respective firmware to the embedded boards.

---

2. Start MQTT Broker

Configure Mosquitto with the required TLS certificates and ACLs.

Secure MQTT Port: 8883
Protocol: MQTT over TLS 1.2

---

3. Start Python Server

Install the required dependencies:

pip install paho-mqtt pandas scikit-learn matplotlib

Run the server:

python server.py

---

4. Start Node-RED

Import the Node-RED flow from the "Node-RED/" directory and configure the MQTT broker connection.

---

5. Generate Health Report

Provide the required historical machine data to the predictive-maintenance module.

The system performs:

Trend Analysis
      ↓
Abnormality Analysis
      ↓
RUL Estimation
      ↓
Condition Assessment
      ↓
Health Report

---

👩‍💻 My Contribution

My primary contribution was firmware, embedded communication, edge processing, and predictive maintenance, including:

- STM32 firmware development
- Embedded C development
- Data acquisition handling
- UART communication
- ESP32 gateway firmware
- MQTT publish/subscribe communication
- Secure MQTT integration
- MQTT security and certificate configuration
- Python-based machine-data processing
- Random Forest Regressor-based RUL estimation
- Historical sensor trend analysis
- Multi-sensor abnormality analysis
- On-demand machine health report generation
- Condition-based maintenance recommendations
- System integration and debugging

The Node-RED Digital Twin and dashboard were developed by another team member.

---

🚀 Future Enhancements

- Larger real-world machine degradation datasets
- Improved RUL estimation
- Component-level RUL prediction
- Advanced time-series predictive-maintenance models
- Automated maintenance scheduling
- OPC UA / Modbus integration
- SCADA integration
- Cloud-based long-term analytics

---

🎥 Complete Project Files & Demonstration

The complete project files, datasets, documentation, demonstration videos, and supporting materials are available on Google Drive.

Google Drive:
https://drive.google.com/drive/folders/14YIjClBYjJO17Va26r0fXVvXWZ1OA_10?usp=sharing

---

👩‍💻 Author

Jabeena Shaik

B.Tech — Electronics and Communication Engineering

Focus: Embedded Systems | Firmware Development | IoT | Embedded Security | Predictive Maintenance
