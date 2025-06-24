
---

# 🔌 Bluetooth Controlled Home Automation System

[![Platform](https://img.shields.io/badge/Platform-Arduino-blue)](https://www.arduino.cc/)  
[![Tech](https://img.shields.io/badge/Tech-Bluetooth-green)](#)  
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](#)

> 📱 A smart, affordable, and modular solution to control electrical appliances wirelessly using Arduino UNO and a Bluetooth-enabled smartphone.

---

![Project Banner](https://via.placeholder.com/900x200?text=Bluetooth+Home+Automation+System)

## 📋 Table of Contents

- [Overview](#-project-overview)  
- [Features](#-features)  
- [Hardware & Software](#-hardware--software-requirements)  
- [Circuit Diagram](#-circuit-diagram)  
- [Working](#-how-it-works)  
- [Code](#-arduino-code-snippet)  
- [Future Scope](#-future-improvements)  

---

## 🛠 Project Overview

This project automates household appliances by leveraging **Bluetooth-based communication** with an **Arduino UNO**, enabling users to remotely control devices using an Android smartphone. It ensures **ease of access**, especially for elderly and physically challenged individuals.

---

## ✨ Features

- ON/OFF control of home appliances via smartphone  
- Low-cost and beginner-friendly setup  
- Real-time feedback on device state  
- Easily extendable for more appliances or sensors  
- No internet needed (offline automation)

---

## 🔧 Hardware & Software Requirements

### Hardware
- Arduino UNO (ATmega328P)  
- HC-05 Bluetooth Module  
- 1-Channel Relay  
- Smartphone (Android)  
- Power Adapter (12V DC + 220V AC Load)  
- Jumper wires, Breadboard

### Software
- Arduino IDE (v1.6.9+)  
- Arduino BlueControl App (Android)  
- Optional: Fritzing (for circuit schematics)

---

## 🔌 Circuit Diagram

> *📷 Add your circuit image here*
> <p align="center">
  <img src="circuit-diagram.png" width="500" alt="Circuit Diagram"><br>
  <em>Figure 1: Home Automation Circuit Diagram</em>
</p>


---

## 🔁 How It Works

1. The Android app sends serial data (`1` for ON, `2` for OFF) via Bluetooth.
2. HC-05 receives data and sends it to the Arduino.
3. Arduino interprets the data and toggles the digital output.
4. Relay module is triggered, switching the connected device accordingly.

---

## 🧠 Arduino Code Snippet

```cpp
char val;
void setup() {
  pinMode(13, OUTPUT);
  Serial.begin(9600);
  digitalWrite(13, HIGH);
}
void loop() {
  if (Serial.available()) {
    val = Serial.read();
    Serial.println(val);
    if (val == '1') digitalWrite(13, LOW);
    else if (val == '2') digitalWrite(13, HIGH);
  }
  delay(100);
}
```

---

## 🚀 Future Improvements

- Extend to multiple appliances with multi-channel relays  
- Use Wi-Fi (e.g., ESP8266) for IoT-based remote access  
- Add sensors (temperature, motion) for intelligent automation  
- Secure communication with encryption and access control  
- Integrate voice control (Google Assistant or Alexa)

---

