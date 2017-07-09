# Configuration Management Policy

Bind standardizes and automates an infrastructure as code (IAC) through the use of [Packer](https://www.packer.io/) machine image building and [Terraform](https://www.terraform.io/) delivered via [Docker](https://www.docker.com/) containers into [AWS EC2 Container Service (ECS)](https://aws.amazon.com/ecs/) as well as documentation of all changes to production systems and networks. These technologies automatically configure all Bind systems according to established and tested policies, and are used as part of our Disaster Recovery plan and process.

## Applicable Standards from the HITRUST Common Security Framework

* 06 - Configuration Management

## Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## Configuration Management

1. Packer, Terraform, and Docker are used to standardize and automate configuration management.
2. Threat Stack is used to continuously scan and monitor systems. This continuous monitoring capture file system changes and also unauthorized or malicious software. AS well as AWS configuration and vulnerability scanning on a daily basis.
3. No systems are deployed into Bind environments without approval of the Bind CTO.  TODO:  Review what statement we want on "approval" (change control) - (1) add "Production systems" or (2) based on continuous delivery methodology and deployment pipeline requirements and change approval by the CTO and Security Officer or (3) ??
4. All changes to production systems, network devices, and firewalls are approved by the Bind CTO and/or Security Officer before they are implemented to assure they comply with business and security requirements. Additionally, all changes are tested before they are implemented in production. All changes are documented using issues filed in the "Deployment Ticket" JIRA project. Implementation of approved changes are only performed by authorized personnel.
5. An up-to-date inventory of systems is maintained using including architecture diagrams hosted on Bind's internal wiki and Dropbox. All systems are categorized as production and utility to differentiate based on criticality.  TODO: create this Notion page for system inventory
6. Clocks are synchronized across all systems using NTP. Modifying time data on systems is restricted.  TODO:  ask/confirm this with research & Gruntwork
7. All front-end functionality (developer dashboards and portals) is separated from backend (database and app servers) systems by being deployed on separate servers.
8. All software and systems are tested using unit tests and end to end functional automated tests thorugh the use of [Jenkins](https://jenkins.io/), a continuous build and deployment solution.
9. All committed code is reviewed using pull requests (on Github) to assure software code quality and proactively detect potential security issues in development.
10. Bind utilizes development and staging environments that mirror production to assure proper security, scale, and function.
11. Bind also deploys environments locally using Docker to assure functionality before moving to staging or production.  These containers are the same that make their way to Production through the deployment pipelines via Jenkins.
12. Bind schedules production deployments in a continuous fashion, only when all manual and automated deployment pipeline activities pass for a given commit and container image.
13. All formal change requests require unique ID and authentication.
14. All physical media is encrypted at provisioning.  All internal communication between services is secured via TLS.  To verify encryption is consistent and in place for all staging and production storage and service communication, checks are performed on a quarterly basis.  TODO:  put this on a shared calendar as reminder for some type of Jira task/story 
