# School Management Application

Welcome to the **School Management Application**! This project is a simple web app designed to manage teacher information, built using **ASP.NET Core MVC**, **Web API**, and a **MySQL** database.

## Features

The application has the following core features:

- 📜 **List Teachers**: View a list of all teachers, displaying their ID, full name, and other details. You can also search for teachers by their first name, last name, full name, hire date, or salary.
  
- 🧑‍🏫 **Show Teacher Details**: See detailed information for a specific teacher, including their ID, full name, employee number, hire date, and salary.

- ➕ **Add Teacher**: Add new teachers to the database. You can submit the form using the traditional method or with **AJAX** for a faster experience. There's error handling in place for:
  - Empty name fields
  - Hire dates set in the future
  - Invalid employee numbers (must start with "T" followed by digits)
  - Duplicate employee numbers
  
- ❌ **Delete Teacher**: Delete a teacher by their ID. You can either do this through a **POST API** or a **confirmation page** in the web interface. Error handling is included for cases where you try to delete a teacher who doesn't exist.

## Technologies Used

This project is built with the following technologies:

- 🚀 **ASP.NET Core MVC** – The framework used to build the web application.
- 💻 **C#** – The programming language for backend logic.
- 🗃️ **MySQL** – A relational database to store teacher information.
- 🔗 **Entity Framework Core** – The ORM used to connect to the MySQL database.
- 🎨 **Bootstrap** – For front-end styling.
- 📱 **jQuery + AJAX** – For asynchronous operations like adding and deleting teachers.

## Getting Started

### Prerequisites

Before you can run the application, make sure you have the following:

- **Visual Studio 2022+** (or any compatible IDE)
- **.NET 6 SDK or later**
- **MySQL Server** running locally
- **MySQL Connector for .NET** (installed via NuGet)

## Setup Instructions

### Prerequisites

To get started, you'll need the following:

- **Visual Studio 2022+** (or any compatible IDE)
- **.NET Framework (or .NET Core/5+ SDK)**
- **MySQL Server** running locally
- **MySQL Connector/NET** (installed via NuGet)

## API Endpoints

### List All Teachers

GET /api/TeacherData/ListTeachers

### Search Teachers

GET /api/TeacherData/ListTeachers/{SearchKey?}

### Get Teacher Details by ID

GET /api/TeacherData/FindTeacher/{id}

### Add a New Teacher

POST /api/TeacherData/AddTeacher

### Request Body (JSON format):

{
  "TeacherFname": "FirstName",
  "TeacherLname": "Lastname",
  "EmployeeNumber": "T1234",
  "HireDate": "2024-01-15",
  "Salary": 55
}

### Delete a Teacher by ID

POST /api/TeacherData/DeleteTeacher/{id}

### API Endpoints

### List All Teachers
GET /api/TeacherData/ListTeachers

### Search Teachers
GET /api/TeacherData/ListTeachers/{SearchKey?}

### Get Teacher Details by ID
GET /api/TeacherData/FindTeacher/{id}

### Add a New Teacher
POST /api/TeacherData/AddTeacher

### Request Body (JSON format):
{
  "TeacherFname": "FirstName",
  "TeacherLname": "Lastname",
  "EmployeeNumber": "T1234",
  "HireDate": "2024-01-15",
  "Salary": 55
}

### Delete a Teacher by ID

POST /api/TeacherData/DeleteTeacher/{id}


### Testing the APIs
### List all teachers
curl http://localhost:<your_port>/api/TeacherData/ListTeachers

### Find a teacher by ID
curl http://localhost:<your_port>/api/TeacherData/FindTeacher/1

### Add a new teacher (example with JSON data)
curl -X POST -H "Content-Type: application/json" -d '{
  "TeacherFname": "John",
  "TeacherLname": "Doe",
  "EmployeeNumber": "T1234",
  "HireDate": "2024-01-01",
  "Salary": 65000
}' http://localhost:<your_port>/api/TeacherData/AddTeacher

### Delete teacher with ID 3
curl -X POST http://localhost:<your_port>/api/TeacherData/DeleteTeacher/3












