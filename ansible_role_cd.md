![Ubuntu Logo](https://i0.wp.com/blog.knoldus.com/wp-content/uploads/2017/10/ansible_logo.png?fit=1800%2C514&ssl=1)

# **Ansible Role in Continuous Deployement(CD)**

| Author         | Created on     | Version         | Last updated by | Last edited on | Pre Reviewer | L0 Reviewer | L1 Reviewer | L2 Reviewer |
|----------------|----------------|-----------------|-----------------|----------------|---------------|-------------|-------------|-------------|
| Mohamed Tharik | 2025-04-18     |     Version 1         | Mohamed Tharik  | 2025-04-18     |Priyanshu | Khushi | Mukul Joshi|Piyush Upadhyay |

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

- ### 1. Code Pushed to Repository
A developer pushes code changes to GitHub/GitLab/Bitbucket.

- ### 2. CI Pipeline Runs (Optional)
  - Linting, unit tests, or build steps might run in a CI pipeline (e.g., Jenkins, GitHub Actions).

  - Artifacts (e.g., JAR files, Docker images) are stored if needed.

- ### 3. CD Pipeline Starts
The CD tool (e.g., Jenkins, GitLab CI) triggers the Ansible playbook that includes roles.
```yaml
- hosts: webservers
  become: yes
  roles:
    - { role: install_nginx }
    - { role: deploy_web_app }
```
- ### 4. Ansible Role Gets Executed
Each role performs a specific task:

|Role Name | Purpose|
|-----------|---------|
|install_nginx | Installs and configures Nginx|
|----------------|------------------------------|
|deploy_web_app | Copies code, sets permissions, restarts services|

- ### 5. Configuration and Deployment
The Ansible role:

  - Pulls artifacts from a remote repo (e.g., from S3 or Jenkins)
  - Copies files to target servers
  - Runs commands/scripts
  - Restarts services if needed
  - Handles rollback if something fails

- ### 6. Notification
Optionally, the pipeline sends notifications (Slack, email) after successful/failed deployment.

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

## References

| Links                                                                                                                                                                                                                     | Descriptions                                                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|

