# Configuration Management Policy

Agathos is reviewing configuration management strategies. Configuration management is currently done manually and subject to approval of the Security Officer or the VP of Engineering.

## Applicable Standards from the HITRUST Common Security Framework

* 06 - Configuration Management

## Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## Configuration Management

1. No systems are deployed into Agathos environments without approval of the Agathos CTO or the Security Officer.
2. All changes to production systems, network devices, and firewalls are approved by the Agathos CTO or the Security Officer before they are implemented to assure they comply with business and security requirements. Additionally, all changes are tested before they are implemented in production. Implementation of approved changes are only performed by authorized personnel.
3. All software and systems are tested using unit tests and end to end tests.
4. All committed code is reviewed using pull requests (on Github) to assure software code quality and proactively detect potential security issues in development.
5. Agathos utilizes development and staging environments that mirror production to assure proper function.
6. Agathos schedules production deployments every two weeks.
7. All physical media is encrypted at provisioning. To verify encryption is consistent and in place for all production storage, checks are performed on a quarterly basis.
