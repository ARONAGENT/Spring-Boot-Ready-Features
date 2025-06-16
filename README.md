# Spring Boot Production-Ready Features

[![Java](https://img.shields.io/badge/Java-21-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![Swagger UI](https://img.shields.io/badge/Swagger--UI-3.x-lightgrey.svg)](https://swagger.io/tools/swagger-ui/)
[![REST Client](https://img.shields.io/badge/REST%20Client-Enabled-blue.svg)](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
[![DevTools](https://img.shields.io/badge/Spring%20Boot%20DevTools-Enabled-yellow.svg)](https://docs.spring.io/spring-boot/docs/current/reference/html/using.html#using.devtools)

A comprehensive Spring Boot application demonstrating various production-ready features including auditing, API integrations, logging, actuators, and API documentation with step-by-step implementation and execution examples.

## WorkFlow Diagram

![image](https://github.com/user-attachments/assets/47120984-10af-4d96-984d-301a1ecfcfea)


## 🚀 Features

- **Spring Boot Web MVC & JPA** - RESTful API with database integration
- **DevTools** - Hot reload and fast development experience
- **Auditing** - Entity versioning and change tracking with Hibernate Envers
- **RestClient Integration** - Third-party API calls and response handling
- **Logging** - Structured logging with SLF4J and Logback
- **Spring Boot Actuator** - Production monitoring and management endpoints
- **API Documentation** - Interactive Swagger UI with OpenAPI

## 📋 Prerequisites

- **Java 21**
- **Maven 3.6+**
- **IntelliJ IDEA** (recommended)
- **MySQL/H2 Database** (for JPA operations)

## 🛠️ Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/ARONAGENT/Spring-Boot-Ready-Features.git
   cd Spring-Boot-Ready-Features
   ```

2. **Build the project**
   ```bash
   mvn clean install
   ```

3. **Run the application**
   ```bash
   mvn spring-boot:run
   ```

4. **Access the application**
   - Main API: `http://localhost:8080`
   - Swagger UI: `http://localhost:8080/swagger-ui.html`
   - Actuator Health: `http://localhost:8080/actuator/health`

## 🏗️ Project Structure

The project follows standard Spring Boot conventions with the following key components:

```
src/main/java/
├── controller/     # REST controllers
├── service/        # Business logic layer
├── repository/     # Data access layer
├── dto/           # Data Transfer Objects
├── entity/        # JPA entities
├── exception/     # Custom exception handling
├── clients/       # External API clients (RestClient implementations)
├── config/        # Configuration classes and beans
├── advice/        # Global exception handlers and AOP aspects
└── auth/          # Authentication and authorization components
                   # Auditable aware implementations


# Post Entity
```java
  private int postId;
  private String name;
  private String description;
  ```
```

## 📚 Implementation Details

### 1. Core Spring Boot Setup
- **Spring Boot Web MVC** for RESTful services
- **Spring Data JPA** for database operations
- **Post Entity** with fields: `postId`, `name`, `description`
- Complete CRUD operations with proper DTOs and exception handling

### 2. Development Tools
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
    <optional>true</optional>
</dependency>
```
- Automatic application restart
- Live reload capability
- Enhanced development experience

### 3. Auditing with Hibernate Envers
- Entity versioning and change tracking
- `@Audited` annotations for audit trails
- Historical data preservation in audit tables
- Revision tracking with timestamps

### 4. RestClient for Third-Party APIs
- External API integration
- GET, POST, PUT, DELETE operations
- Response transformation and error handling
- Employee management through external services

### 5. Advanced Logging
- **SLF4J** and **Logback** integration
- Multiple logging levels (INFO, DEBUG, ERROR)
- Custom log formatting via `application.properties`
- Day-wise log file rotation
- Structured logging for production monitoring

### 6. Spring Boot Actuator
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-actuator</artifactId>
</dependency>
```

**Available Endpoints:**
- `/actuator/health` - Application health status
- `/actuator/info` - Application metadata
- `/actuator/metrics` - Performance and usage statistics
- `/actuator/env` - Environment properties

### 7. API Documentation with Swagger
- **OpenAPI 3.0** specification
- Interactive **Swagger UI** interface
- Comprehensive API endpoint documentation
- Request/response examples
- Built-in API testing capabilities

## 🔌 API Endpoints

### Post Management
- `POST /posts/add` - Create a new post
- `GET /posts/all` - Retrieve all posts
- `GET /posts/{id}` - Get post by ID
- `PUT /posts/update/{id}` - Update existing post
- `DELETE /posts/delete/{id}` - Delete post

### Employee Management (via RestClient)
- `POST /employees/add` - Add employee via external API
- `GET /employees/all` - Fetch employees from external service
- `PUT /employees/update/{id}` - Update employee data
- `DELETE /employees/delete/{id}` - Remove employee

### Auditing
- `GET audit/posts/{id}` - Get audit history for posts

## 📸 Execution Screenshots

The repository includes comprehensive execution screenshots demonstrating:

- ✅ CRUD operations for Post entity
- ✅ RestClient third-party API calls
- ✅ Logging output and file storage
- ✅ Swagger UI interface and operations
- ✅ Auditing and revision tracking
- ✅ Exception handling scenarios

## 🔧 Configuration

### Application Properties
```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/springboot_features
spring.datasource.username=your_username
spring.datasource.password=your_password

# JPA Configuration
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# Logging Configuration
logging.level.com.yourpackage=DEBUG
logging.pattern.console=%d{yyyy-MM-dd HH:mm:ss} - %msg%n

# Actuator Configuration
management.endpoints.web.exposure.include=health,info,metrics
```

### Execution Images ->

  #### 1.Add post
  ![00 addPost(post request)](https://github.com/user-attachments/assets/04506588-7814-463e-addb-2679d4586e1b)

  #### 2.Get post
  ![01 allPost(get)](https://github.com/user-attachments/assets/17b4aa88-6426-447d-a2b5-6c8d60c95591)
  
  #### 3.Update Post
  ![02 updatePost(put request)](https://github.com/user-attachments/assets/5a9a0f2b-f8ae-4718-85a9-e0ae30d7d969)

### 4. Spring Boot Basic Auditing and Advanced Auditing with Hibernate Envers
- Implemented entity versioning and auditing using Hibernate Envers.
- Enabled auditing annotations like `@Audited` and `@RevisionEntity`.
- Stored historical changes in audit tables.

  ### Steps of Doing Auditing - > [Auditing and Advanced Auditing using Hibernate Envers.pdf](https://github.com/user-attachments/files/18678411/Auditing.and.Advanced.Auditing.using.Hibernate.Envers.pdf)
    ![03 auditingRevisionChecking](https://github.com/user-attachments/assets/cc9b1109-24d9-46f0-977c-8c660ef8adf8)

  ## Steps of Doing RestClient -> [RestClient in Spring Boot.pdf](https://github.com/user-attachments/files/18678418/RestClient.in.Spring.Boot.pdf)


  ### Exceution Images ->
  #### 1.Add Employee Using RestClient
  ![04 employeePOST(RestClientThirdPartyCall)fromWEEK2Homework](https://github.com/user-attachments/assets/30c9e383-31fb-4002-a8fe-036e80fe88f6)

  #### 2.Get Employee Using RestClient
  ![05 employeeGET(RestClientThirdPartyCall)fromWEEK2Homework](https://github.com/user-attachments/assets/cbd5c576-9f98-4d4a-95f1-afe2c285c002)

  #### 3.Update Employee Using RestClient
  ![06 employeeUpdate(RestClientThirdPartyCall)fromWEEK2Homework](https://github.com/user-attachments/assets/12e053b0-c6e7-40f9-b090-a706235409c3)

  #### 4.Delete Employee Using RestClient
  ![07 employeeDELETE(RestClientThirdPartyCall)fromWEEK2Homework](https://github.com/user-attachments/assets/29ca375d-7a73-4197-a953-5e6bd9f66e4a)

  #### 5.Delete Employee Using RestClient
  ![7 1 employeeDELETE(RestClientThirdPartyCall)fromWEEK2Homework](https://github.com/user-attachments/assets/8beb3aca-4a9a-4171-b4dc-9bfa60e322a7)

  #### 6.Exception Handling If Employee Not Found
  ![15 exceptionHandingDone(if not found By Id)](https://github.com/user-attachments/assets/5b75bf60-fef6-40da-919e-64f402e9610d)


### 5. Logging in Spring Boot Applications
- Configured logging using `application.properties`.
- Implemented logging levels (INFO, DEBUG, ERROR, etc.).
- Used SLF4J and Logback for structured logging.

## Execution Images ->

#### 1.Logging Working Fine When POST The Employee

![08 Logging-AddData](https://github.com/user-attachments/assets/b78ef5ba-fed6-4bc7-912f-ed36dc3df6b8)

#### 2.Logging Working Fine When Get The Employee

![09 Logging-all-data](https://github.com/user-attachments/assets/c885d096-39b9-4fa4-9449-5ac55ee52bb7)

#### 3.Logging Working Fine When PUT The Employee

![10 Logging-update-data](https://github.com/user-attachments/assets/5fcc433a-91ab-4dc0-aa58-d7e6f0ac8589)

#### 4.Custom Logging Using Logging Formatters in application.properties

![12 Logging-(Log-Formatters)](https://github.com/user-attachments/assets/90d03465-9621-497c-a059-e7cc6882b8c9)

#### 5.LogBack used to save Logging DAY WISE

![13 logback-spring xml(config)](https://github.com/user-attachments/assets/e3819c46-d802-4bb0-a4c9-7b887f8a35b7)

#### 6.Logging Stored in file 

![14 Logging-storedinFile(application log)](https://github.com/user-attachments/assets/435acf67-d72c-48f8-80fb-8776a52d3f99)

### 7. OpenAPI and Swagger to Generate API Documentation
- Integrated Swagger UI to generate interactive API documentation.
- Added OpenAPI annotations to document REST endpoints.
- Hosted the API documentation at `/swagger-ui.html`.

  ### Execution Images ->

  #### 1. Swagger UI Interface

  ![16 Swagger-ui(Interface)](https://github.com/user-attachments/assets/f4dc66ca-f59f-469d-9882-22c4a39408c3)

  #### 2. Swagger UI Exceution POST Request

  ![17 Swagger-ui(POST-Method)](https://github.com/user-attachments/assets/9f1168a0-82e3-44be-b101-41f6f7bd8d0e)

  #### 3. Swagger UI Exceution Get Request

  ![18 Swagger-ui(Get-Method)allElements](https://github.com/user-attachments/assets/af38d3d7-5f6b-4cb0-8392-eab0d02d032f)
   
  #### 4. Swagger UI Exceution Get Request By ID

  ![19 Swagger-ui(GET-Method)getElementById](https://github.com/user-attachments/assets/6b49e76f-3eef-4979-9445-82ace9399db7)

  #### 5. Swagger UI Exceution Put Request 

  ![20 Swagger-ui(Put-Method)](https://github.com/user-attachments/assets/99187367-7aec-4c45-9d95-68500cc5a81c)

  #### 6. Swagger UI Exceution Delete Request

  ![21 Swagger-ui(Delete-Method)deleteById](https://github.com/user-attachments/assets/c6232faf-6759-4474-a955-e3d6cb7c4e8d)

  #### 7. Swagger UI Exceution Delete Request If ID is not Found

  ![22 Swagger-ui(Delete-Method)NOT_FOUND_BY_ID](https://github.com/user-attachments/assets/ff144c40-068f-4d38-a2a6-48514a19fe04)

  #### 8. Swagger UI Exceution Auditing Request 

  ![23 Swagger-ui(Auditing)](https://github.com/user-attachments/assets/9d776dc3-362c-42f8-9e2c-cf8439faad0b)


## 👨‍💻 Author

**Rohan Uke**  
Backend Developer | Java & Spring Boot Enthusiast

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rohan-uke)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ARONAGENT)

---

## ⭐ Show your support

Give a ⭐️ if this project helped you learn microservices architecture!

## 📞 Support

If you have any questions or need help with the project, please:
1. Check the [Issues](https://github.com/ARONAGENT/Spring-Boot-Ready-Features/issues) page
2. Create a new issue if your question isn't already answered
3. Contact me via [LinkedIn](https://linkedin.com/in/rohan-uke)

⭐ Star this repository if you find it helpful!
