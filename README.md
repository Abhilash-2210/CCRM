
# Campus Course & Records Manager (CCRM)
Name: Abhilash Singh

Registration Number: 24BCE10706

Course: Programming in Java

Institution: Vellore Institute of Technology (VIT)

## 1. Project Overview

The Campus Course & Records Manager (CCRM) is a console-based Java application designed for an educational institute to manage students, courses, enrollments, and grades. It serves as a comprehensive demonstration of core and advanced Java SE features, from Object-Oriented Programming principles to modern I/O and design patterns.

### Key Features

* **Student Management**: Add, list, update, and deactivate students. View student profiles and generate academic transcripts.
* **Course Management**: Create, list, update, and search for courses. Assign instructors and filter courses by department or semester using the Stream API.
* **Enrollment & Grading**: Enroll and unenroll students from courses with business rule validation (e.g., max credits). Record marks, compute letter grades, and calculate GPA.
* **File Operations**: Import and export application data (students, courses) from/to CSV-like text files using Java NIO.2.
* **Data Backup**: A utility to back up all data files into a timestamped archive folder.
* **Reports**: Generate simple reports like GPA distribution using the Stream API.

---

## 2. Getting Started

### Prerequisites

* Java Development Kit (JDK) 11 or later
* Eclipse IDE for Java Developers (or any other Java IDE)
* Git for cloning the repository

### How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Abhilash-2210/CCRM.git 
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
    To run the program with assertions enabled (as required by the project), you need to add the `-ea` VM argument.
    * Go to `Run` > `Run Configurations...`.
    * Select your application's run configuration.
    * Go to the `Arguments` tab.
    * In the `VM arguments` box, type `-ea`.
    * Click `Apply`, then `Run`.

---

## 3. Usage & Sample Commands

The application is operated through a console menu. [cite_start]Upon running, you will be presented with the main menu:

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

* **Sample Data**: Sample CSV files for importing students and courses are located in the `/test-data` directory. Use the "Import/Export Data" menu option to load this data into the application.
* **Backup**: Using the "Backup & Utilities" option will create a new folder in the project directory named `backup_[timestamp]` containing copies of the current data files.

---

## 4. Java Core Concepts Explained

###  Evolution of Java (Timeline)

* **JDK 1.0 (1996):** The initial release.
* **J2SE 1.2 (1998):** Introduced Collections Framework, Swing, and JIT compiler.
* **J2SE 5.0 (2004):** Major release adding Generics, Enums, Annotations, and Autoboxing.
* **Java SE 8 (2014):** A revolutionary release that introduced Lambda Expressions, the Stream API, and a new Date/Time API.
* **Java SE 11 (2018):** The first Long-Term Support (LTS) release after the new 6-month release cycle.
* **Java SE 17 (2021):** The latest LTS release, bringing features like Sealed Classes and Pattern Matching for `instanceof`.

###  Java Platforms: ME vs. SE vs. EE 

| Feature           | Java ME (Micro Edition)                             | Java SE (Standard Edition)                            | Java EE (Enterprise Edition)                          |
| ----------------- | --------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| **Primary Use** | Mobile devices, embedded systems, IoT.              | Desktop applications, servers, core Java development. | Large-scale, distributed, enterprise web applications.|
| **Core API** | A subset of the Java SE API with specific libraries for mobile/embedded devices. | The foundational Java platform (includes JDK, JRE, JVM). | Built on top of Java SE, adds APIs for web services, servlets, transactions, etc. |
| **Example** | Old feature phone apps.                             | This CCRM project, Minecraft: Java Edition.           | Banking applications, e-commerce websites.            |

### Java Architecture: JDK vs. JRE vs. JVM 

* **JVM (Java Virtual Machine):** An abstract machine that provides the runtime environment in which Java bytecode can be executed. It is platform-dependent and handles memory management, security, and execution.
* **JRE (Java Runtime Environment):** A software package that contains the JVM, Java class libraries, and other components necessary to *run* Java applications. You need the JRE to run a Java program, but not to develop one.
* **JDK (Java Development Kit):** A superset of the JRE. It contains everything in the JRE, plus development tools like the compiler (`javac`), debugger (`jdb`), and archiver (`jar`). You need the JDK to *develop* Java applications.

**Interaction**: `JDK` contains `JRE`, which in turn contains `JVM`. A developer writes code and uses the `JDK` to compile it into bytecode. Any user with `JRE` can then run that bytecode on the `JVM`.

---

## 5. Installation & Setup Guide

### JDK Installation on Windows 

1.  Download the JDK installer from the official Oracle website or an alternative like Adoptium.
2.  Run the installer and follow the on-screen instructions.
3.  Set up the `JAVA_HOME` environment variable to point to the JDK installation directory.
4.  Add the JDK's `bin` folder to the `Path` environment variable.
5.  Verify the installation by opening a command prompt and running `java -version` and `javac -version`.

**My Installation Verification:**
`[INSERT YOUR 'java -version' SCREENSHOT HERE]` 

### Eclipse IDE Project Setup 

1.  Launch Eclipse IDE.
2.  Create a new Java Project via `File` > `New` > `Java Project`.
3.  Set up the project structure by creating packages as required (e.g., `edu.ccrm.domain`, `edu.ccrm.service`).
4.  Begin creating classes within their respective packages.

**My Eclipse Project Setup:**
[INSERT YOUR ECLIPSE PROJECT STRUCTURE SCREENSHOT HERE]` 

---

## Project Concepts Mapping Table 

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

### Java Installation Verification
<img width="1089" height="193" alt="Java Installation Verification" src="https://github.com/user-attachments/assets/1250a739-6050-4157-8f92-556626036482" />


### Eclipse Import
<img width="795" height="873" alt="492903086-4baa52a1-b750-4dde-838c-eb05ff2c0e61" src="https://github.com/user-attachments/assets/89e0364f-23a0-401d-ad2e-f2a77e36ee18" />


### Project Structure
<img width="486" height="607" alt="Project Structure" src="https://github.com/user-attachments/assets/14bc22eb-2858-492d-93f1-715f3d0d926f" />


### Student Management
<img width="663" height="514" alt="image" src="https://github.com/user-attachments/assets/7ffef1f4-d9f2-402f-bc0c-a1eb0f297a54" />
<img width="1888" height="864" alt="image" src="https://github.com/user-attachments/assets/aef73568-b8e9-4fb2-ae81-be85e26688e8" />





---

## 8. Acknowledgements

* This project was completed as a requirement for the "Programming in Java" course.
  
Project Completed: September 2025

Academic Session: Semester 3, B.Tech Computer Science

Institution: Vellore Institute of Technology (VIT)

This project demonstrates comprehensive understanding of Java SE features, object-oriented programming principles, and software engineering best practices.
