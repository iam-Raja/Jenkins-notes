# Jenkins-notes

### What is Jenkins:
* Jenkins is a CI/CD tool that allows me to manage the entire continuous integration and continuous deployment process, from the creation of a pull request to deployment. It continuously delivers our newly created images to development or QA environments. We use multiple plugins to achieve this, such as the Git plugin, Maven plugin, and SonarQube plugin for code analysis. We also utilize the Kubernetes plugin for deploying applications

### Explain the Master-Slave architecture:
* In a Master-Slave architecture, I can reduce the load on the master by configuring multiple slave nodes and running Jenkins jobs on those slaves. To connect a Linux agent as a slave to Jenkins, I need to go to the nodes section and add a new node. I must provide the IP address of the slave I want to attach, along with the PEM file for authentication. I also need to specify the user directory and select the type of checks that Jenkins should perform while connecting to the slave.
If I want to connect a Windows agent, I need to download the jnlp.jar file onto the Windows machine. After that, I should run the jnlp.jar so that Jenkins can connect the Windows agent as a slave to the Jenkins master

### Explain the CI/CD pipelines :
* In our CI/CD pipelines, we have multiple stages that are triggered via a webhook that we have configured. Whenever a developer creates a pull request, this action triggers the Jenkins pipeline through the webhook. The pipeline consists of several stages:
1.	Checkout Stage: In the first stage, we check out the latest code from the repository.
2.	Build Stage: In the second stage, we build the artifact.
3.	SonarQube Scan Stage: In the third stage, we perform SonarQube scans to identify vulnerabilities, code smells, and bugs in the project.
4.	Docker Build Stage: In the fourth stage, we build the Docker image using a Docker file.
5.	Trivy Scan Stage: In the fifth stage, we use Trivy scans to check for vulnerabilities inside the Docker container.
6.	Push Image Stage: In the sixth stage, we push the built image to the container registry.

After that, we upgrade our development or QA servers with the latest image and run our QA automation test cases against the newly released build. We send the test results as post-build actions to both the developers and the QA team.
We utilize multiple plugins within these pipelines, such as the Jenkins Credentials plugin, to securely store credentials. By using the credentials ID in these stages, we can check out the repositories and authenticate with Docker to push all images to the container repository

### Explain the declarative pipeline syntax used in Jenkins:
* The declarative pipeline follows a specific syntax, starting with the pipeline block. Within this block, I have stages, and each stage contains steps. I can define multiple stages inside the stages block, and I also have the ability to run steps in parallel, allowing for simultaneous execution of multiple stages

### What kind of pipelines have you written in Jenkins :
* I have worked on multiple types of pipelines, including declarative pipelines, scripted pipelines, and hybrid pipelines, which combine elements of both declarative and scripted pipelines

### :
*

### :
*

### :
*

### :
*
### :
*
### :
*
### :
*

### :
*

### :
*

### :
*

### :
*

### :
*

