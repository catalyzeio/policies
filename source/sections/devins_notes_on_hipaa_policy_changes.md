# Devins Notes on HIPAA Policy Changes

* removed data management policy because it is concerned with hipaa backups, so it is irrelevant to us.
* recommend removing inheritance tables for catalyze style customers and adding a table for our type of customer
* systems access policy contains relevant info for VP of Eng, Sec. Officer, and Priv. Officer.
* removed PaaS access section from systems access policy because Agathos doesn't have PaaS customers.
e
* removed Catalyze-specific methods in configuration policy. Recommend further addition to configuration policy with Agathos-specific management methods.
* "./incident.form.pdf" appears to be missing from the catalyze documents
* removed PaaS section from breach policy
* removed specifics from vulnerability scanning

## To Do:
* update policy index
* update/build policy front-end
* create inheritance table for AaaS customers
* **policy management policy**:
	* publish policies and update link
	* create policy change form and update link
	* create policy review form and update link
	* create Slack channel that logs changes to policy repo via github
	* look into HITRUST CSF
* **systems access policy**:
	* Appoint Privacy Officer and Security Officer
	* account review form
	* change of access form
	* implement two factor Authentication for all agathos systems
	* remind team that no generic accounts should be used
	* S/O create list of pre-approved personal devices
	* all devices must use Filevault 2.0, firewalls
* **configuration management policy**:
	* Add to configuration management policy with agathos specific methods and tools.
	* **Implement unit tests in all production code.**
* **incident response policy**:
	* implement incident response form and add link
	* find incident identification form and include it in the sources folder.
* **breach policy**:
	* update "breach.log.pdf"
* **vulnerability scanning**
	* choose a method for vulnerability scanning and possibly use 3rd party scanning.
