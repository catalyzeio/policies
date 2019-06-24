# 9. Configuration Management Policy

Cloudticity standardizes and automates configuration management through the use of Chef/userdata scripts as well as documentation of all changes to production systems and networks. Chef and userdata scripts automatically configure all Cloudticity systems according to established and tested policies, and are used as part of our Disaster Recovery plan and process.

## 9.1 Applicable Standards

### 9.1.1 Applicable Standards from the HITRUST Common Security Framework

* 06 - Configuration Management
* 09.af - Clock Synchronization

### 9.1.2 Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## 9.2 Configuration Management Policies

1. Chef, SSM, and userdata shell/powershell scripts are used to standardize and automate configuration management.
2. No systems are deployed into Cloudticity environments without approval of the Cloudticity CTO.
3. All changes to production systems, network devices, and firewalls are approved by the Cloudticity CTO before they are implemented to assure they comply with business and security requirements.
4. All changes to production systems are tested before they are implemented in production.
5. Implementation of approved changes are only performed by authorized personnel.
6. Tooling to generate an up-to-date inventory of systems is located in Cloudcheckr.
   * All systems are labelled using tags to differentiate resources based on criticality and sensitivity.
   * Cloudcheckr is used to generate the inventory lists and asset lists required by the Risk Assessment phase of Cloudticity's Risk Management procedures ([§4.3.1](04-risk_management_policy.md#431-risk-assessment)).
