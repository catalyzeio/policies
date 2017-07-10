# 21. 3rd Party Policy

BIND makes every effort to assure all 3rd party organizations are compliant and do not compromise the integrity, security, and privacy of Datica or Datica Customer data. 3rd Parties include Customers, Partners, Subcontractors, and Contracted Developers.

## 21.1 Applicable Standards

## 21.1.1 Applicable Standards from the HITRUST Common Security Framework

*  05.i - Identification of Risks Related to External Parties
*  05.k - Addressing Security in Third Party Agreements
*  09.e - Service Delivery
*  09.f - Monitoring and Review of Third Party Services
*  09.g - Managing Changes to Third Party Services
*  10.1 - Outsourced Software Development

## 21.1.2 Applicable Standards from the HIPAA Security Rule

* 164.314(a)(1)(i) - Business Associate Contracts or Other Arrangements

## 21.2 Policies to Assure 3rd Parties Support Datica Compliance

1. The following steps are required before 3rd parties are granted access to any Datica systems:
	* Due diligence with the 3rd party;
	* Controls implemented to maintain compliance;
	* Written agreements, with appropriate security requirements, are executed.
2. All connections and data in transit between the Datica Platform and 3rd parties are encrypted end to end.
3. Access granted to external parties is limited to the minimum necessary and granted only for the duration required.
4. A standard business associate agreement with Customers and Partners is defined and includes the required security controls in accordance with the organization’s security policies. Additionally, responsibility is assigned in these agreements.
5. Bind has Service Level Agreements (SLAs) with Subcontractors with an agreed service arrangement addressing liability, service definitions, security controls, and aspects of services management.
   * Subcontractors must coordinate, manage, and communicate any changes to services provided to Bind.
   * Changes to 3rd party services are classified as configuration management changes and thus are subject to the policies and procedures described in [§9](#9.-configuration-management-policy); substantial changes to services provided by 3rd parties will invoke a Risk Assessment as described in [§4.2](#4.2-risk-management-policies).
   * Bind utilizes monitoring tools to regularly evaluate Subcontractors against relevant SLAs.
6. No Bind Customers or Partners have access outside of their own environment, meaning they cannot access, modify, or delete anything related to other 3rd parties.
7. Whenever outsourced development is utilized by Bind, all changes to production systems will be approved and implemented by Bind workforce members only. All outsourced development requires a formal contract with Bind.
8. Bind maintains and annually reviews a list all current Partners and Subcontractors.
   * The list of current Partners and Subcontractors is maintained by the Bind Privacy Officer, includes details on all provided services (along with contact information), and is recorded in [§1.4](#1.4-datica-organizational-concepts).
   * The annual review of Partners and Subcontractors is conducted as a part of the security, compliance, and SLA review referenced below.
10. Bind assesses security requirements and compliance considerations with all Partners and Subcontracts. This includes annual assessment of SOC2 Reports for all Bind infrastructure partners.
  * Bind leverages recurring calendar invites to assure reviews of SLAs with all 3rd parties are performed annually. These are performed by the Bind Security Officer and Privacy Officer. Jira issues and forms stored in Dropbox are used to track such reviews. The process for reviewing 3rd party services is outlined below:
     1. The Security Officer initiates the SLA review by creating a "SLA Review" Issue type in the JIRA Security (SEC) Project.
     2. The Security Officer, or Privacy Officer, is assigned to review the SLA and performance of 3rd parties. The list of current 3rd parties, including contact information, is also reviewed to assure it is up to date and complete.
     3. SLA, security, and compliance performance is documented in the Issue.
     4. Once the review is completed and documented, the Security Officer approves or rejects the Issue. If the Issue is rejected, it goes back for further review and documentation.
11. Regular review is conducted as required by SLAs to assure security and compliance. These reviews include reports, audit trails, security events, operational issues, failures and disruptions, and identified issues are investigated and resolved in a reasonable and timely manner.

13. Any changes to Partner and Subcontractor services and systems are reviewed before implementation.
14. For all partners, Bind reviews activity annually to assure partners are in line with SLAs in contracts with Bind.
15. SLA review is monitored on a quarterly basis using JIRA reporting to assess compliance with above policy.
