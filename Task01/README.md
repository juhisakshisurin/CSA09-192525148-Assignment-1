# Task 1 – Understand the Problem and Identify the Objects

## Programming in Java – Assignment 1 (CO1)

**Assignment Title:** Campus Smart-Parking System  
**Student Name:** Juhi Surin  
**Register Number:** 192525148

**Course:** CSA0919-Programming in Java  
**Task Number:** Task 1    
**Java Version:** Java 27

---

## 1. Objective

To analyse the Campus Smart-Parking System, identify candidate classes and their responsibilities, define business rules and assumptions, and compare an object-oriented design with a parallel-array approach using time and space complexity.

## 2. Problem Description

The Campus Smart-Parking System manages a multi-level parking facility used by students, staff and visitors. It supports two-wheelers, cars and electric vehicles (EVs).

The system allocates available parking slots, issues unique parking tickets, records entry and exit times, calculates parking fees and checks monthly pass eligibility. EV charging fees are calculated separately.

## 3. Work Completed

- Analysed the problem and identified system inputs and outputs.
- Identified candidate classes from the nouns in the problem statement and justified their purpose.
- Defined the responsibilities of each candidate class.
- Mapped problem actions to proposed Java methods.
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
- `FeeCalculator` – Calculates parking and charging fees.
- `Chargeable` – Defines the charging capability for eligible vehicles.
- `ParkingApp` – Handles input and output.

## 5. Business Rules and Assumptions

The analysis establishes rules for unique ticket numbers, valid slot allocation and release, duplicate registration prevention, valid entry and exit times, parking-fee calculation, monthly pass eligibility and separate EV charging fees.

The facility is assumed to have a fixed configuration during execution. The initial allocation policy selects the first available slot, floors and slots are indexed from zero in the program, and data is stored in memory.

## 6. Alternative Concept and Complexity Analysis

The alternative design stores vehicle information in parallel arrays, such as `regNo[]`, `type[]` and `entryTime[]`, where matching indexes represent the same vehicle.

### 6.1 Parallel-Array Code Snippet

The following Java snippet illustrates the alternative approach included in the problem-analysis report.

```java
String[] regNo = new String[MAX];
String[] type = new String[MAX];
long[] entryTime = new long[MAX];
int count = 0;

int find(String reg) {
    for (int i = 0; i < count; i++) {
        if (regNo[i].equals(reg))
            return i;
    }
    return -1;
}
```

**Explanation:**

- `regNo[]` stores vehicle registration numbers.
- `type[]` stores vehicle types.
- `entryTime[]` stores entry timestamps.
- `count` tracks the number of stored vehicles.
- `find()` searches for a registration number and returns its index, or `-1` if the vehicle is not found.

This is an illustrative code excerpt, not a standalone Java program. `MAX` and the method's surrounding class fields must be defined for execution.

### 6.2 Object-Oriented Search Approach

In the object-oriented design, vehicle data is stored in `Vehicle` objects. The registration number can be searched using each object's getter method.

```java
for (int i = 0; i < count; i++) {
    if (parked[i].getRegNo().equals(reg))
        return i;
}
return -1;
```

Here, `parked` represents an array of `Vehicle` references, and `getRegNo()` retrieves the registration number of each vehicle.

### 6.3 Complexity Comparison

| Criterion | Vehicle objects | Parallel arrays |
|---|---|---|
| Worst-case search time | O(n) | O(n) |
| Best-case search time | O(1) | O(1) |
| Total storage | O(n) | O(n) |
| Adding an attribute | Modify the class and relevant construction or access code | Add another array and maintain matching indexes |
| Extensibility | Supports subclasses and encapsulated behaviour | Requires additional array management and type-based logic |

The object-oriented design is preferred because it groups related data and behaviour, improves type safety and makes the system easier to extend.

Actual memory usage depends on the JVM and implementation.

## 7. Files Included

- `Task1_Problem_Analysis.pdf` – Contains the complete problem analysis, inputs and outputs, candidate classes, responsibilities, method mapping, business rules, assumptions, alternative-design code snippet and complexity comparison.
- `README.md` – Documents the scope, design analysis, code examples and result of Task 1.

## 8. Result

The Campus Smart-Parking System was analysed, candidate classes and methods were identified and justified, business rules and assumptions were documented, and the object-oriented design was compared with the parallel-array alternative.

## 9. Execution Requirement

Task 1 is primarily a problem-analysis task. It does not specify a separate executable Java program. The code snippets in this README illustrate the alternative data representation and search approaches discussed in the report.

Java implementation and execution evidence will be provided for the tasks that explicitly require programming.

---

**Note:** This README documents Task 1 only. The main repository README must contain the overall assignment information and compile-and-run instructions for the Java programs required in subsequent tasks.
