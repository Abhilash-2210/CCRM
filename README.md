# Campus Course & Records Manager (CCRM)

## 1. Project Overview

[cite_start]The Campus Course & Records Manager (CCRM) is a console-based Java application designed for an educational institute to manage students, courses, enrollments, and grades[cite: 4]. [cite_start]It serves as a comprehensive demonstration of core and advanced Java SE features, from Object-Oriented Programming principles to modern I/O and design patterns[cite: 12].

### Key Features

* **Student Management**: Add, list, update, and deactivate students. [cite_start]View student profiles and generate academic transcripts[cite: 17, 19].
* **Course Management**: Create, list, update, and search for courses. [cite_start]Assign instructors and filter courses by department or semester using the Stream API[cite: 21, 23].
* [cite_start]**Enrollment & Grading**: Enroll and unenroll students from courses with business rule validation (e.g., max credits)[cite: 25]. [cite_start]Record marks, compute letter grades, and calculate GPA[cite: 26].
* [cite_start]**File Operations**: Import and export application data (students, courses) from/to CSV-like text files using Java NIO.2[cite: 30, 31].
* [cite_start]**Data Backup**: A utility to back up all data files into a timestamped archive folder[cite: 32].
* [cite_start]**Reports**: Generate simple reports like GPA distribution using the Stream API[cite: 93, 120].

---

## 2. Getting Started

### Prerequisites

* Java Development Kit (JDK) 11 or later
* Eclipse IDE for Java Developers (or any other Java IDE)
* Git for cloning the repository