7. All frontend functionality (developer dashboards and portals) is separated from backend (database and app servers) systems by being deployed on separate servers or containers.
8. All software and systems are tested using unit tests and end to end tests.
9. All committed code is reviewed using pull requests to assure software code quality and proactively detect potential security issues in development.
10. Cloudticity utilizes, where appropriate, development and staging environments that mirror production to assure proper function.
11. Cloudticity also deploys environments locally using the Serverless framework to assure functionality before moving to staging or production.
12. All formal change requests require unique ID and authentication.
13. Cloudticity uses the [Security Technical Implementation Guides (STIGs)](http://iase.disa.mil/stigs/) published by the Defense Information Systems Agency as a baseline for hardening systems.
    * Windows-based systems use a baseline configuration in conjunction with the Windows Server 2012 STIG.
    * Linux-based systems use a Red Hat Enterprise Linux STIG.
14. Clocks are continuously synchronized to an authoritative source across all systems using NTP or a platform-specific equivalent. Modifying time data on systems is restricted.
15. Any vendor software which is non-supported will be replaced where possible or if not possible a plan for migration will be developed

## 9.3 Provisioning Production Systems

1. Before provisioning any systems, ops team members must have an assigned task in an active project that requires resource provisioning.
   * Teamwork access requires authenticated users.
   * The CTO grants access to Teamwork following the procedures covered in the [Access Establishment and Modification section](07-systems_access_policy.md#72-access-establishment-and-modification).
2. The CTO must approve the provisioning request before any new system can be provisioned.
3. Once provisioning has been approved, the ops team member must configure the new system according to the standard baseline chosen for the system's role.
   * For instance configuration, this means adding the appropriate changes to the userdata scripts and running an `update` operation on the product or resource.
   * For application configuration, this means adding the appropriate changes to the userdata scripts and running an `update` operation on the product or resource or adding the appropriate roles to the system's Chef profile and forcing a Chef run.
4. If the system will be used to house production data (ePHI), the ops team member must add an encrypted Elastic Block Storage (EBS) volume to the VM during provisioning.
5. Once the system has been provisioned, the ops team member must inspect, or have another workforce member inspect, the new system. Verification that the secure baseline has been applied to the new system, included (but is not limited to) verifying the following items:
   * Removal of default users used during provisioning.
   * Network configuration for system.
   * Data volume encryption settings.
   * Intrusion detection and virus scanning software installed.
   * All items listed in the operating system-specific subsections.
6. The new system may be rotated into production once the CTO verifies all the provisioning steps listed above have been correctly followed and has marked the task as Complete.

### 9.3.1 Provisioning Linux Systems

1. Linux systems have their baseline security configuration applied via userdata shell scripts, SSM, or Chef. These baseline states cover:
   * Ensuring that the machine is up-to-date with security patches and is configured to apply patches in accordance with our policies.
   * Stopping and disabling any unnecessary OS services.
   * Installing and configuring the TMDS agent.
   * Installing and configuring the NTP daemon, including ensuring that modifying system time cannot be performed by unprivileged users.
   * Configuring audit logging as described in [§8](08-auditing_policy.md#82-auditing-policies).
2. Any additional states applied to the Linux system must be clearly documented by the ops team member in the DT request by specifying the purpose of the new system.

### 9.3.2 Provisioning Windows Systems

1. Windows systems have their baseline security configuration applied via userdata powershell scripts, SSM, or Chef. These baseline settings cover:
   * Ensuring that the machine is up-to-date with security patches and is configured to apply patches in accordance with our policies.
   * Stopping and disabling any unnecessary OS services.
   * Installing and configuring the TMDS agent.
   * Configuring the system clock, including ensuring that modifying system time cannot be performed by unprivileged users.
   * Configuring audit logging as described in [§8](08-auditing_policy.md#82-auditing-policies).
2. Any additional states applied to the Windows system must be clearly documented by the ops team member in the DT request by specifying the purpose of the new system.

### 9.3.3 Provisioning Management Systems

1. Provisioning management systems such as LDAP servers or VPN appliances follows the same procedure as [provisioning a production system](09-configuration_management_policy.md#93-provisioning-production-systems).

## 9.4 Changing Existing Systems

1. Subsequent changes to already-provisioned systems are unconditionally handled by one of the following methods:
   * Changes to userdata scripts.
   * Changes to Chef recipes.
   * For configuration changes that cannot be handled by Chef or userdata, a runbook describing exactly what changes will be made and by whom.
2. Configuration changes to Chef recipes or userdata states must be initiated by creating a pull request in Github.
   * The ops team member will create a feature branch and make their changes on that branch.
   * The ops team member must test their configuration change locally when possible, or otherwise on a development and/or staging sandbox.
   * At least one other ops team member must review the Chef or userdata change before merging the change into the main branch.
3. Once the request has been approved by the CTO, the ops team member may roll out the change into production environments.

## 9.5 Patch Management Procedures

1. Cloudticity uses automated tooling to ensure systems are up-to-date with the latest security patches.

## 9.6 Software Development Procedures

1. All development uses feature branches based on the main branch used for the current release. Any changes required for a new feature or defect fix are committed to that feature branch.
   * These changes must be covered under 1) a unit test where possible, or 2) integration tests.
   * Integration tests are _required_ if unit tests cannot reliably exercise all facets of the change.
2. Developers are strongly encouraged to follow the [commit message conventions suggested by GitHub](https://github.com/blog/926-shiny-new-commit-styles).
   * Commit messages should be wrapped to 72 characters.
   * Commit messages should be written in the present tense. This convention matches up with commit messages generated by commands like git merge and git revert.
3. Once the feature and corresponding tests are complete, a pull request will be created using the GitHub web interface. The pull request should indicate which feature or defect is being addressed and should provide a high-level description of the changes made.
4. Code reviews are performed as part of the pull request procedure. Once a change is ready for review, the author(s) will notify other engineers using an appropriate mechanism, typically via an `@here` message in Slack.
   * Other engineers will review the changes, using the guidelines above.
   * Engineers should note all potential issues with the code; it is the responsibility of the author(s) to address those issues or explain why they are not applicable.
5. If the feature or defect interacts with ePHI, or controls access to data potentially containing ePHI, the code changes must be reviewed by the Security Officer before the feature is marked as complete.
   * This review must include a security analysis for potential vulnerabilities such as those listed in the [OWASP Top 10](https://www.owasp.org/index.php/Top10).
   * This review must also verify that any actions performed by authenticated users will generate appropriate audit log entries.
6. Once the review process finishes, each reviewer should leave a comment on the pull request saying "looks good to me" (often abbreviated as "LGTM"), at which point the original author(s) may merge their change into the release branch.

## 9.7 Software Release Procedures

1. Software releases are treated as changes to existing systems and thus follow the procedure described in [§9.4](09-configuration_management_policy.md#94-changing-existing-systems).
