# 6. Data Management Policy

CareJourney has procedures to create and maintain retrievable exact copies of electronic protected health information (ePHI) stored in conjunction with CareJourney Add-ons and for PaaS Customers utilizing our Backup Service. This policy, and associated procedures for testing and restoring from backup data, do not apply to PaaS Customers that do not choose CareJourney Backup Service. The policy and procedures will assure that complete, accurate, retrievable, and tested backups are available for all systems used by CareJourney.

Data backup is an important part of the day-to-day operations of CareJourney. To protect the confidentiality, integrity, and availability of ePHI, both for CareJourney and CareJourney Customers, complete backups are done daily to assure that data remains available when needed and in case of a disaster.

Violation of this policy and its procedures by workforce members may result in corrective disciplinary action, up to and including termination of employment.

## 6.1 Applicable Standards

### 6.1.1 Applicable Standards from the HITRUST Common Security Framework

* 01.v - Information Access Restriction

### 6.1.2 Applicable Standards from the HIPAA Security Rule

* 164.308(a)(7)(ii)(A) - Data Backup Plan
* 164.310(d)(2)(iii) - Accountability
* 164.310(d)(2)(iv) - Data Backup and Storage

## 6.2 Backup Policy and Procedures

1. Perform daily snapshot backups of all systems that process, store, or transmit ePHI for CareJourney Customers, including PaaS Customers that utilize the CareJourney Backup Service.
2. The CareJourney Ops Team is designated to be in charge of backups.
3. Dev Ops Team members are trained and assigned to complete backups and manage the backup media.
4. Document backups
   * Name of the system
   * Date & time of backup
   * Where backup stored (or to whom it was provided)
5. Securely encrypt stored backups in a manner that protects them from loss or environmental damage.
6. Test backups annually and document that files have been completely and accurately restored from the backup media.