### How to Run

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Abhilash-2210/CCRM.git](https://github.com/Abhilash-2210/CCRM.git)
    cd CCRM
    ```

2.  **Open in Eclipse IDE:**
    * Open Eclipse.
    * Go to `File` > `Import...`.
    * Select `General` > `Existing Projects into Workspace`.
    * Browse to the cloned repository directory and click `Finish`.

3.  **Run the Application:**
    * Locate the main class at `edu.ccrm.cli.MainMenu` (or your main class).
    * Right-click on the file and select `Run As` > `Java Application`.

4.  **Running with Assertions Enabled:**
    [cite_start]To run the program with assertions enabled (as required by the project), you need to add the `-ea` VM argument[cite: 89, 137].
    * Go to `Run` > `Run Configurations...`.
    * Select your application's run configuration.
    * Go to the `Arguments` tab.
    * In the `VM arguments` box, type `-ea`.
    * Click `Apply`, then `Run`.

---

## 3. Usage & Sample Commands

The application is operated through a console menu. [cite_start]Upon running, you will be presented with the main menu[cite: 35]:

```
==== Campus Course & Records Manager ====
1. Manage Students
2. Manage Courses
3. Manage Enrollment & Grades
4. Import/Export Data
5. Backup & Utilities
6. View Reports
7. Exit
=======================================
Enter your choice:
```

* [cite_start]**Sample Data**: Sample CSV files for importing students and courses are located in the `/test-data` directory[cite: 145]. Use the "Import/Export Data" menu option to load this data into the application.
* [cite_start]**Backup**: Using the "Backup & Utilities" option will create a new folder in the project directory named `backup_[timestamp]` containing copies of the current data files[cite: 32, 124].

---

## 4. Java Core Concepts Explained

### [cite_start]A. Evolution of Java (Timeline) [cite: 42, 132]

* **JDK 1.0 (1996):** The initial release.
* **J2SE 1.2 (1998):** Introduced Collections Framework, Swing, and JIT compiler.
* **J2SE 5.0 (2004):** Major release adding Generics, Enums, Annotations, and Autoboxing.
* **Java SE 8 (2014):** A revolutionary release that introduced Lambda Expressions, the Stream API, and a new Date/Time API.
* **Java SE 11 (2018):** The first Long-Term Support (LTS) release after the new 6-month release cycle.
* **Java SE 17 (2021):** The latest LTS release, bringing features like Sealed Classes and Pattern Matching for `instanceof`.

### [cite_start]B. Java Platforms: ME vs. SE vs. EE [cite: 43, 133, 125]

| Feature           | Java ME (Micro Edition)                             | Java SE (Standard Edition)                            | Java EE (Enterprise Edition)                          |
| ----------------- | --------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| **Primary Use** | Mobile devices, embedded systems, IoT.              | Desktop applications, servers, core Java development. | Large-scale, distributed, enterprise web applications.|
| **Core API** | A subset of the Java SE API with specific libraries for mobile/embedded devices. | The foundational Java platform (includes JDK, JRE, JVM). | Built on top of Java SE, adds APIs for web services, servlets, transactions, etc. |
| **Example** | Old feature phone apps.                             | This CCRM project, Minecraft: Java Edition.           | Banking applications, e-commerce websites.            |

### [cite_start]C. Java Architecture: JDK vs. JRE vs. JVM [cite: 44, 134]

* **JVM (Java Virtual Machine):** An abstract machine that provides the runtime environment in which Java bytecode can be executed. It is platform-dependent and handles memory management, security, and execution.
* **JRE (Java Runtime Environment):** A software package that contains the JVM, Java class libraries, and other components necessary to *run* Java applications. You need the JRE to run a Java program, but not to develop one.
* **JDK (Java Development Kit):** A superset of the JRE. It contains everything in the JRE, plus development tools like the compiler (`javac`), debugger (`jdb`), and archiver (`jar`). You need the JDK to *develop* Java applications.

**Interaction**: `JDK` contains `JRE`, which in turn contains `JVM`. A developer writes code and uses the `JDK` to compile it into bytecode. Any user with `JRE` can then run that bytecode on the `JVM`.

---

## 5. Installation & Setup Guide

### [cite_start]A. JDK Installation on Windows [cite: 45, 135]

1.  Download the JDK installer from the official Oracle website or an alternative like Adoptium.
2.  Run the installer and follow the on-screen instructions.
3.  Set up the `JAVA_HOME` environment variable to point to the JDK installation directory.
4.  Add the JDK's `bin` folder to the `Path` environment variable.
5.  Verify the installation by opening a command prompt and running `java -version` and `javac -version`.

**My Installation Verification:**
[cite_start]`[INSERT YOUR 'java -version' SCREENSHOT HERE]` [cite: 139]

### [cite_start]B. Eclipse IDE Project Setup [cite: 46, 135]

1.  Launch Eclipse IDE.
2.  Create a new Java Project via `File` > `New` > `Java Project`.
3.  Set up the project structure by creating packages as required (e.g., `edu.ccrm.domain`, `edu.ccrm.service`).
4.  Begin creating classes within their respective packages.

**My Eclipse Project Setup:**
[cite_start]`[INSERT YOUR ECLIPSE PROJECT STRUCTURE SCREENSHOT HERE]` [cite: 140]

---

## [cite_start]6. Project Concepts Mapping Table [cite: 136]

This table maps the key Java concepts required by the project to their implementation in the source code.

| Concept / Syllabus Topic                    | Demonstrated In (File/Class/Method)                                                                |
| ------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **OOP - Encapsulation** | `domain/Student.java`, `domain/Course.java` (private fields with public getters/setters)         |
| **OOP - Inheritance** | `domain/Student.java` and `domain/Instructor.java` extend `domain/Person.java`                     |
| **OOP - Abstraction** | `domain/Person.java` (is an abstract class with an abstract `printProfile()` method)             |
| **OOP - Polymorphism** | `MainMenu.java` where a `Person` reference can hold a `Student` or `Instructor` object and invoke the correct `printProfile()` method. Also, overridden `toString()` in domain classes. |
| **Design Pattern - Singleton** | `config/AppConfig.java` (ensures a single instance for application configuration)                   |
| **Design Pattern - Builder** | `domain/Course.java` (contains a static nested `Course.Builder` class)                             |
| **Exception Handling (Custom)** | `util/MaxCreditLimitExceededException.java`, `util/DuplicateEnrollmentException.java`              |
| **Exception Handling (try-catch-finally)** | `io/ImportExportService.java` (handles `IOException`), `cli/MainMenu.java` (handles user input)  |
| **File I/O (NIO.2)** | `io/ImportExportService.java`, `io/BackupService.java` (uses `Path`, `Files`, `Paths`)              |
| **Streams API** | `service/CourseService.java` (for filtering courses), `service/ReportService.java` (for GPA reports) |
| **Date/Time API** | `io/BackupService.java` (for creating timestamped backup folder names), `domain/Student.java` (for registration date) |
| **Interfaces** | `service/Searchable.java` (example interface for searching functionality)                          |
| **Enums (with fields & constructor)** | `domain/Grade.java` (stores grade points), `domain/Semester.java`                                  |
| **Lambdas & Functional Interfaces** | `service/CourseService.java` (used as predicates in `.filter()`), `Collections.sort()` with a lambda comparator. |
| **Recursion** | `io/BackupService.java` (in a method like `calculateDirectorySize(Path path)`)                      |
| **Nested Classes (Static & Inner)** | `domain/Course.Builder` (static nested), An inner class could be used for a custom comparator.      |
| **Arrays & `java.util.Arrays`** | `util/DataUtils.java` (example: using `Arrays.sort()` or `Arrays.binarySearch()`)                   |

---

## 7. Screenshots

### Program Running
[cite_start]`[INSERT SCREENSHOT OF YOUR APPLICATION'S MAIN MENU HERE]` [cite: 141]

### Sample Operation (e.g., Listing Students)
[cite_start]`[INSERT SCREENSHOT OF A SAMPLE OPERATION HERE]` [cite: 141]

### Backup Folder Structure
[cite_start]`[INSERT SCREENSHOT OF THE GENERATED BACKUP FOLDER HERE]` [cite: 142]

---

## 8. Acknowledgements

* This project was completed as a requirement for the "Programming in Java" course.
* Any external libraries or code snippets used are cited in the source code comments where they appear.
