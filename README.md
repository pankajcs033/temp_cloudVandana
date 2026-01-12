# Salesforce Switch – Spring Boot Web Application

A Spring Boot web application that integrates with Salesforce to authenticate users and fetch Salesforce metadata such as validation rules.
The application is designed to be deployed on an online server like Heroku.

---

## Project Overview

This project demonstrates:

* Salesforce OAuth 2.0 authentication
* Fetching Salesforce metadata after login
* Spring Boot MVC architecture
* Thymeleaf-based UI
* Cloud deployment readiness

---

## Tech Stack

* Java 17
* Spring Boot 3.5.x
* Maven
* Thymeleaf
* Salesforce REST APIs
* Heroku

---

## Project Structure

```
Project_WebApp/
│
├── src/
│   └── main/
│       ├── java/
│       │   └── Project_WebApp/demo/
│       │       ├── controller/
│       │       ├── service/
│       │       └── DemoApplication.java
│       └── resources/
│           ├── templates/
│           ├── static/
│           └── application.properties
│
├── pom.xml
├── Procfile
├── system.properties
└── README.md
```

---

## Prerequisites

* Java 17
* Maven 3.8+
* Git
* Salesforce Developer Account
* Heroku CLI

Verify installations:

```bash
java -version
mvn -version
```

---

## Environment Variables

Salesforce credentials should not be hardcoded.

Set the following environment variables:

```bash
SF_CLIENT_ID=your_salesforce_client_id
SF_CLIENT_SECRET=your_salesforce_client_secret
SF_REDIRECT_URI=https://your-app.herokuapp.com/oauth/callback
```

---

## Build the Project

Run the following command from the project root:

```bash
mvn clean package
```

On success, the following JAR file will be created:

```
target/demo-0.0.1-SNAPSHOT.jar
```

---

## Run Locally

```bash
java -jar target/demo-0.0.1-SNAPSHOT.jar
```

Access the application at:

```
http://localhost:8080
```

## Common Issues

| Issue                    | Solution                               |
| ------------------------ | -------------------------------------- |
| Port 8080 already in use | Use `server.port=${PORT:8080}`         |
| OAuth redirect error     | Ensure callback URL matches Salesforce |
| App crashes on deploy    | Check logs using `heroku logs --tail`  |
| JAR not found            | Verify Procfile JAR name               |

---

## Author

Harish Saini

---

## License

This project is intended for educational and demonstration purposes
