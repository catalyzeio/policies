# Data Management Policy

Bind has procedures to create and maintain retrievable exact copies of electronic protected health information (ePHI) stored in conjunction with Bind Add-ons and for PaaS Customers utilizing our Backup Service. This policy, and associated procedures for testing and restoring from backup data, do not apply to PaaS Customers that do not choose Bind Backup Service. The policy and procedures will assure that complete, accurate, retrievable, and tested backups are available for all systems used by Bind.

Data backup is an important part of the day-to-day operations of Bind. To protect the confidentiality, integrity, and availability of ePHI, both for Bind and Bind Customers, complete backups are done daily to assure that data remains available when it needed and in case of disaster. Bind uses Amazon RDS services to provide high availability and cross reqion snapshots for data availability and recovery.

Violation of this policy and its procedures by workforce members may result in corrective disciplinary action, up to and including termination of employment.

## Applicable Standards from the HITRUST Common Security Framework

* 01.v - Information Access Restriction

## Applicable Standards from the HIPAA Security Rule

* 164.308(a)(7)(ii)(A) - Data Backup Plan
* 164.310(d)(2)(iii) - Accountability
* 164.310(d)(2)(iv) - Data Backup and Storage

## Backup Policy and Procedures

1. We use automated systems to perform daily snapshot backups of all systems that process, store, or transmit ePHI for Bind Customers, including PaaS Customers that utilize the Bind Backup Service
2. Bind Ops Team, lead by the CTO, is designated to be in charge of backup procedures.
3. Dev Ops Team members are trained and assigned to complete backups and manage the backup media.
