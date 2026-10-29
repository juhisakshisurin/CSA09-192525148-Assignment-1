# Task 1 – Understand the Problem and Identify the Objects

## Programming in Java – Assignment 1 (CO1)

| **Field** | **Details** |
|---|---|
| Assignment Title | Campus Smart-Parking System |
| Student Name | Juhi Surin |
| Register Number | 192525148 |
| Course | CSA0919 – Programming in Java |
| Task Number | Task 1 |
| Java Version | Java 27 |

---

## 1. Objective

To analyse the Campus Smart-Parking System, identify candidate classes and their responsibilities, define business rules and assumptions, and compare an object-oriented design with a parallel-array approach using time and space complexity.

## 2. Problem Description

The Campus Smart-Parking System manages a multi-level parking facility used by students, staff and visitors. It supports two-wheelers, cars and electric vehicles (EVs).

The system must allocate suitable parking slots, issue unique tickets, record entry times, release slots when vehicles leave, calculate parking fees and validate monthly passes. EV charging fees are charged separately.

## 3. Work Completed

- Analysed the problem and identified system inputs and outputs.
- Identified candidate classes from the nouns in the problem statement and justified their necessity.
- Defined the responsibilities of each candidate class.
- Mapped problem actions to proposed Java methods.
- Established business rules for valid parking operations.
- Documented assumptions about the parking facility.
- Compared object-oriented vehicle representation with parallel arrays.
- Analysed search time and memory requirements using Big-O notation.

## 4. Candidate Classes and Interface

The proposed object-oriented model includes the following classes and interface:

- `Vehicle` – Abstract superclass defining common vehicle behaviour and fee calculation.
- `TwoWheeler`, `Car`, `ElectricCar` – Represent specific vehicle categories.
- `ParkingTicket` – Records ticket details and the parking session.
- `ParkingFacility` – Manages parking slots, allocation, release, active tickets and ticket numbering.
- `ParkingUser`, `Student`, `Staff`, `Visitor` – Represent user categories and parking eligibility.
- `MonthlyPass` – Stores pass validity information and determines whether a pass is valid.
- `FeeCalculator` – Combines applicable parking fees, pass exemptions and charging fees.
- `Chargeable` – Defines the charging capability for eligible vehicles.
- `ParkingApp` – Handles input, invokes the model and displays results.

## 5. Inputs, Outputs, Business Rules and Assumptions

### Inputs and Outputs

The inputs include facility configuration, vehicle registration number and type, user category, entry and exit times, pass information and EV charging consumption.

The outputs include allocated floor and slot, unique ticket number, parking duration, parking fee, charging fee, total amount payable, slot availability and daily collection.

### Business Rules

The analysis establishes the following rules:

- A parking slot cannot hold more than one vehicle.
- A vehicle cannot be parked twice simultaneously.
- Ticket numbers must be unique and must never be reused.
- An unavailable slot or full facility must not result in an invalid allocation.
- Only valid occupied slots may be released.
- Exit time cannot precede entry time, and a ticket can be closed only once.
- Parking fees depend on vehicle type and parking duration.
- Eligible students and staff with valid monthly passes receive free parking.
- EV charging fees are calculated separately.
- Invalid vehicle information must be rejected.

### Assumptions

- The facility configuration remains fixed during execution.
- Any free slot can initially accommodate any vehicle type.
- The allocation policy selects the first available slot, searching from the lowest floor and slot number.
- Floors and slots are indexed from zero inside the program.
- Parking duration is measured in whole minutes, and each started hour is charged in full.
- Ticket numbers start at 1 and increase with each ticket issued.
- Data is maintained in memory, without a database or payment gateway.

## 6. Alternative Concept and Complexity Analysis

The alternative design stores vehicle information in parallel arrays, where corresponding indexes represent the same vehicle. The assignment asks for a comparison with an object-oriented design when finding vehicles by registration number and adding new attributes.

### 6.1 Parallel-Array Code Snippet

The following code illustrates the alternative approach included in the problem-analysis report.

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

- `regNo[]` stores registration numbers.
- `type[]` stores vehicle types.
- `entryTime[]` stores numerical entry timestamps.
- `count` tracks the number of stored vehicles.
- `find()` searches by registration number and returns the matching index or `-1` if no match exists.

This is an illustrative code excerpt, not a standalone Java program. `MAX` and the surrounding class fields must be defined for execution.

### 6.2 Object-Oriented Search Approach

In the object-oriented design, vehicle information is stored in objects referenced through an array such as `Vehicle[] parked`.

```java
for (int i = 0; i < count; i++) {
    if (parked[i].getRegNo().equals(reg))
        return i;
}
return -1;
```

The search examines each vehicle's registration number through `getRegNo()`. This is also an illustrative method excerpt rather than a complete program.

### 6.3 Complexity Comparison

Let `n` represent the number of stored vehicles.

| Criterion | Vehicle Objects | Parallel Arrays |
|---|---|---|
| Worst-case search time | O(n) | O(n) |
| Best-case search time | O(1) | O(1) |
| Space per vehicle | O(1) | O(1) |
| Total space for n vehicles | O(n) | O(n) |
| Adding a new attribute | Update the class and relevant construction or access code | Add another array and maintain matching indexes |
| Extensibility | Supports subclasses and encapsulated behaviour | Requires consistent management of multiple arrays |

Both approaches have the same asymptotic search complexity when using linear search. However, the object-oriented approach groups related data and behaviour, improves type safety and makes it easier to introduce new vehicle categories and attributes.

Exact memory consumption depends on the implementation and JVM. Memory estimates should not be presented as measured results unless actual measurements have been performed.

## 7. Files Included

- `Task1_Problem_Analysis.pdf` – Contains the complete written analysis, inputs and outputs, candidate-class justification, class responsibilities, method mapping, business rules, assumptions, alternative-design code and complexity comparison.
- `README.md` – Documents the scope, analytical approach, illustrative code snippets and result of Task 1.

## 8. Result

The Campus Smart-Parking System was analysed by identifying its inputs and outputs, candidate classes, class responsibilities, methods, business rules and assumptions. The object-oriented approach was compared with the parallel-array alternative in terms of search complexity, storage and extensibility.

## 9. Execution Requirement

Task 1 is primarily a problem-analysis task. The assignment does not specify a separate executable Java program for this task. The code snippets illustrate the alternative data representation and search approaches.

Java implementation and execution evidence will be provided in the task folders for the tasks that explicitly require programming.
