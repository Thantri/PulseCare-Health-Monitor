# PulseCare - Medical Care & Vitality
[cite_start]**"Peace of Mind, Every Beat"** [cite: 2]

[cite_start]PulseCare is a compact, wrist-worn device designed to continuously track vital signs (Heart Rate and SpO2) and bridge the gap between patients and guardians via BLE[cite: 16]. [cite_start]Built for a university semester project, it captures precautionary data and features an emergency SOS system to ensure high-risk patients are never disconnected from medical oversight[cite: 11, 12, 18].

## Project Team
* [cite_start]E/20/418 - Wahalathantri TN [cite: 3]
* [cite_start]E/20/192 - Karunarathne AGSI [cite: 3]
* [cite_start]E/20/440 - Wickramsinghe RT [cite: 4]

## Hardware Architecture
The device is powered by a low-cost, efficient hardware stack:
* [cite_start]**Microcontroller:** ESP32-C3 Super Mini [cite: 28]
* [cite_start]**Sensor:** MAX30100 Pulse Oximeter & Heart Rate Module [cite: 33]
* [cite_start]**Display:** 0.96" OLED (128x64) [cite: 30]
* [cite_start]**Power:** 3.7 V Li-Po ion battery with a TP4056 Charger IC [cite: 128, 130]
* [cite_start]**Inputs:** Push button for screen toggling and SOS activation [cite: 24]

## Software & Technologies
* **Device Firmware:** C++ (Arduino IDE) utilizing `BLEDevice.h` and standard I2C communication.
* **Mobile Application:** Flutter/Dart (Android).
* [cite_start]**Backend:** Cloud Firestore for live data syncing and Guardian alerts[cite: 42, 43].

## Repository Contents
* `/Code`: Contains the complete ESP32-C3 Arduino source code, including BLE setup, OLED rendering, and MAX30100 data processing (with a simulation mode fallback).
* [cite_start]`/Documentation`: Contains the complete project presentation and report (`PulseCare.pdf`), detailing the white-box analysis [cite: 126][cite_start], schematics [cite: 141][cite_start], and clinical thresholds (e.g., Hypoxia warnings for SpO2 below 90% [cite: 107]).

## Mobile Application (APK Download)
> **Note:** The source code for the Flutter application was unfortunately lost due to a local hardware failure. 

However, the final, fully compiled Android Application is available for testing! 
* You can download the **`app-release.apk`** directly from the **[Releases](../../releases)** tab on the right side of this repository. 
* [cite_start]Install this APK on any Android device to experience the Patient and Guardian UI, which connects to the smart gadget via Bluetooth Low Energy (BLE)[cite: 16].

## Key Features
1. [cite_start]**Continuous Monitoring:** Uses Photoplethysmography (PPG) to track real-time BPM and Blood Oxygen[cite: 91].
2. [cite_start]**Emergency SOS:** A long-press (2000ms) on the device button instantly pushes an SOS flag to Firebase via the connected phone, immediately alerting the guardian[cite: 18].
3. **Smart Power Management:** Enters a simulated data phase if the sensor is disconnected to prevent system freezing. 
