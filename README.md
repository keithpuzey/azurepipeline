Digital Bank (Generation One)
Digital Bank is a sample application that was developed for exploratory purposes to examine development frameworks and techniques. The application is an example online digital banking application with integrations into other services.

Getting Started
Using either an Eclipse IDE or IntelliJ, import the source code as an Existing Maven Project.
Prerequisites
Install Java SDK 
Java SDK 8  - Required only for JUnit tests using CodeSV mock services.
Install Apache Maven 
Install Eclipse IDE , Spring Tools Suite  or IntelliJ 
Executing Tests
JUnit Tests - Execute "mvn clean test"
Serenity BDD Acceptance Tests - Execute "mvn clean verify"
Serenity BDD tests use Cucumber Feature file definitions.
UI Tests are executed using the Selenium Java framework.
API Test are executed using the Rest Assured Java framework.
Use '-Dcucumber.options="--tags {tag}"' maven command line option to filter test execution based on Feature or Scenario tags defined within the feature files.
Packaging
To create a deployment package, execute "mvn clean package -DbuildNumber={###}"
To create a new Docker image, update the Dockerfile with the latest build number and then execute "docker build -t {imageName}:{imageTag} ."
Deployment
Digital Bank can be deployed as a single standalone application service or be deployed and configured to integrate with Digital Credit.

WAR Package Deployment 
Apache Tomcat version 8.5 or higher
Deployment does not work with Apache Tomcat 7.x
Copy the WAR file into an existing Tomcat instance under ${catalina.base}/webapps folder.
(Optional) Copy the digitalbank.properites file into the ${catalina.base}/conf folder.
Use to customize the configuration of the application.
The digitalbank.properties file is configured to be a "watched resource" in the deployment context. Any updates to the digitalbank.properties file will automatically trigger Tomcat to recycle the application to pick up the new changes.
Start the Tomcat service.
A digitalbank.log file will be created within ${catalina.base}/logs.
Docker Deployment 
Deploy Digital Bank as a standalone service.
Docker Compose Deployment
Deploy Digital Bank as a full stack to enable all services.
Use 'docker-compose -f [DOCKER_COMPOSE_FILE_NAME]'.
H2 In-Memory Database Deployment
MS SQL Server Database Deployment
MySQL Database Deployment
PostgreSQL Database Deployment
Interfaces
Web Interface @ https://{hostname}:{port}/bank
Sample user data is created when the application is started. User credentials for these users are as follows:
jsmith@demo.io/Demo123!
nsmith@demo.io/Demo123!
Swagger UI @ https://{hostname}:{port}/bank/swagger-ui.html
The API Admin user credentials are as follows:
admin@demo.io/Demo123!
Built With
Sufee Admin Dashboard  - A HTML5 Dashboard Template
Spring Boot  - Application Framework
Thymeleaf  - Server-Side Java Template
Swagger  - API Documentation
Apache Maven  - Software Project Management
Apache Tomcat  - Application Server / Servlet Engine
Apache Artemis  - Messaging Broker
H2 Database Engine  - In-Memory Database
MS SQL Server Database Engine  - Microsoft SQL Server
MySQL Database Engine  - MySQL
PostgreSQL Database Engine  - PostgreSQL
Serenity BDD  - Acceptance Testing Framework
JUnit 5  - Unit Testing Framework
CodeSV  - Unit Testing with Mock Services
BlazeMeter  - Functional / Performance API & UI Testing Services
