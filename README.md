Animal Adoption and Care Platform
A web application for managing animal adoption requests. Users can submit requests to adopt animals, and administrators can view all adoption requests. The application is built using Spring Boot with MySQL as the database, and it includes Swagger UI for API documentation.

Features
Animal Adoption Request: Users can submit requests to adopt animals, providing their name, email, and animal details.
View Adoption Requests: Administrators can view all adoption requests submitted by users.
Database Integration: MySQL is used for storing the adoption requests.
API Documentation: Swagger UI is integrated for API documentation and testing.
Technologies Used
Backend: Java, Spring Boot
Database: MySQL
API Documentation: Swagger UI
Dependencies:
Spring Boot Starter Web
Spring Boot Starter Data JPA
MySQL Connector
Springfox Swagger
Prerequisites
Before running the project, ensure you have the following installed:

Java 11+: For running the Spring Boot application.
MySQL: For the database.
Maven: For building the project (if using Maven).
IDE: IntelliJ IDEA, Eclipse, or any Java IDE (optional).
Setup and Installation
1. Clone the Repository
First, clone the repository to your local machine:

bash
Copy code
git clone https://github.com/your-username/animal-adoption-care-platform.git
2. Configure MySQL Database
Create a database in MySQL:

sql
Copy code
CREATE DATABASE animal_adoption;
Create the table for adoption requests:

sql
Copy code
CREATE TABLE adoption_requests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    animal_name VARCHAR(255) NOT NULL,
    your_name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    date DATETIME DEFAULT CURRENT_TIMESTAMP
);
3. Configure Application Properties
Update the application.properties file with your MySQL database credentials. This file can be found in src/main/resources/application.properties.

properties
Copy code
# MySQL Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/animal_adoption
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
Make sure to replace yourpassword with your actual MySQL password.

4. Build and Run the Application
You can run the application using Maven or through your IDE.

Using Maven:
Open a terminal and navigate to the project directory.

Run the following command to build and run the application:

bash
Copy code
mvn spring-boot:run
Using IDE:
Open the project in your IDE (e.g., IntelliJ IDEA, Eclipse).
Run the AnimalAdoptionApplication.java class as a Java application.
5. Access the Application
Once the application is running, you can access the following:

API Endpoints: The backend will be running on http://localhost:8080.

POST /api/adopt: Create a new adoption request.
GET /api/adopt/requests: Retrieve all adoption requests.
Swagger UI: The API documentation will be available at http://localhost:8080/swagger-ui.html. You can use it to interact with the API endpoints.

Endpoints
POST /api/adopt
Create a new adoption request.

Request Body
json
Copy code
{
  "animalName": "Fluffy the Cat",
  "yourName": "John Doe",
  "email": "john.doe@example.com"
}
Response
json
Copy code
{
  "id": 1,
  "animalName": "Fluffy the Cat",
  "yourName": "John Doe",
  "email": "john.doe@example.com",
  "date": "2024-11-10T12:34:56"
}
GET /api/adopt/requests
Fetch all adoption requests.

Response
json
Copy code
[
  {
    "id": 1,
    "animalName": "Fluffy the Cat",
    "yourName": "John Doe",
    "email": "john.doe@example.com",
    "date": "2024-11-10T12:34:56"
  },
  {
    "id": 2,
    "animalName": "Rex the Dog",
    "yourName": "Jane Smith",
    "email": "jane.smith@example.com",
    "date": "2024-11-10T12:45:12"
  }
]
Swagger Documentation
To access the API documentation, navigate to the following URL in your browser:

bash
Copy code
http://localhost:8080/swagger-ui.html
Swagger UI provides an easy-to-use interface for interacting with the API and testing the endpoints.

Database Schema
AdoptionRequest Table
Field	Type	Description
id	INT	Primary Key, Auto Increment
animal_name	VARCHAR(255)	Name of the animal being adopted
your_name	VARCHAR(255)	Name of the person adopting the animal
email	VARCHAR(255)	Email address of the adopter
date	DATETIME	Timestamp of when the request was made
License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or suggestions, feel free to contact:

Author: Samar Malik
Email:samarmalik5098@gmail.com
