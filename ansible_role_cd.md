![Ubuntu Logo](https://i0.wp.com/blog.knoldus.com/wp-content/uploads/2017/10/ansible_logo.png?fit=1800%2C514&ssl=1)

# **Continuous Deployement(CD) Workflow with Ansible Roles**

| Author         | Created on     | Version         | Last updated by | Last edited on | Pre Reviewer | L0 Reviewer | L1 Reviewer | L2 Reviewer |
|----------------|----------------|-----------------|-----------------|----------------|---------------|-------------|-------------|-------------|
| Mohamed Tharik | 2025-04-18     |     Version 1         | Mohamed Tharik  | 2025-04-18     |Priyanshu | Khushi | Mukul Joshi|Piyush Upadhyay |

## Table of Contents

- [What Is an Ansible Role?](#what-is-an-ansible-role)
- [CD Workflow with Ansible Role – Step-by-Step](#cd-workflow-with-ansible-role--step-by-step)
  - [Code Pushed to Repository](#1-code-pushed-to-repository)
  - [CI Pipeline Runs (Optional)](#2-ci-pipeline-runs-optional)
  - [CD Pipeline Starts](#3-cd-pipeline-starts)
  - [Ansible Role Gets Executed](#4-ansible-role-gets-executed)
  - [Configuration and Deployment](#5-configuration-and-deployment)
  - [Notification](#6-notification)
- [Benefits of Using Roles in CD](#benefits-of-using-roles-in-cd)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [Reference](#reference)


## **What Is an Ansible Role?**

An Ansible Role is a structured, reusable unit of automation in Ansible. It helps you organize playbooks by grouping related tasks, variables, files, templates, and handlers into a clean directory layout.
An Ansible role has a standard directory structure:
```text
my-role/
├── tasks/
├── handlers/
├── templates/
├── files/
├── vars/
├── defaults/
├── meta/
```
## CD Workflow with Ansible Role – Step-by-Step
![image](https://github.com/user-attachments/assets/722cbe87-cbd3-4d13-ae42-1bc89c923efa)

- ### 1. Code Pushed to Repository
      - A developer makes changes to the application code.

      - Commits and pushes the code to a version control system like GitHub, GitLab, or Bitbucket.

      - This action acts as a trigger for the CI/CD pipeline to begin.

- ### 2. CI Pipeline Runs
- The CI (Continuous Integration) pipeline is triggered to validate the code:
Steps usually included in CI:

|Step | Description|
|------|------------|
|Linting | Checks for syntax/style errors (e.g., flake8 for Python, eslint for JS).|
|Testing | Runs unit tests, integration tests using tools like pytest, JUnit, etc.|
|Build | Compiles code, builds Docker images, JAR files, etc.|
|Artifact Storage | Saves the output (e.g., JAR, ZIP, Docker image) to a central location like S3, Nexus, Artifactory, or Docker Hub.|
  
- ### 3. CD Pipeline Starts
Now begins the CD (Continuous Deployment) process using Ansible.

  - The CI/CD tool (Jenkins, GitLab CI, etc.) runs an Ansible playbook that defines deployment logic using roles.
  - It connects to target servers (e.g., EC2 instances) and performs tasks automatically.


- ### 4. Ansible Role Gets Executed
Each Ansible Role is a small, reusable unit that does one job. These roles are called one by one in the playbook.

|Role | What It Does|
|-------|-------------|
|install_nginx | Installs Nginx, configures Nginx.conf, starts the service.|
|deploy_web_app | Pulls the code/artifact, copies to server, sets permissions, restarts app.|

- ### 5. Configuration and Deployment
The Ansible role:

  - Pulls artifacts from a remote repo (e.g., from S3 or Jenkins)
  - Copies files to target servers
  - Runs commands/scripts
  - Restarts services if needed
  - Handles rollback if something fails

- ### 6. Notification
Once the deployment is done, the CD pipeline sends a notification:

Tools Used:

  - Slack – Notifies DevOps/dev team of success/failure
  - Email – Sends logs or status
  - Jira/Webhooks – For auto-updating issues

## Benefits of Using Roles in CD
- Reusable and modular
- Easier to test and maintain
- Better separation of concerns
- Works well with Jenkins, GitLab CI, and other CD tools
- Roles can be versioned and stored in a central repo (e.g., Ansible Galaxy, Git)

## Conclusion
Ansible roles in a CD pipeline automate tasks like:

- Provisioning servers
- Deploying apps
- Configuring services
- Rolling back if needed

They bring structure, reusability, and reliability to your deployments.

## Contact Information

| Name | Email address         |
|------|------------------------|
| Mohamed Tharik  | md.tharik.sanaatak@mygurukulam.co    |

## Reference

| Links                                                                                                                                                                                                                     | Descriptions                                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|[Understanding of CI/CD Workflow](https://medium.com/@shadaabsikander/ci-cd-pipeline-with-jenkins-ansible-git-apache-7e624dbac00b) |In this we can understand the CI/CD workflow of how Ansible Roles is used| 

