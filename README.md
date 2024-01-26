# System Admin / DevOps Engineer Test

## IMPORTANT:
    - Working URL of the app that can be accessible online - http://3.92.199.21:8081/
    - Upload the project to your own repo and send us the link - https://github.com/RajalakshmiNagendran/laravel-CICD
    - Launch the application through following URL - http://3.92.199.21:8081/

### Test assignment A: Docker and Microservices
**Objective:** To assess the candidate’s ability to work with Docker and microservices architecture.

**Task Description:**
- To Containerize the application first thing to checkout the code from source code repo. In my case I have used curl command to get the zip file and unzip the file in one of my EC2 ubuntu server created in AWS.
- I checked the existing docker-compose.yml and found the build context for laravel.test was already pointing to ./vendor/laravel/sail/runtimes/8.3. I have added composer service which requ
ires to build the app.
- Next I have written Dockerfile in the same path of the context.
- Created ubuntu base image, set maintainer, ARGS, ENV, RUN. etc... I have setup the WORKDIR to /var/www/html. Installing all the dependant packages in the container. Adding the user and group as sail. copied required files to start the container, supervisor file to check the system in case of any failures so that they are restarted automatically. The php.ini file contains a wide range of configuration settings that control PHP's behavior, also giving execution permission to start-container script(also placed in the same directory). Setting ENTRYPOINT to start
the container script.
- copied .env.example file to .env and set the required Environment variables like DB_DATABASE, DB_USERNAME, DB_PASSWORD, etc...
- Installed and updated composer.I performed docker-compose up --build to build the entire application. Running php artisan test for testing.
- Please check the repo link shared in above IMPORTANT point.

### Test assignment B: Continuous Integration/Continuous Deployment (CI/CD)

**Task Description:** 
- Created a CI/CD pipeline using a tool like Jenkins(The pipeline stages for building, testing, and deploying the application in localhost).
- Steps to perform CI CD Pipeline, Installed Jenkins in the commandline by appending the Debian package repository, install using apt package. Installed required plugins in Jenkins configuration. Created Jenkins pipeline which includes multiple stages for Verify Tooling, Clear All Running Docker Containers, Build, Test and Deploy.
- Please check the Jenkinsfile created for the CI CD in the above mentioned Github url.

### Test assignment C: Deployment to a Cloud or Server Environment

**Task Description:**
- Extended te CI/CD pipeline to include a deployment stage that automatically deploys the application to a cloud provider (AWS EKS) 
- Created EKS cluster which includes all the networks, security congurations inbuilt and it provides highly available and sclable cluster.
- Implemented monitoring and logging for the Laravel application using Prometheus and Grafana.
- Attached the IAM role having full access to the EC2 instance created, Installed and Setup Kubectl,eksctl and helmchart using curl, installed Kubernetes Metrics Server using kubectl, Verified that the metrics-server deployment is running the desired number of pods, installed Prometheus using helm, created prometheus namespace and installed Prometheus using helm, created IAM OIDC Provider, iamserviceaccount with role, Then attached ROLE to eks, now prometheus is created. Created Grafana using helm, Now I have created a Prometheus data source so that Grafana can access the Kubernetes metrics, Now Grafana dashboard also created. Import Grafana custom Dashboard using 6417. Load and select the source as Prometheus, Now I can Visualise the Laravel application
- created manifest files for kubernetes deployment. Please check in the repository from above mentioned Github url.

- Finally In github created a Repo, clone the url in local, created remote origin, created branch, added all the files created, commited the change with a commit message, pushed the change to github.
