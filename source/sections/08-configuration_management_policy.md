# 8. Configuration Management Policy

WatchTower standardizes and automates configuration management through the use of AWS OpsWorks scripts as well as documentation of all changes to production systems and networks. AWS OpsWorks automatically configures all WatchTower systems according to established and tested policies, and are used as part of our Disaster Recovery plan and process.

## 8.1 Applicable Standards

### 8.1.1 Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## 8.2 Configuration Management Policies

1. AWS OpsWorks is used to standardize and automate configuration management.
2. No systems are deployed into WatchTower environments without approval of the WatchTower CTO.
3. All changes to production systems, network devices, and firewalls are approved by the WatchTower CTO before they are implemented to assure they comply with business and security requirements.
4. All changes to production systems are tested before they are implemented in production.
5. Implementation of approved changes are only performed by authorized personnel.
7. All frontend functionality (developer dashboards and portals) is separated from backend (database and app servers) systems by being deployed on separate servers or containers.
8. All software and systems are tested using unit tests and end to end tests.
9. All committed code is reviewed using pull requests to assure software code quality and proactively detect potential security issues in development.
10. WatchTower utilizes development and staging environments that mirror production to assure proper function.
12. All formal change requests require unique ID and authentication.
14. Clocks are continuously synchronized to an authoritative source across all systems using NTP or a platform-specific equivalent. Modifying time data on systems is restricted.

## 8.3 Provisioning Production Systems

1. Before provisioning any systems, ops team members must file a request in the WatchTower Quality Management System.
   * Quality Management System access requires authenticated users.
   * The CTO grants access to the Quality Management System following the procedures covered in the [Access Establishment and Modification section](#6.2-access-establishment-and-modification).
2. The CTO, or an authorized delegate of the CTO, must approve the provisioning request before any new system can be provisioned.
3. Once provisioning has been approved, the ops team member must configure the new system according to the standard baseline chosen for the system's role.
4. If the system will be used to house production data (ePHI), the ops team member must add an encrypted block data volume to the VM during provisioning.
   * For systems on AWS, the ops team member must add an encrypted Elastic Block Storage (EBS) volume.
5. Once the system has been provisioned, the ops team member must contact the security team to inspect the new system. A member of the security team will verify that the secure baseline has been applied to the new system, including (but not limited to) verifying the following items:
   * Removal of default users used during provisioning.
   * Network configuration for system.
   * Data volume encryption settings.
   * Intrusion detection and virus scanning software installed.
   * All items listed below in the operating system-specific subsections below.
7. The new system may be rotated into production once the CTO verifies all the provisioning steps listed above have been correctly followed and has marked the Issue with the `Approved` state.

## 8.4 Changing Existing Systems

1. Subsequent changes to already-provisioned systems are unconditionally handled by one of the following methods:
   * Changes to Salt states or pillar values.
   * Changes to Chef recipes.
   * For configuration changes that cannot be handled by Chef or Salt, a runbook describing exactly what changes will be made and by whom.
2. Configuration changes to Chef recipes or Salt states must be initiated by creating a Merge Request in GitLab.
   * The ops team member will create a feature branch and make their changes on that branch.
   * The ops team member must test their configuration change locally when possible, or on a development and/or staging sandbox otherwise.
   * At least one other ops team member must review the Chef or Salt change before merging the change into the main branch.
3. In all cases, before rolling out the change to production, the ops team member must file an Issue in the DT project describing the change. This Issue must link to the reviewed Merge Request and/or include a link to the runbook.
4. Once the request has been approved by the CTO, the ops team member may roll out the change into production environments.

## 8.5 Patch Management Procedures

1. WatchTower uses automated tooling to ensure systems are up-to-date with the latest security patches.
2. On Ubuntu Linux systems, the unattended-upgrades tool is used to apply security patches in phases.
   * The security team maintains a mirrored snapshot of security patches from the upstream OS vendor. This mirror is synchronized bi-weekly and applied to development systems nightly.
   * If the development systems function properly after the two-week testing period, the security team will promote that snapshot into the mirror used by all staging systems. These patches will be applied to all staging systems during the next nightly patch run.
   * If the staging systems function properly after the two-week testing period, the security team will promote that snapshot into the mirror used by all production systems. These patches will be applied to all production systems during the next nightly patch run.
   * Patches for critical kernel security vulnerabilities may be applied to production systems using hot-patching tools at the discretion of the Security and Privacy Officer. These patches must follow the same phased testing process used for non-kernel security patches; this process may be expedited for severe vulnerabilities.
3. On Windows systems, the baseline Group Policy setting configures Windows Update to implement the patching policy.

## 8.6 Software Development Procedures

1. All development uses feature branches based on the main branch used for the current release. Any changes required for a new feature or defect fix are committed to that feature branch.
   * These changes must be covered under 1) a unit test where possible, or 2) integration tests.
   * Integration tests are _required_ if unit tests cannot reliably exercise all facets of the change.
2. Developers are strongly encouraged to follow the [commit message conventions suggested by GitHub](https://github.com/blog/926-shiny-new-commit-styles).
   * Commit messages should be wrapped to 72 characters.
   * Commit messages should be written in the present tense. This convention matches up with commit messages generated by commands like git merge and git revert.
3. Once the feature and corresponding tests are complete, a pull request will be created using the GitHub/GitLab web interface. The pull request should indicate which feature or defect is being addressed and should provide a high-level description of the changes made.
4. Code reviews are performed as part of the pull request procedure. Once a change is ready for review, the author(s) will notify other engineers using an appropriate mechanism, typically via an `@channel` message in Slack.
   * Other engineers will review the changes, using the guidelines above.
   * Engineers should note all potential issues with the code; it is the responsibility of the author(s) to address those issues or explain why they are not applicable.
5. Once the review process finishes, each reviewer should leave a comment on the pull request saying "looks good to me" (often abbreviated as "LGTM"), at which point the original author(s) may merge their change into the release branch.

## 8.7 Software Release Procedures

1. Software releases are treated as changes to existing systems and thus follow the procedure described in [§7.4](#7.4-changing-existing-systems).
