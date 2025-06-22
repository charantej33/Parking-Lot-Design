# Parking-Lot-Design
# 🚗 Smart Multi-Level Parking Lot Management System

## 🧠 Overview

A low-level design and implementation of a **multi-level smart parking system** that automates the parking process in an urban environment. This system efficiently manages spot allocation, tracks vehicles in real-time, and calculates parking fees upon exit.

---

## 📌 Features

- 🔐 **Automatic Parking Spot Allocation**  
  Assigns the most suitable spot based on **vehicle size** (Motorcycle, Car, Bus) and **real-time availability**.

- ⏱️ **Vehicle Check-In and Check-Out**  
  Captures entry and exit timestamps to track parking duration accurately.

- 💰 **Dynamic Fee Calculation**  
  Calculates parking charges based on:
  - Total time parked
  - Vehicle type

- 📡 **Real-Time Availability Tracking**  
  Ensures up-to-date spot availability across **multiple floors**.

- 🤹 **Concurrency Support**  
  Designed to handle simultaneous entries and exits efficiently.

---

## 🧱 Tech Stack

- **Language**: Java (or your language of implementation)
- **Design Pattern**: Object-Oriented Design (OOD)
- **Architecture**: Layered Architecture (LLD Principles)
- **Database**: In-Memory / Relational Database (as applicable)

---

## 🗂️ Data Model Overview

- `ParkingLot`  
  - Contains multiple `Floor`s  
  - Each floor has `ParkingSpot`s (divided by size: Small, Medium, Large)

- `Vehicle`  
  - Type: Motorcycle, Car, Bus  
  - License Number

- `ParkingSpot`  
  - Spot ID  
  - Size  
  - Availability Status

- `ParkingTicket`  
  - Ticket ID  
  - Vehicle Info  
  - Check-In & Check-Out Time  
  - Fee

---

## 🧠 Core Logic

### ✅ Spot Allocation Algorithm
- Checks spot availability from smallest possible level (nearest, smallest-fit)
- Follows First-Come-First-Serve (FCFS) for same-size slots
- Efficient lookup using HashMaps or PriorityQueues

### 💸 Fee Calculation Logic

| Vehicle Type | Rate Per Hour |
|--------------|----------------|
| Motorcycle   | ₹10            |
| Car          | ₹20            |
| Bus          | ₹30            |

Total Fee = `(Exit Time - Entry Time in hours) * Rate Per Hour`

---
