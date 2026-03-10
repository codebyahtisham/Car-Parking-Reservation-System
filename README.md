# 🚗 Car Parking Reservation System

> A console-based car parking management system built with C++ using Object-Oriented Programming principles including inheritance, composition, and association.

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Language](https://img.shields.io/badge/Language-C++-blue)
![Type](https://img.shields.io/badge/Type-University%20Project-orange)
![Course](https://img.shields.io/badge/Course-Computer%20Programming-purple)

---

## 📌 Overview

This project implements a **Car Parking Reservation System** that allows users to manage parking operations through a password-protected console interface. The system handles car arrival registration, parking slot allocation, expense calculation (with VIP discounts), record viewing, and car departure — all persisted via file handling. Built as a semester project to demonstrate core OOP concepts in C++.

---

## 🎯 Objectives

- Design a parking management system using OOP principles (classes, inheritance, composition, association)
- Implement secure login with masked password input
- Enable CRUD operations for parking records with file-based persistence
- Calculate parking charges with VIP/regular pricing tiers

---

## 🛠️ How It Works

The system follows a menu-driven approach with 5 core operations:

```
====== CAR PARKING RESERVATION SYSTEM ======

  1. Arrival of a Car
  2. Total no of cars Arrived
  3. Total parking charges of all cars with details
  4. Departure of the car
  5. Exit Program

  Select Your Choice ::
```

**Flow:** Login (password-protected) → Main Menu → Perform operations → Data saved to file

---

## 🏗️ Architecture & OOP Concepts

The system is designed around **5 classes** connected through different OOP relationships:

| Class | Role | Relationship |
|-------|------|-------------|
| `LOGIN` | Handles password authentication with masked input | Association with `car` |
| `car` | Core class — stores driver name, car number, hours, time slot | Central entity |
| `DETAILS` | Reads and displays parking records from file | Composition with `car` |
| `CALCULATE` | Computes parking charges (VIP: 20 Rs, Regular: hours × 25 Rs) | Inheritance from `car` |
| `DELETE` | Removes car records from binary file on departure | Association with `car` |

### Class Diagram

```
┌──────────────┐     ┌──────────────────┐     ┌──────────────┐
│    LOGIN     │     │       Car        │     │    DELETE     │
├──────────────┤     ├──────────────────┤     ├──────────────┤
│ - pass: str  │────▶│ + vno: int       │◄────│ + *ptr: car  │
│ - name: char │     │ + count: float   │     ├──────────────┤
├──────────────┤     │ + dname[15]: char│     │ + delete_    │
│ + login():int│     │ + x: char        │     │   record()   │
└──────────────┘     │ + l[50]: char    │     └──────────────┘
                     ├──────────────────┤
                     │ + input(): void  │
                     └───────┬──────────┘
                        ▲    │◆
                        │    │
               ┌────────┘    └────────┐
               │                      │
      ┌────────┴───────┐    ┌────────┴───────┐
      │   CALCULATE    │    │    DETAILS     │
      │  (inherits)    │    │ (composition)  │
      ├────────────────┤    ├────────────────┤
      │ + cal(): void  │    │ + output():void│
      └────────────────┘    └────────────────┘
```

---

## 🧰 Tech Stack

| Category       | Tools                              |
|---------------|-------------------------------------|
| Language       | C++                                |
| Paradigm       | Object-Oriented Programming        |
| IDE            | Code::Blocks                       |
| File Handling  | `fstream` (text + binary files)    |
| Platform       | Windows (uses `conio.h`, `process.h`) |

---

## ✨ Features

- **Password-protected login** — masked input using `_getch()`, with retry on failure
- **Car registration** — stores driver name, car number, stay hours, and time slot
- **Parking availability check** — validates capacity before parking (limit: 50 cars)
- **Record viewing** — displays all parked car details with lot positions
- **Expense calculator** — VIP members pay flat 20 Rs; regular users pay 25 Rs/hour
- **Car departure** — removes record from binary file using temp-file swap method
- **File persistence** — data survives between program runs via `.txt` and `.dat` files

---

## 📁 Repository Structure

```
├── README.md                    # Project documentation
├── Report.pdf                   # Full project report
├── Slides.pdf                   # Presentation slides
└── src/
    └── car_parking_system.cpp   # Complete source code
```

---

## 📄 Documentation

| Document               | Link                                |
|------------------------|-------------------------------------|
| 📘 Full Report (PDF)   | [View Report](./Report.pdf)         |
| 📊 Presentation Slides | [View Slides](./Slides.pdf)         |

---

## 📸 Screenshots

<details>
<summary>Click to view screenshots</summary>

### Login Screen
The system prompts for a password with masked input (shown as `****`).

### Main Menu
Displays all 5 operations in a clean console interface.

### Car Parking
Registers a car by collecting driver name, car number, hours of stay, and time slot.

### Car Position & Details
Shows parking lot position along with all stored details for each car.

### Expense Calculation
Asks VIP status and displays total charges accordingly.

### Car Departure
Removes parking record by car number from the database.

</details>

---

## 👥 Team

| Name              | Role & Contribution                                      |
|-------------------|----------------------------------------------------------|
| Muhammad Ramzan   | Complete project development (all classes except Details) |
| Ahtisham Saleem   | Details class implementation & presentation slides        |

---

## 🏫 Academic Info

| Detail          | Info                          |
|----------------|-------------------------------|
| Course          | Computer Programming (OOP)    |
| Date            | June 2022                     |
| Language        | C++                           |

---

## 📬 Contact

- **Email:** engr.ahtishamsaleem@gmail.com
- **LinkedIn:** [Ahtisham Saleem](https://www.linkedin.com/in/ahtisham-salim)
- **GitHub:** [@codebyahtisham](https://github.com/codebyahtisham)

---

<p align="center">
  ⭐ If you found this project interesting, consider giving it a star!
</p>
