
# Task 1 – Understand the Problem and Identify the Objects

## Programming in Java – Assignment 1 (CO1)

**Assignment Title:** Campus Smart-Parking System  
**Student Name:** Juhi Surin  
**Register Number:** [Your Register Number]  
**Course:** Programming in Java  
**Task Number:** Task 1  
**Marks:** 4  
**Java Version:** Java 27

---

## 1. Objective

To analyse the Campus Smart-Parking System, identify candidate classes and their responsibilities, define business rules and assumptions, and compare an object-oriented design with a parallel-array approach using time and space complexity.

## 2. Problem Description

The Campus Smart-Parking System manages a multi-level parking facility used by students, staff and visitors. It supports two-wheelers, cars and electric vehicles (EVs).

The system allocates available parking slots, issues unique parking tickets, records entry and exit times, calculates parking fees and checks monthly pass eligibility. EV charging fees are calculated separately.

## 3. Work Completed

- Analysed the problem and identified the system inputs and outputs.
- Identified candidate classes from the nouns in the problem statement and justified their purpose.
- Defined the responsibilities of each candidate class.
- Mapped actions in the problem statement to proposed Java methods.
- Documented business rules for valid parking operations.
- Stated assumptions about the parking facility.
- Compared object-based vehicle representation with parallel arrays.
- Analysed time and space complexity using Big-O notation.

## 4. Candidate Classes and Interface

The proposed object-oriented model contains the following classes and interface:

- `Vehicle` – Abstract superclass representing common vehicle behaviour.
- `TwoWheeler`, `Car`, `ElectricCar` – Represent specific vehicle categories.
- `ParkingTicket` – Stores parking-session and ticket information.
- `ParkingFacility` – Manages parking slots, allocation, release and active tickets.
- `ParkingUser`, `Student`, `Staff`, `Visitor` – Represent parking user categories.
- `MonthlyPass` – Checks monthly pass validity.
- `FeeCalculator` – Combines the applicable parking fee, pass exemption and charging fee.
- `Chargeable` – Defines the charging capability for eligible vehicles.
- `ParkingApp` – Handles input and output.

## 5. Business Rules and Assumptions

The analysis establishes rules for unique ticket numbers, valid slot allocation and release, duplicate registration prevention, valid entry and exit times, parking-fee calculation, monthly pass eligibility and separate EV charging fees.

The facility is assumed to have a fixed configuration during execution. The initial allocation policy selects the first available slot, floors and slots are indexed from zero in the program, and data is stored in memory.

## 6. Alternative Concept and Complexity Analysis

The alternative design stores vehicle information in parallel arrays, such as `regNo[]`, `type[]` and `entryTime[]`, where matching indexes represent the same vehicle.

Both the object-oriented design and the parallel-array design require **O(n)** time for worst-case linear search by registration number, where `n` is the number of stored vehicles.

Both designs require **O(n)** total storage and **O(1)** storage per vehicle under a fixed-field model. Actual memory usage depends on the implementation and JVM.

The object-oriented design is preferred because it groups related data and behaviour, improves type safety and makes the system easier to extend with new vehicle types and attributes.

## 7. Files Included

- `Task1_Problem_Analysis.pdf` – Contains the problem analysis, candidate classes and responsibilities, business rules, assumptions, alternative-design code snippet and complexity comparison.

## 8. Result

The Campus Smart-Parking System was analysed, candidate classes and methods were identified and justified, business rules and assumptions were documented, and the object-oriented design was compared with the parallel-array alternative.

## 9. Execution Requirement

Task 1 is a problem-analysis task. No separate executable Java program is specified for this task. The alternative parallel-array approach is illustrated through a code snippet in the written report.

Java implementation and execution evidence will be provided for tasks that explicitly require programming.

---

**Note:** This README documents Task 1 only. The main repository README will contain the overall assignment information and the compile-and-run instructions for the Java programs required in subsequent tasks.
