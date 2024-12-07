# WEB322 Assignment 6 - README

## Overview

This assignment focuses on enhancing a web application by implementing secure user authentication and session management. The process involves integrating **MongoDB** for data persistence, **bcrypt.js** for password hashing, and **client-sessions** for managing user sessions. By the end, the application provides functionality for user registration, login, logout, and tracking user login history. Routes are protected to ensure only authenticated users can access certain parts of the application.

---

## Steps to Completion

### Part A: User Accounts and Sessions

1. **Set Up MongoDB Atlas**  
   - A MongoDB Atlas account is set up to host the database.  
   - A cluster and database are created for storing user credentials and login history.  
   - A connection string is generated to enable the application to interact with the database.

2. **Create the Authentication Service**  
   - A dedicated `auth-service` module is added to manage user data.  
   - The schema defines user attributes such as:
     - `username`
     - `password`
     - `email`
     - `login history`
   - The module handles database initialization, user registration, and validation.

3. **Integrate User Registration**  
   - Users can create new accounts.  
   - Registration validates:
     - Password matching.
     - Duplicate usernames.
   - Successful registrations save user data to the database, while errors are clearly communicated.

4. **Implement Login Functionality**  
   - The application verifies user credentials against stored data.  
   - Login attempts are tracked, user agent information is recorded, and login history is updated in the database.  
   - Only valid credentials allow access to protected areas.

5. **Add Middleware for Sessions**  
   - The **client-sessions** middleware is configured to securely manage user sessions.  
   - Custom middleware ensures session data is available in views and protects routes by redirecting unauthenticated users to the login page.

6. **Define Routes for Authentication**  
   The application includes the following routes:
   - **Register**: Enables users to create accounts.
   - **Login**: Authenticates users and starts a session.
   - **Logout**: Ends the session and redirects to the home page.
   - **User History**: Displays the login history of authenticated users.  
   Each route integrates seamlessly with the backend and ensures a smooth user experience.

---

### Part B: Password Hashing

1. **Integrate bcrypt.js for Security**  
   - The application uses **bcrypt.js** to hash passwords before saving them.  
   - This ensures stored passwords are secure and cannot be retrieved in plaintext, enhancing security.

2. **Validate Passwords Against Hashes**  
   - During login, **bcrypt.js** compares entered passwords with their hashed counterparts.  
   - This ensures secure authentication.

3. **Clean the Database**  
   - Test user data is removed from the database to maintain consistency before implementing hashing.

---

### Finalization

1. **Testing and Debugging**  
   - The application is tested locally to ensure all features function correctly, including:
     - Registration.
     - Login.
     - Session handling.
     - Route protection.

2. **Deployment**  
   - The completed application is pushed to a GitHub repository and deployed on Cyclic.  
   - Deployment ensures the server starts correctly and all dependencies are configured.

3. **Submission**  
   - A compressed version of the application folder is submitted to the assignment portal, adhering to submission guidelines.

---

## Features Upon Completion

- **Secure User Authentication**  
  Users can register with unique credentials, and their passwords are securely hashed before storage.

- **Session Management**  
  The application securely manages user sessions, allowing authenticated users to navigate protected areas.

- **Login History Tracking**  
  User actions are tracked, and login history is available for auditing.

- **Route Protection**  
  Unauthenticated users are redirected to login pages, ensuring restricted access to sensitive areas.

- **User-Friendly Interface**  
  Views dynamically adjust based on user login status, providing a seamless experience.


