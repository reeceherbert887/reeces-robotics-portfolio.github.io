---
layout: default
title: Assignment Checklist
permalink: /course-projects/iot-assignment/assignment-checklist/
---

---

# Report (30%)

## Design and Documentation

- [ ] (10) Details of system design clearly explained  
- [ ] (10) Flowchart included (Arduino + ESP32 logic)  
- [ ] (10) System functionality clearly described  

- [ ] (10) Schematic diagram included  
- [ ] (10) Wiring diagram included  

- [ ] (5) CAN protocol explained  
- [ ] (5) Bluetooth (COBS) protocol explained  
- [ ] (5) UART communication explained  
- [ ] (5) MQTT protocol explained  

- [ ] (5) Security risks identified  
- [ ] (5) Security mitigations discussed  

---

# Task 1: Local Functionality (Arduino Uno) – 25%

## CAN Bus

- [x] (3) CAN bus initialised correctly (MCP2515 working)  
- [x] (2) CAN heartbeat sent at correct interval (1–5 Hz)  

### CAN Receive Handling

- [x] (5) 0x10 Button messages decoded correctly  
- [ ] (5) 0x20 LED status decoded correctly  
- [x] (5) 0x30 Fan speed decoded (MSB/LSB combined)  
- [x] (5) 0x40 Temperature decoded (signed, ÷10)  
- [ ] (5) 0xF0 Heartbeat handled  

- [x] (1) Unknown CAN messages ignored safely  

## CAN Send

- [ ] (5) 0x21 Set LED message formatted correctly  
- [ ] (5) 0x22 Multi LED message formatted correctly  
- [x] (5) 0x31 Fan speed message formatted correctly  
- [ ] (5) 0xF0 Heartbeat message formatted correctly  

## Bluetooth

- [ ] (3) Bluetooth connection established  
- [ ] (3) Reconnect on disconnection works  

### Bluetooth Receive

- [ ] (5) COBS decoding implemented correctly  
- [ ] (5) 0x23 LED status handled  
- [ ] (5) 0x40 Temperature handled  
- [ ] (5) 0xF0 Heartbeat handled  

### Bluetooth Send

- [ ] (5) COBS encoding implemented correctly  
- [ ] (5) 0x24 LED control sent correctly  
- [ ] (5) Heartbeat sent correctly  

## LEDs

- [x] (1) Red LED works  
- [x] (1) Green LED works  
- [x] (1) Blue LED works  
- [x] (1) LEDs respond to CAN (0x21 / 0x22)  

---

# Task 2: Remote Functionality (FireBeetle ESP32) – 25%

## Wi-Fi

- [x] (3) Connect to wireless network  
- [x] (2) Reconnect to network on failure  

## MQTT Core

- [x] (2) MQTT heartbeat sent every 2 seconds  

### Publish Topics

- [x] (8) `/student/<id>/heartbeat` correct  
- [x] (8) `/student/<id>/button` correct  
- [x] (8) `/student/<id>/temperature` correct  
- [x] (8) `/student/<id>/speed` correct  

### Subscribe Topics

- [x] (8) `/heartbeat` received and handled  
- [x] (8) `/button` received and handled  
- [x] (8) `/temperature` received and handled  
- [x] (8) `/led` received and handled  

- [x] (8) Irrelevant MQTT messages ignored  

## LEDs

- [x] (2) ESP32 LEDs match Arduino LEDs  

---

# Task 3: System Level Functionality – 20%

- [x] (5) Arduino ↔ ESP32 UART communication working  

## Full Data Flow

- [x] (5) CAN → Arduino → ESP32 → MQTT working  
- [ ] (5) Bluetooth → Arduino → ESP32 → MQTT working  

## Control Flow

- [x] (5) MQTT → ESP32 → Arduino → LEDs working  
- [x] (5) MQTT → ESP32 → Arduino → CAN message working  

## Robustness

- [x] (5) Wi-Fi reconnect works  
- [x] (5) MQTT reconnect works  
- [x] (5) System survives missing CAN nodes  
- [ ] (5) System survives Bluetooth disconnect  

---

# CAN Message Reference

## Sensor → System

| ID   | Purpose      | Key Data |
|------|-------------|---------|
| 0x10 | Button      | Node ID, Button ID |
| 0x20 | LED status  | LED states |
| 0x30 | Fan speed   | MSB + LSB |
| 0x40 | Temperature | Signed 16-bit ÷10 |
| 0xF0 | Heartbeat   | Counter |

## System → Sensor

| ID   | Purpose |
|------|--------|
| 0x21 | Set LED |
| 0x22 | Set multiple LEDs |
| 0x31 | Set fan speed |
| 0xF0 | Heartbeat |

---

# Bluetooth Message Reference

## Receive

| ID   | Purpose |
|------|--------|
| 0x23 | LED status |
| 0x40 | Temperature |
| 0xF0 | Heartbeat |

## Send

| ID   | Purpose |
|------|--------|
| 0x24 | Set LED |
| 0xF0 | Heartbeat |

---

# MQTT Reference

## Publish

- `/student/<id>/heartbeat` → every 2s  
- `/student/<id>/button` → on event  
- `/student/<id>/temperature` → on update  
- `/student/<id>/speed` → every 1s  

## Subscribe

- `/heartbeat`  
- `/button`  
- `/temperature`  
- `/led`  

---

# FINAL COMPLETION CHECK

- [x] All CAN messages handled correctly  
- [ ] All Bluetooth messages handled correctly  
- [x] UART communication stable  
- [x] MQTT topics exactly match specification  
- [ ] LEDs working and synced  
- [ ] System fully robust  
- [ ] Report completed with all required sections  

---
