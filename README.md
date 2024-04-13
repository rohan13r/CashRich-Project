# CashRich-Project
Project Name: Crypto User Management and Coin Data API
LINK- https://drive.google.com/drive/folders/1bCpXkZNdgodQhHi5wltoFTmKU7LGeodi?usp=drive_link

Description:

This project is a Spring Boot backend application designed to allow users to create and update profiles, sign up and log in, and access coin data from a third-party API (CoinMarketCap Pro).

Tech Stack:

Spring Boot
Hibernate
MySQL
Apache Commons Validator (for username validation)
Features:

User Management:
User registration with unique username (email) and password (validation enforced).
User login with basic authentication.
User profile management: ability to update first name, last name, mobile number, and password.
Coin Data Integration:
Integration with CoinMarketCap Pro API to retrieve real-time cryptocurrency quotes.
Stores user-initiated API calls with timestamps in the database.
Error Handling:
Handles errors from the third-party API and provides user-friendly error messages.
Endpoints:

Endpoint	Description	HTTP Method	Authentication Required
/users/signup	Creates a new user account.	POST	No
/users/login	Logs a user in using username (email) and password.	POST	No
/users/me	Retrieves the currently logged-in user's profile information.	GET	Yes
/users/update	Updates the currently logged-in user's profile information.	PUT	Yes
/coins/latest	Retrieves real-time cryptocurrency quotes (using User ID and timestamp).	GET	Yes
API Headers:

User Authentication (for /users/me, /users/update, and /coins/latest): Include an Authorization header with a valid JWT token obtained during login.
Third-Party API (for /coins/latest):
Include X-CMC_PRO_API_KEY: Your CoinMarketCap Pro API key in the header.
Validation:

Username (email): Must be unique, alphanumeric with underscores allowed, and between 4 and 16 characters.
Password: Must be between 8 and 15 characters and include at least one uppercase letter, one lowercase letter, one digit, and one special character.
Security Considerations:

Basic authentication is used for login, but it's recommended to implement a more robust authentication mechanism like JWT (implemented in /users/me, /users/update, and /coins/latest).
Store user passwords securely using a one-way hashing algorithm with salting.
Validate API requests and sanitize user input to prevent potential security vulnerabilities.
Getting Started:

Clone this repository.
Install required dependencies (e.g., using Maven or Gradle).
Configure database connection details in application.properties (or equivalent).
Obtain a CoinMarketCap Pro API key and set it in an environment variable or configuration file.
Run the application using mvn spring-boot:run or gradle bootRun.
Additional Notes:

Consider implementing unit and integration tests for robust application functionality.
Explore error handling strategies for robust system behavior.
Secure your application by following best practices and staying updated on security vulnerabilities.
Future Enhancements:

Implement JWT authentication for a more secure API access mechanism.
Integrate with additional third-party APIs to expand user information or coin data access.
Implement user roles and permissions for more granular access control.

Steps to Run the Application- 

Locate the Application Folder: Navigate to the folder where your application files are saved. This typically involves using the command line or terminal to change directories (cd) to the appropriate location.

Set Docker IP Addresses (if applicable): If your application is using Docker containers and requires specific IP addresses, ensure that you have those IP addresses available and configured correctly. You may need to edit configuration files or environment variables to specify the Docker IP addresses.

Run the Application using execute.sh Script: If provided, execute the execute.sh script by running the following command in the terminal:


sh execute.sh
This script likely contains commands to build, deploy, or start the application with the necessary configurations.

Or Run Directly from Spring: Alternatively, if your application is a Spring Boot application, you can run it directly from within the Spring framework. You might do this by executing a Gradle or Maven command, depending on your build tool. For example:


./gradlew bootRun
or


mvn spring-boot:run
Ensure that you have the necessary dependencies installed and configured for your application to run smoothly.

Modify Database Credentials: If you're running the application with different database credentials than the default ones, make sure to update the configuration files or environment variables with the correct database credentials. This ensures that your application can connect to the database without any issues.

Monitor Application Logs: While the application is running, monitor the logs for any errors or warnings. This helps in troubleshooting and ensuring that the application is functioning as expected.

By following these steps, you should be able to execute your application smoothly either through Docker or directly from Spring Boot.
