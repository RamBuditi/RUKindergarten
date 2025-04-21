# RUKindergarten
# Kindergarten Classroom Simulation

## Description

This Java program simulates various activities in a kindergarten classroom, including managing student lineups, seating arrangements, and playing musical chairs. It demonstrates the use of fundamental data structures like Singly Linked Lists, Circular Linked Lists, and 2D arrays to manage student data and state transitions.

## Features

*   **Student Lineup:** Reads student information (first name, last name, height) from an input file and adds them to the front of a Singly Linked List (`studentsInLine`), effectively reversing the input order to achieve A-Z sorting based on the input file format.
*   **Seating Chart Creation:** Reads classroom dimensions and seat availability (true/false) from a seating chart file to initialize 2D arrays representing `openSeats` (availability) and `studentsInSeats` (occupancy).
*   **Seating Students:** Moves students one by one from the `studentsInLine` (SLL) to the first available seat in the `studentsInSeats` (2D array).
*   **Musical Chairs Setup:** Transfers seated students from the `studentsInSeats` (2D array) to the end of a Circular Linked List (`musicalChairs`).
*   **Musical Chairs Elimination:**
    *   Randomly selects a student from the `musicalChairs` (CLL) for elimination using `StdRandom.uniform()`.
    *   Removes the eliminated student from the CLL.
    *   Inserts the eliminated student back into the `studentsInLine` (SLL) in ascending alphabetical order (last name, then first name).
    *   Repeats elimination until only one winner remains in the `musicalChairs` CLL.
*   **Seat Winner:** Moves the single remaining student (winner) from the `musicalChairs` (CLL) to the first available seat in the classroom (`studentsInSeats`).

## Technologies Used

*   **Language:** Java
*   **Core Data Structures:**
    *   Singly Linked List (Implemented via `SNode`) - For student lineup.
    *   Circular Linked List (Implemented via `SNode`) - For musical chairs.
    *   2D Arrays (`boolean[][]`, `Student[][]`) - For classroom seating chart and student placement.
*   **Libraries:** Assumes use of Princeton `stdlib` library (`StdIn`, `StdOut`, `StdRandom`).

## How it Works

1.  The simulation starts by reading student data and seating configurations from specified input files.
2.  Students are added to a line (SLL).
3.  The classroom seating grid (2D Array) is initialized.
4.  Students move from the line to available seats.
5.  Students move from seats to the musical chairs circle (CLL).
6.  The musical chairs game eliminates students randomly, placing them back in the line (SLL) sorted alphabetically.
7.  The winner of musical chairs is seated.
8.  Any remaining students in the line are seated.
9.  Output methods can print the state of the line, seats, and musical chairs at various stages.

## Setup and Usage

1.  **Compile:** Compile `Classroom.java`, `Student.java`, `SNode.java` (and any other dependencies) using a Java compiler. Ensure the `stdlib` library (or equivalent) is available in your classpath if required.
    ```bash
    javac Classroom.java Student.java SNode.java
    ```
2.  **Input Files:** Prepare two input files:
    *   `students.txt`: Contains the number of students followed by lines with `firstName lastName height`. Students should be listed in reverse alphabetical order for the `enterClassroom` method to result in A-Z order.
    *   `seatingchart.txt`: Contains the number of rows, number of columns, followed by row lines of `true`/`false` values indicating seat presence.
3.  **Run:** Execute the compiled code, likely involving creating a `Classroom` object and calling its methods (e.g., `enterClassroom`, `createSeats`, `playMusicalChairs`, `printClassroom`). The exact execution command depends on your driver program structure.


   
