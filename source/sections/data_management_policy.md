# Data Management Policy

Bind has procedures to create and maintain retrievable exact copies of electronic protected health information (ePHI) stored in conjunction with Bind ODHI Employer Health Insurance and PaaS Customers.  The policy and procedures will assure that complete, accurate, retrievable, and tested backups are available for all systems used by Bind.

Data backup is an important part of the day-to-day operations of Bind. To protect the confidentiality, integrity, and availability of ePHI, both for Bind and Bind Customers, completes backups are done daily to assure that data remains available when it needed and in case of disaster or ransom threat.

Violation of this policy and its procedures by workforce members may result in corrective disciplinary action, up to and including termination of employment.

## Applicable Standards from the HITRUST Common Security Framework

* 01.v - Information Access Restriction

## Applicable Standards from the HIPAA Security Rule

* 164.308(a)(7)(ii)(A) - Data Backup Plan
* 164.310(d)(2)(iii) - Accountability
* 164.310(d)(2)(iv) - Data Backup and Storage

## Backup Policy and Procedures

1. Perform daily snapshot backups of all systems that process, store, or transmit ePHI for Bind Customers, including PaaS Customers.
2. Bind Ops Team, lead by Chief Technology Officer, is designated to be in charge of backups.
3. Dev Ops Team members are trained and assigned assigned to complete backups and manage the backup data. TODO: We need to look into Aurora DB backup process (and/or the multi-AZ/Region option to turn on continuouse backup from a read cluster)
4. Document backups . TODO:  put details here on what/how or reference a Notion page from here that details
	* Name of the system
	* Date & time of backup
	* Where backup stored (or to whom it was provided)
5. Securely encrypt stored backups in a manner that protects them from loss or environmental damage.
6. Test backups and document that files have been completely and accurately restored from the backup media.
