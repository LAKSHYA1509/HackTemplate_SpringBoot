
# Hack Template for Java Spring Boot Authentication

This repository provides a hack template built with Java Spring Boot, designed to efficiently manage login and signup pages with OAuth integration for Google and GitHub. The frontend is designed to be user-friendly and visually appealing, making it easy for developers to integrate database connections and authentication in their projects.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Prerequisites](#prerequisites)
3. [Configuration](#configuration)
   - [Database Configuration](#database-configuration)
   - [Google OAuth Configuration](#google-oauth-configuration)
   - [GitHub OAuth Configuration](#github-oauth-configuration)
4. [Running the Application](#running-the-application)
5. [Customizing the Entity Classes](#customizing-the-entity-classes)
6. [Features](#features)
7. [Contributing](#contributing)
8. [License](#license)

## Getting Started

To get started with this template, clone the repository and follow the steps below to set up your environment.

```bash
git clone https://github.com/your-username/hack-template.git
cd hack-template
```

## Prerequisites

Make sure you have the following installed:

- [Java 11+](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- [Spring Boot](https://spring.io/projects/spring-boot)
- [MySQL](https://www.mysql.com/downloads/)
- [Maven](https://maven.apache.org/download.cgi)

## Configuration

### Database Configuration

1. Open the `application.properties` file located in `src/main/resources/`.

2. Change the database name, username, and password to match your MySQL configuration:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/your_database_name
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    ```

3. Create the specified database in MySQL:

    ```sql
    CREATE DATABASE your_database_name;
    ```

### Google OAuth Configuration

1. Obtain your Google API keys from the [Google Developers Console](https://console.developers.google.com/).

2. Open the `application.properties` file and update the following properties:

    ```properties
    spring.security.oauth2.client.registration.google.client-id=your_google_client_id
    spring.security.oauth2.client.registration.google.client-secret=your_google_client_secret
    spring.security.oauth2.client.registration.google.redirect-uri={baseUrl}/login/oauth2/code/google
    ```

### GitHub OAuth Configuration

1. Obtain your GitHub API keys from the [GitHub Developer Settings](https://github.com/settings/developers).

2. Update the `application.properties` file with your GitHub credentials:

    ```properties
    spring.security.oauth2.client.registration.github.client-id=your_github_client_id
    spring.security.oauth2.client.registration.github.client-secret=your_github_client_secret
    spring.security.oauth2.client.registration.github.redirect-uri={baseUrl}/login/oauth2/code/github
    ```

## Running the Application

After configuring the application, you can run it using Maven:

```bash
mvn spring-boot:run
```

Access the application in your browser at `http://localhost:8080`.

## Customizing the Entity Classes

The template includes basic entity classes for User management. You can modify these classes according to your project's requirements.

1. **User Entity Class:**
   - Located at `src/main/java/com/yourpackage/model/User.java`.
   - Fields include `id`, `username`, `email`, `password`, `roles`, etc.
   - Add or remove fields as needed to customize the user profile.

   Example of adding a new field:

   ```java
   @Column(name = "phone_number", nullable = true)
   private String phoneNumber;
   ```

   - Update your database schema accordingly.

2. **Repository Layer:**
   - Located at `src/main/java/com/yourpackage/repository/UserRepository.java`.
   - Use this interface to interact with the database.

3. **Service Layer:**
   - Located at `src/main/java/com/yourpackage/service/UserService.java`.
   - Modify this class to include additional business logic.

## Features

- **Login and Signup:** Manage user registration and authentication.
- **OAuth Integration:** Support for Google and GitHub OAuth.
- **Beautiful Frontend:** Pre-built templates for a clean and responsive UI.
- **Database Integration:** Easily connect to MySQL databases.
- **Customization:** Modify entity classes and configurations as per your project requirements.

## Contributing

Feel free to fork this repository and contribute to it. Pull requests are welcome for any improvements or bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

# Please Note that this template code is part of my LegalDost project and no extra template variable code is permissible to copy. In case file names are not working in your pc. 
1. Go to start.spring.io and make a new project.
2. Copy paste main codes like application.properties, controllers, config, services etc. according to your needs.
3. Enjoy!!
