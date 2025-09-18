# 🏥 Hospital Management System

A robust, console-based Hospital Management System built in **Java** with **JDBC** for seamless connectivity to a **MySQL** database. This application allows for efficient management of patient records, doctor information, and appointments.

---

## ✨ Features

-   **Patient Management**: Add new patients to the system and view a comprehensive list of all registered patients.
-   **Doctor Management**: View a list of all available doctors and their specialties.
-   **Appointment Booking**: Schedule appointments by selecting a patient and a doctor. The system intelligently checks for doctor availability to prevent scheduling conflicts.
-   **Real-Time Database Interaction**: Every action, from adding a patient to booking an appointment, instantly updates the MySQL database.
-   **Robust Error Handling**: Implemented comprehensive `SQLException` handling to ensure the application remains stable and provides clear feedback.

---

## 🛠️ Built With

-   **Java**
-   **MySQL**
-   **JDBC** (Java Database Connectivity)

---

## 🚀 Getting Started

Follow these steps to get the project up and running on your local machine.

### Prerequisites

Ensure you have the following installed on your system:
* Java Development Kit (JDK) 8 or higher
* MySQL Server
* MySQL JDBC Driver `.jar` file


### Installation

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/haneef111/hospital-management-system.git](https://github.com/haneef111/hospital-management-system.git)
    cd hospital-management-system
    ```


2.  **Database Setup**
    * In your MySQL client, create a new database.
        ```sql
        CREATE DATABASE hospital;
        USE hospital;
        ```
    * Run the following script to create the required tables.
        ```sql
        
        -- Create Patients Table
        CREATE TABLE patients (
            id INT PRIMARY KEY AUTO_INCREMENT,
            name VARCHAR(255) NOT NULL,
            age INT NOT NULL,
            gender VARCHAR(50)
        );


        -- Create Doctors Table
        CREATE TABLE doctors (
            id INT PRIMARY KEY AUTO_INCREMENT,
            name VARCHAR(255) NOT NULL,
            specialization VARCHAR(255)
        );


        -- Create Appointments Table
        CREATE TABLE appointments (
            id INT PRIMARY KEY AUTO_INCREMENT,
            patient_id INT,
            doctor_id INT,
            appointment_date DATE NOT NULL,
            FOREIGN KEY (patient_id) REFERENCES patients(id),
            FOREIGN KEY (doctor_id) REFERENCES doctors(id)
        );
        ```


3.  **Configure JDBC Connection**
   
    * Add the **MySQL JDBC Driver `.jar`** file to your project's classpath.
      
    * Open the Java source code and update the database connection variables with your credentials.
        ```java
        private static final String URL = "jdbc:mysql://localhost:3306/hospital";
        private static final String USERNAME = "your_mysql_username";
        private static final String PASSWORD = "your_mysql_password";
        ```

5.  **Compile and Run**
    * Compile and run the main application file, `HospitalManagementSystem.java`, from your IDE or the command line.

