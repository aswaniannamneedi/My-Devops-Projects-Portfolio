# NexaFlow CI/CD Pipeline

### Project Overview
NexaFlow CI/CD Pipeline is an end-to-end Continuous Integration and Continuous Deployment project. It automates the build, testing, code quality analysis, artifact storage, and deployment of a Maven-based Java web application to a Tomcat application server. This project demonstrates DevOps best practices by integrating multiple tools into a seamless pipeline.

### Tools & Technologies Used
- **Version Control System:** Git & GitHub
- **Build Tool:** Maven
- **Artifact Repository:** Nexus
- **Code Quality Analysis:** SonarQube
- **Code Coverage Report:** JaCoCo
- **CI/CD Tool:** Jenkins
- **Notification System:** Slack
- **Application Server:** Apache Tomcat
- **Scripting Language:** Shell Scripting
- **Security & User Management:** Role-Based Authorization Strategy, Project-Based Matrix Security in Jenkins. These security measures ensure that only authorized users can access or modify Jenkins jobs and project resources, enhancing the overall security of the pipeline.

### Project Flow Diagram
```
GitHub ➡ Jenkins ➡ Maven ➡ SonarQube ➡ Nexus ➡ Jenkins ➡ Tomcat ➡ Slack Notifications
```

### Step-by-Step Pipeline Implementation

#### 1. Git Clone
- Jenkins pulls the code from GitHub using the **Git Plugin**.
- Branch: `development`
- Credentials managed in Jenkins.

#### 2. Build the Application
- Maven is used to build the application with the following command:
```
mvn clean package
```

#### 3. Code Quality and Coverage Analysis
- SonarQube integrated with Jenkins.
- JaCoCo plugin generates the code coverage report.
- Build fails if code coverage is below the threshold.

#### 4. Nexus Artifact Storage
- Successful builds are deployed to Nexus using the `mvn deploy` command.

#### 5. Deployment to Tomcat Server
- Jenkins uses the **Deploy to Tomcat via curl** shell script to upload the `.war` file to the Tomcat server.
- Deployment URL:
```
http://<Tomcat_IP>:8080/manager/text/deploy?path=/maven-web-application&update=true
```

#### 6. Slack Notifications
- Slack Plugin in Jenkins sends notifications for job **Start**, **Success**, and **Failure**.

### Security Implementation
- Jenkins User Creation
- Role-Based Strategy
- Project-Based Matrix Authorization

### Error Handling & Troubleshooting
- Build Failures with SonarQube Quality Gate
- Incorrect Workspace Paths in Shell Scripts
- Nexus Authentication Failures
- Slack Notification Not Triggering Due to Missing Webhook URL
- Tomcat Deployment Failures Due to Incorrect URL Format
- Jenkins Job Configuration Errors

### What I Learned
- End-to-End CI/CD Pipeline Creation
- Integrating Multiple Tools in Real-time Projects
- Debugging Build Failures
- Jenkins Security Management
- Slack Notifications for Automation

### Conclusion
NexaFlow CI/CD Pipeline is my **first DevOps project** where I independently integrated all the DevOps tools into one seamless pipeline. This project gave me hands-on experience with CI/CD pipelines and built my confidence to work on real-time DevOps projects.

### GitHub Repository
You can view the project and its pipeline scripts on my GitHub:
[GitHub Repository Link](https://github.com/aswaniannamneedi/NexaFlow-CI-CD-Pipeline)

Feel free to explore the code and steps I followed during the implementation.


