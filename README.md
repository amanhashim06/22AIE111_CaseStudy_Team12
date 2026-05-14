# Hostel Management System

**Course:** 22AIE111 — Object Oriented Programming in Java  
**Team ID:** Group 12  
**Branch:** S2 B.Tech CSE-AI  
**Institution:** Amrita School of Computing, Amritapuri Campus

---

## Team Members

| Roll No | Name | Role |
|---|---|---|
| AM.SC.U4AIE25014 | Aman Hashim | Team Lead & SystemManager / Admin |
| AM.SC.U4AIE25055 | Harigovind M | Hostel & Room Logic |
| AM.SC.U4AIE25056 | Harinarayan P | Student & Warden Logic |
| AM.SC.U4AIE25006 | Rahul Krishna R | Allocation & Documentation |

---

## Problem Description

Manual hostel allocation processes lead to record mismatches, allocation conflicts, and delays in accommodation management. There is no centralized digital system to handle student applications, room assignment, occupancy tracking, and record maintenance.

This project implements a **console-based Hostel Management System in Java** that digitizes the entire process — covering student registration, room application, warden allotment, and admin control — while demonstrating all core OOP concepts: Encapsulation, Inheritance, Polymorphism (Overriding & Overloading), Abstraction, Interface, and Final.

---

## Repository Structure

```
22AIE111_CaseStudy_Group12/
│
├── Phase1/
│   └── Phase1_Analysis.pdf          # Problem identification & class mapping
│
├── Phase2/
│   └── Phase2_Design.pdf            # UML diagrams & architectural modelling
│
├── src/
│   ├── RoomOperations.java          # Interface
│   ├── HostelEntity.java            # Abstract class
│   ├── Person.java                  # Base class
│   ├── Student.java                 # extends Person
│   ├── Warden.java                  # extends Person
│   ├── Admin.java                   # Admin management
│   ├── Room.java                    # implements RoomOperations
│   ├── Hostel.java                  # extends HostelEntity, implements RoomOperations
│   ├── Allocation.java              # Room allocation record
│   └── SystemManager.java           # Main class (entry point)
│
├── output/
│   └── (sample output screenshots)
│
└── README.md
```

---

## How to Run the Code

### Prerequisites
- Java JDK 8 or above installed
- A terminal / command prompt

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/<your-username>/22AIE111_CaseStudy_Group12.git
cd 22AIE111_CaseStudy_Group12/src
```

**2. Compile all Java files**
```bash
javac *.java
```

**3. Run the program**
```bash
java SystemManager
```

---

## Sample Input / Output

### Main Menu
```
=== HOSTEL MANAGEMENT SYSTEM ===
1. Student Login
2. Warden Login
3. Admin Login
4. Register New Student
5. Exit
Choose:
```

### Register a New Student
```
Choose: 4
Enter name       : Aman
Enter roll number: S003
Student registered successfully.
```

### Student Applies for a Room
```
Choose: 1
Enter roll number: S003
I am a student.
Welcome, Aman!

--- Student Menu ---
1. Apply for Room
2. Check Status
3. Logout
Choose: 1
Application submitted. Status: pending.
```

### Warden Allots a Room
```
Choose: 2
Enter warden name: warden1
I am a warden.
Welcome, warden1! Managing: Hostel1

--- Warden Menu ---
Choose: 2
Enter student roll number: S003

=== Allocation Receipt ===
Student Roll : S003
Hostel       : Hostel1
Room Number  : 1
==========================
```

### Student Checks Status After Allotment
```
Choose: 2
Status: assigned
Hostel: Hostel1  Room: 1
```

### Admin Views All Students
```
Enter admin ID  : 101
Enter password  : admin123
Welcome, Admin!

--- All Students ---
  Name: Alice  Roll: S001  Status: none      Location: Not assigned
  Name: Bob    Roll: S002  Status: none      Location: Not assigned
  Name: Aman   Roll: S003  Status: assigned  Location: Hostel1, Room 1
```

---

## OOP Concepts Demonstrated

| Concept | Where Used |
|---|---|
| Encapsulation | Private fields + getters/setters in all classes |
| Inheritance | `Student extends Person`, `Warden extends Person`, `Hostel extends HostelEntity` |
| Constructor Chaining | `super(name, id)` in `Student` and `Warden` |
| Method Overriding | `displayRole()` in `Student` and `Warden` |
| Method Overloading | `bookRoom()` and `bookRoom(int)` in `Hostel` |
| Abstract Class | `HostelEntity` with `abstract showInfo()` |
| Interface | `RoomOperations` implemented by `Room` and `Hostel` |
| Final Variable | `final String TYPE = "HOSTEL"` in `HostelEntity` |
| Final Method | `final void printReceipt()` in `Allocation` |

---

## Tools / Technologies Used

| Tool | Purpose |
|---|---|
| Java SE (JDK 8+) | Programming language |
| `java.util.ArrayList` | In-memory storage for all entity lists |
| `java.util.Scanner` | Console input handling |
| VS Code / IntelliJ IDEA | Code editor |
| Git & GitHub | Version control and submission |

---

## Initial Data (Pre-loaded on Startup)

- **Hostels:** Hostel1 (Campus North), Hostel2 (Campus South) — 10 rooms each
- **Wardens:** warden1 → Hostel1, warden2 → Hostel2
- **Students:** Alice (S001), Bob (S002) — status: none
- **Admin:** ID `101`, Password `admin123`
