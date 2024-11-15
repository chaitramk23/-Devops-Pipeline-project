# Devops-Pipeline-project
Setting Up a Complete Devops Pipeline with Jenkins, Kubernetes, Docker,SonarQube, Nexus,Trivy, Prometheus &amp; Grafana with mail notification

# Developer Makes a Change and Pushes to GitHub
The process starts when a developer writes code to meet a new requirement (like changing the background color of a webpage). They push their changes to GitHub, a platform that stores and tracks code changes.

# Jenkins Begins the Pipeline
Jenkins, an automation tool, detects the new code change on GitHub and starts a series of automated steps (a “pipeline”) to make sure the code is ready for deployment. Jenkins handles all the tasks from building to testing and deploying the code.

# Code Goes Through a Series of Checks and Tests
Build the Code: Jenkins uses Maven, a build tool, to compile the code. This step makes sure the code is transformed into an executable form, so it’s ready to run.
Run Tests: Jenkins then runs tests using Maven to ensure the new code doesn’t break any existing features. This helps catch issues early.
File System Scan: The pipeline performs a quick check to make sure there are no unwanted files in the codebase.
Code Quality Check with SonarQube: SonarQube scans the code for bugs, security vulnerabilities, and other quality issues. This check ensures the code is clean and follows good practices.
Quality Gate: SonarQube applies a “quality gate,” which is a set of criteria the code must pass to move to the next stage. If it fails here, it won’t proceed until the issues are fixed.

# Preparing the Application for Deployment
Build Package: Jenkins uses Maven again to package the code into an artifact (a deployable file) like a .jar or .war file.
Store in Nexus Repository: This packaged file is stored in Nexus, which acts like a library for different versions of the application. This way, if needed, older versions can be accessed and redeployed.

# Containerization with Docker
Create Docker Image: Jenkins creates a Docker image of the application, which is a container that includes the application and its environment. This ensures the app runs the same way no matter where it’s deployed.
Security Scan with Trivy: Trivy scans this Docker image for any known security vulnerabilities, ensuring it’s safe to deploy.

# Deploying the Application to Kubernetes
Deploy to Kubernetes: Jenkins sends the Docker image to Kubernetes, a platform that helps manage and run applications consistently across different servers.
Verify Deployment: Jenkins checks to make sure the application is running smoothly in Kubernetes. This step ensures that the deployment was successful.

# Monitoring and Notifications
Application Monitoring: Once deployed, Prometheus collects data on the application’s performance (like CPU and memory usage), while Grafana displays this data in dashboards. This allows the team to see how well the application is performing and quickly spot any issues.
Email Notification: Jenkins sends an email to the team to inform them that the deployment is complete and the application is live.

