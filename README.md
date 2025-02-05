# Spring Boot Production-Ready Features

## Project Description
This project explores various production-ready features of Spring Boot, including auditing, API integrations, logging, actuators, and API documentation. It provides step-by-step implementation details along with execution images.

## Steps to Get Started
1. Go to [start.spring.io](https://start.spring.io/).
2. Select the necessary dependencies:
   - Spring Web
   - Spring Boot DevTools
   - Spring Data JPA
   - Hibernate Envers (for auditing)
   - MySQL Driver (to connect database)
   - Spring Boot Actuator
   - OpenAPI & Swagger (for API documentation)
3. Generate the project and extract it.
4. Open the project in your preferred IDE (IntelliJ, Eclipse, VS Code).
5. Start developing by following the steps below.

## Topics Covered

### 1. Setting up a Spring Boot Project with Spring Boot Web MVC and Spring Data JPA
- Implemented **Spring Boot Web MVC** and **Spring Data JPA**.
- Created a **POST entity** with the following structure:
  ```java
  private int postId;
  private String name;
  private String description;
  ```
- Developed controllers, services, repositories, DTOs, and exception handling.

  ### Execution Images ->

  #### 1.Add post
  ![00 addPost(post request)](https://github.com/user-attachments/assets/04506588-7814-463e-addb-2679d4586e1b)

  #### 2.Get post
  ![01 allPost(get)](https://github.com/user-attachments/assets/17b4aa88-6426-447d-a2b5-6c8d60c95591)
  
  #### 3.Update Post
  ![02 updatePost(put request)](https://github.com/user-attachments/assets/5a9a0f2b-f8ae-4718-85a9-e0ae30d7d969)



### 2. Spring Boot DevTools
- Spring Boot DevTools provides automatic application restart, live reload, and fast development experience.
- Simply add the dependency in `pom.xml`:
  ```xml
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-devtools</artifactId>
      <optional>true</optional>
  </dependency>
  ```

### 3. Spring Boot Basic Auditing and Advanced Auditing with Hibernate Envers
- Implemented entity versioning and auditing using Hibernate Envers.
- Enabled auditing annotations like `@Audited` and `@RevisionEntity`.
- Stored historical changes in audit tables.

### Execution Images ->
**Auditing**

![03 auditingRevisionChecking](https://github.com/user-attachments/assets/cc9b1109-24d9-46f0-977c-8c660ef8adf8)


### 4. Making Third-Party API Calls with RestClient
- Integrated external APIs using RestClient.
- Demonstrated GET and POST requests to third-party services.
- Managed response transformation and exception handling.

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


### 4.6 Spring Boot Actuator
- Added the **Spring Boot Actuator** dependency:
  ```xml
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-actuator</artifactId>
  </dependency>
  ```
- Provides **monitoring and management endpoints** like:
  - `/actuator/health` - Displays application health status.
  - `/actuator/info` - Shows application metadata.
  - `/actuator/metrics` - Provides performance and usage statistics.

### 4.7 OpenAPI and Swagger to Generate API Documentation
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

 
## How to Run the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/ARONAGENT/Spring-Boot-Ready-Features.git
   cd spring-boot-production-ready
   ```
2. Build the project using Maven:
   ```bash
   mvn clean install
   ```
3. Run the application:
   ```bash
   mvn spring-boot:run
   ```
4. Access the application endpoints and API documentation as per the topics above.

## Prerequisites
- Java 21
- Maven
- IntelliJ IDEA

## Contributing
Feel free to fork this repository and contribute with pull requests to improve the project.

## License
This project is open-source and available under the MIT License.

