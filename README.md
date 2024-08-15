# CashRichAssesment

# MyCashRichApp

## Overview

MyCashRichApp is a backend application built with Spring Boot that allows users to create and update profiles, and retrieve cryptocurrency data from a third-party API (CoinMarketCap). This application includes user signup, login, and profile update functionalities with secure API access and proper validation.

## Tech Stack

- **Spring Boot**
- **Hibernate (JPA)**
- **MySQL**
- **Spring Security**
- **RestTemplate** for API calls
- **Lombok** (optional)

## Features

- **User Signup**: Users can sign up with a unique username, email, and a secure password.
- **User Login**: Authenticate users and allow them to log in.
- **Profile Management**: Users can update their profile information (First Name, Last Name, Mobile, Password).
- **Coin Data Retrieval**: Retrieve cryptocurrency data from CoinMarketCap using a secure API call.

## Project Structure

src
├── main
│ ├── java
│ │ └── com.example.mycryptoapp
│ │ ├── MyCryptoAppApplication.java
│ │ ├── controller
│ │ │ ├── UserController.java
│ │ │ ├── CoinController.java
│ │ ├── entity
│ │ │ ├── User.java
│ │ │ ├── ApiRequestLog.java
│ │ ├── repository
│ │ │ ├── UserRepository.java
│ │ │ ├── ApiRequestLogRepository.java
│ │ ├── service
│ │ │ ├── UserService.java
│ │ │ ├── CoinDataService.java
│ │ ├── security
│ │ │ └── SecurityConfig.java
│ │ ├── exception
│ │ │ ├── CustomException.java
│ │ │ └── GlobalExceptionHandler.java
│ └── resources
│ ├── application.properties
├── test
│ └── java
│ └── com.example.mycryptoapp
│ ├── UserServiceTest.java
│ ├── CoinDataServiceTest.java
└── README.md



## Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6 or higher
- MySQL 8.0 or higher

### Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/kushwahaarpit/CashRichAssesment.git
   cd mycashrichapp

   

CREATE DATABASE my_cashRich_db;

Update your application.properties with your MySQL credentials:

properties

spring.datasource.url=jdbc:mysql://localhost:3306/my_cashRich_db?useSSL=false&serverTimezone=UTC
spring.datasource.username=your-username
spring.datasource.password=your-password

Build the project:

bash

./mvnw clean install

Run the application:

bash

    ./mvnw spring-boot:run

Usage

You can test the application endpoints using tools like Postman or curl.
User Signup

    Endpoint: POST /api/users/signup

    Payload:

    json

    {
      "firstName": "John",
      "lastName": "Doe",
      "email": "john.doe@example.com",
      "mobile": "1234567890",
      "username": "johndoe",
      "password": "Secure@123"
    }

User Login

    Endpoint: POST /api/users/login
    Parameters: username, password

Update Profile

    Endpoint: PUT /api/users/{userId}/update

    Payload:

    json

    {
      "firstName": "John",
      "lastName": "Doe",
      "mobile": "0987654321",
      "password": "NewSecure@123"
    }

Get Coin Data

    Endpoint: GET /api/coins/data
    Parameters: symbols (e.g., BTC,ETH,LTC)

Running Tests

To run the tests:

bash

./mvnw test

Security

    Passwords are securely stored using BCryptPasswordEncoder.
    API endpoints are protected using Spring Security, allowing only authenticated users to access certain endpoints.

API Integration

This application integrates with the CoinMarketCap API to fetch cryptocurrency data. Make sure to set up your API key in the application.properties file:

properties

coinmarketcap.api.key=your-api-key
coinmarketcap.api.url=https://pro-api.coinmarketcap.com/v1/cryptocurrency/quotes/latest

