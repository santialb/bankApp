# BankApp

BankApp is a simple web-based banking application built with Spring Boot. It allows users to register, log in, view account information, deposit funds, withdraw funds, and transfer money to other accounts. The application uses Thymeleaf for server-side rendering of HTML views and stores data in a MySQL database.

## Features

- **User Registration**: Create a new account with a unique username and password.
- **User Authentication**: Log in with a username and password.
- **View Account Details**: View balance and transaction history.
- **Deposit Funds**: Deposit money into the account.
- **Withdraw Funds**: Withdraw money from the account (with balance checks).
- **Transfer Funds**: Transfer money to another user by username.
- **Transaction History**: View a list of past transactions.

## Technologies Used

- **Spring Boot**: For building the back-end logic.
- **Spring Security**: For handling authentication and authorization.
- **Thymeleaf**: For server-side rendering of HTML views.
- **MySQL**: As the relational database for storing account and transaction data.
- **Bootstrap**: For basic styling of HTML templates.

## Project Structure
```
src
├── main
│   ├── java
│   │   └── com.example.bank
│   │       ├── BankApplication.java          # Main entry point of the application
│   │       ├── config
│   │       │   └── SecurityConfig.java       # Spring Security configuration
│   │       ├── controllers
│   │       │   └── BankController.java       # Controller for handling user requests
│   │       ├── models
│   │       │   ├── Account.java              # Account entity
│   │       │   └── Transaction.java          # Transaction entity
│   │       ├── repositories
│   │       │   ├── AccountRepository.java    # Repository for Account entity
│   │       │   └── TransactionRepository.java # Repository for Transaction entity
│   │       └── services
│   │           └── AccountService.java       # Service layer for handling business logic
│   └── resources
│       ├── application.properties            # Application configuration
│       └── templates                         # Thymeleaf templates
│           ├── dashboard.html                # User dashboard page
│           ├── login.html                    # Login page
│           ├── register.html                 # Registration page
│           └── transactions.html             # Transaction history page
```
### Prerequisites

- **Java 17** or higher
- **MySQL** (or another relational database if you modify the configurations)
- **Maven** (for building and running the application)

### Database Configuration

Update the `application.properties` file with your MySQL database credentials.
```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/bankappdb
spring.datasource.username=YOUR_DB_USERNAME
spring.datasource.password=YOUR_DB_PASSWORD
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```

### Running the Application
- Build and Run the application with Maven:
```bash
mvn spring-boot:run
```
- Access the application at http://localhost:8080.

## Endpoints and Usage

- **`/register`**: Registration page for new users.
- **`/login`**: Login page for registered users.
- **`/dashboard`**: User dashboard displaying account balance and recent transactions.
- **`/transactions`**: Transaction history page.

### Account Actions (from the dashboard):

- **Deposit**: Deposit funds to your account.
- **Withdraw**: Withdraw funds from your account.
- **Transfer**: Transfer funds to another account using the recipient's username.

## Security

This application uses Spring Security to handle user authentication and authorization. Passwords are hashed using `BCryptPasswordEncoder` before being stored in the database.

## Author

Created by Santiago Albarracin.
