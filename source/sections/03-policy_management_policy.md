# 3. Policy Management Policy

Bind implements policies and procedures to maintain compliance and integrity of data. The Security Officer and Privacy Officer are responsible for maintaining policies and procedures and assuring all Bind workforce members, business associates, customers, and partners are adherent to all applicable policies. Previous versions of policies are retained to assure ease of finding policies at specific historic dates in time.

## 3.1 Applicable Standards

## 3.1.1 Applicable Standards from the HITRUST Common Security Framework

* 12.c - Developing and Implementing Continuity Plans Including Information Security

## 3.1.2 Applicable Standards from the HIPAA Security Rule

* 164.316(a) - Policies and Procedures
* 164.316(b)(1)(i) - Documentation

## 3.2 Maintenance of Policies

1. All policies are stored and up to date to maintain Bind compliance with HIPAA, HITRUST, NIST, and other relevant standards. Updates and version control are done similar to source code control.
2. Policy update requests can be made by any workforce member at any time. Furthermore, all policies are reviewed annually by both the Security and Privacy Officer to assure they are accurate and up-to-date.
3. Bind employees may request changes to policies using the following process:
  1. The Bind employee initiates a policy change request by creating a "Compliance Review Activity Issue type in the JIRA Security (SEC) project. The change request may optionally include a GitHub pull request from a separate branch or repository containing the desired changes.
  2. The Security Officer or the Privacy Officer is assigned to review the policy change request.
  3. Once the review is completed, the Security Officer approves or rejects the Issue. If the Issue is rejected, it goes back for further review and documentation.
  4. If the review is approved, the Security Officer then marks the Issue as Done, adding any pertinent notes required.
  5. If the policy change requires technical modifications to production systems, those changes are carried out by authorized personnel using Bind's [change management process (§9.4)](#9.4-changing-existing-systems).
4. All policies are made accessible to all Bind workforce members. The current master policies are published [here](https://policy.yourbind.com).  TODO: determine if we get here or just publish to a Notion page.
   * Changes are automatically communicated to all Bind team members through integrations between GitHub and Slack that log all GitHub policy channels to a dedicated Bind Slack Channel.  TODO: determine if easy to hook-up at this point - #bind-privacy-and-security
   * The Security Officer also communicates policy changes to all employees via email. These emails include a high-level description of the policy change using terminology appropriate for the target audience.
5. All policies, and associated documentation, are retained for 6 years from the date of its creation or the date when it last was in effect, whichever is later
  1. Version history of all Bind policies is done via Github.
  2. Backup storage of all policies is done with Dropbox.
6. The policies and information security policies are reviewed and audited annually. Issues that come up as part of this process are reviewed by Bind management to assure all risks and potential gaps are mitigated and/or fully addressed. The policy review form can be found [here](https://docs.google.com/a/catalyze.io/forms/d/1kuyIYA-Z-tmRdfMwrVMl59BujIy9y1dyjMSd8_Wy760/viewform) TODO: Create Notion page to memorialize the review process.

6. The policies and information security policies are reviewed and audited annually, or after significant changes occur to Bind's organizational environment. Issues that come up as part of this process are reviewed by Bind management to assure all risks and potential gaps are mitigated and/or fully addressed. The process for reviewing polices is outlined below:
  1. The Security Officer initiates the policy review by creating a "Compliance Review Activity" Issue type in the JIRA Security (SEC) project.
  2. The Security Officer or the Privacy Officer is assigned to review the current Bind policies ([https://policy.yourbind.com/](https://policy.yourbind.com/)).
  3. If changes are made, the above process is used. All changes are documented in the Issue.
  4. Once the review is completed, the Security Officer approves or rejects the Issue. If the Issue is rejected, it goes back for further review and documentation.
  5. If the review is approved, the Security Officer then marks the Issue as Done, adding any pertinent notes required.
  6. Policy review is monitored on a quarterly basis using JIRA reporting to assess compliance with above policy.
7. Bind utilizes the HITRUST MyCSF framework to track compliance with the HITRUST CSF on an annual basis. Bind also tracks compliance with HIPAA and publishes results at [https://hipaa.yourbind.com](https://hipaa.yourbind.com). In order to track and measure adherence on an annual basis, Bind uses the following process to track HITRUST audits, both full and interim:  TODO:  HITRUST MyCSF framework 1st steps
  1. The Security Officer initiates the HITRUST audit activity by creating a "Compliance Review Activity" Issue type in the JIRA Security (SEC) project.
  2. The Security Officer or the Privacy Officer is assigned to own and manage the HITRUST activity.
  3. Once the HITRUST activity is completed, the Security Officer approves or rejects the Issue.
  5. If the review is approved, the Security Officer then marks the Issue as Done, adding any pertinent notes required.
  6. Compliance with annual compliance assessments, utilizing the HITRUST CSF as a framework, is monitored on a quarterly basis using JIRA reporting to assess compliance with above policy.

Additional documentation related to maintenance of policies is outlined in [§5.3.1](#5.3-security-officer).
