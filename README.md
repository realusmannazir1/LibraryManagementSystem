# LibraryManagementSystem
A JavaFX desktop app for our OOP semester project. Features include user login/registration, book &amp; student management, and borrow/return with due dates. Built using Java OOP, JavaFX for GUI, and MySQL (via JDBC) for database integration.
--------------------------------
Project Features
Login and Registration (Authentication)

Dashboard after Login

Book Management (Add, Update, Delete, Search)

Student Management

Borrow and Return System

Deadlines, Penalty Tracker (optional)

GUI using JavaFX (FXML + Controllers)
----------------------------------

Technologies Required
Java SE (JDK 17+)

JavaFX SDK

Eclipse IDE

Scene Builder (for FXML GUI)

MySQL or SQLite (for Database)

JDBC (for Java-DB connection)

------------------------------
Cretaed:

LibraryManagementSystem/
│
├── src/
│   ├── application/
│   │   ├── Main.java
│   ├── controllers/
│   │   ├── LoginController.java
│   │   ├── RegisterController.java
│   │   ├── DashboardController.java
│   │   ├── BookController.java
│   ├── models/
│   │   ├── Book.java
│   │   ├── Student.java
│   │   ├── User.java
│   ├── database/
│   │   ├── DBConnection.java
│
├── resources/
│   ├── login.fxml
│   ├── register.fxml
│   ├── dashboard.fxml
│   ├── book_form.fxml
│
├── lib/ (for JavaFX & MySQL JDBC jar)

===========================

Database Tables


CREATE DATABASE library_db;

USE library_db;

CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50),
    middle_name VARCHAR(50),
    last_name VARCHAR(50),
    age INT,
    email VARCHAR(100),
    mobile_number VARCHAR(20),
    department VARCHAR(50),
    university VARCHAR(100),
    semester VARCHAR(20)
);

CREATE TABLE books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100),
    author VARCHAR(100),
    genre VARCHAR(50),
    availability BOOLEAN DEFAULT TRUE
);

CREATE TABLE borrow_records (
    record_id INT AUTO_INCREMENT PRIMARY KEY,
    student_id INT,
    book_id INT,
    borrow_date DATE,
    return_date DATE,
    deadline DATE,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (book_id) REFERENCES books(book_id)
);


==========================

 Create JavaFX Login Screen


 <Button text="Login" onAction="#loginAction"/>
<TextField fx:id="usernameField"/>
<PasswordField fx:id="passwordField"/>
<Label fx:id="errorLabel"/>

worring on next steps
