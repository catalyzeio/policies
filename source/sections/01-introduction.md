# 1. Introduction

Bind is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of compliant hosted On-Demand Health Insurance platform used by employers, health insurance companies, health technology vendors, and enterprises, Bind strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by Bind to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Bind Customers.

Bind provides secure and compliant cloud-based software. This hosted software falls into two broad categories: 1) **Employer On-Demand Health Insurance** 2) **On-Demand Health Insurance Platform as a Service (PaaS)**. These Categories are cited throughout polices as Customers in each category inherit different policies, procedures, and obligations from Bind.

## 1.1 Employer On-Demand Health Insurance

Bind Employer On-Demand Health Insurance services cover all third party administration (TPA) aspects for self-insured employers choosing to offer their employees on-demand health insurance. The services offered as part of the Bind On-Demand Health Insurance PaaS currently include: healthcare adapters, data science, provider network, and plan design components. Also included are mobile and web applications used to administer and interact with the services.

Third-Party, add-on services may be available as part of the Bind Platform. Any third-party, or Partner Services, shall be reviewed by Bind to ensure compliance with Bind information and security posture.

## 1.2 On-Demand Health Insurance Platform as a Service (PaaS)

PaaS Customers utilize hosted software and infrastructure from Bind to configure, host, and scale custom developed on-demand health insurance applications and solutions. These customers are deployed into compliant containers run on systems secured and managed by Bind. Bind makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of PaaS Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, Intrusion Detection Systems (IDS) throughout the Platform, etc).

(TODO): needs to align with technology, sales, and marketing
PaaS Customers can opt for a list of Services from Bind, which include Human Experience Service, Operations Service, Micro-Network Service, Plan Design Service, Data Science Service. 

## 1.3 Compliance Inheritance

Bind provides compliant hosted software infrastructure for its Customers. (TODO): Bind plans to conduct a HIPAA compliance audit by a national, 3rd party compliance firm, to validate and map organizational policies and technical settings to HIPAA rules. (TODO)Bind, as a company, and its technology, is in progress of being HITRUST Certified.  Bind's production systems on AWS will also be included in Bind's third-party audits and HITRUST certification when executed.

Bind signs either (1) business associate agreements (BAAs) or (2) sub-contractor agreements with its Customers. These agreements outline Bind obligations and Customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Bind manages various aspects of compliance for Customers. The aspects of compliance that Bind manages for Customers are inherited by Customers, and Bind assumes the risk associated with those aspects of compliance. In doing so, Bind helps Customers achieve and maintain compliance, as well as mitigates Customers risk.

For Employer On Demand Health Insurance customers Bind acts as a business associate.  The self-insured employer customer is the covered entity.  For On Demand PaaS customers, Bind acts as a subcontractor.  And in this case, Bind does not interface with PaaS customer users to obtain or provide access to ePHI. Access to ePHI is through the PaaS customers' application(s).

Certain aspects of compliance cannot be inherited. Because of this, Bind Customers, in order to achieve full compliance or HITRUST Certification, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of Bind.

Mappings of HIPAA Rules to Bind controls and a mapping of what Rules are inherited by Customers, both Employer On Demand Health Insurance and PaaS Customers, are covered in [§2](#2.-hipaa-inheritance).

## 1.4 Bind Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructure and managed by AWS. Bind does not have physical access into the network components. The Bind environment consists of AWS network security and firewalls; AWS application load balancers (ALBs); Java application servers; AWS relational datastore (RDS) database servers; Ubuntu Linux monitoring and management servers; Threat Stack IDS, Vulnerability, and AWS Config Audit services; Docker containers; and developer tool servers running on Ubuntu Linux.

Within the Bind Platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. Bind assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

The data and network segmentation mechanism for AWS uses hosted load balancers that segment data across dedicated Virtual Private Clouds (VPCs) for the Bind platform.

(TODO: confirm with Gruntwork on what we should write into this paragraph)
Additionally, IPtables is used on each each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. Bind has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

In the case of On-Demand Health Insurance Platform as a Service (PaaS), once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into AWS RDS databases through programming logic, such that access to one database server will not present you with the full ePHI spectrum.  (TODO: determine if we should include this DB separation statement, as this might not be the case initially, since we'll have a single Aurora DB RDS instance with a single authN and multiple DBs within the instance)

The bastion host, public application load balancers (ALBs) are externally facing and accessible via the Internet. The internal ALBs, application, and database servers, where the ePHI resides, are located on the internal Bind network and can only be accessed directly over an SSH connection through the bastion host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

All platform components, containers, and operating systems are tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.5 Requesting Audit and Compliance Reports - TODO

Bind, at its sole discretion, shares audit reports, including its HITRUST reports and Corrective Action Plans (CAPs), with customers on a case by case basis. All audit reports are shared under explicit NDA in Bind format between Bind and party to receive materials. Audit reports can be requested by Bind workforce members for Customers or directly by Bind Customers.

The following process is used to request audit reports:

1. Email is sent to compliance-reports@yourbind.com. In the email, please specify the type of report being requested and any required timelines for the report. TODO: create this email (alias to privacy@yourbind.com?)
2. Bind staff will log a "Compliance Review Activity" Issue type with the details of the request into the Bind Security (SEC) Project on JIRA. JIRA is used to track requests status and outcomes. TODO: create
3. Bind will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, Bind will send one for execution.
4. Once it has been confirmed that an NDA is executed, Bind staff will move the JIRA Issue to "Under Review".  TODO
5. The Bind Security Officer or Privacy Officer must Approve or Reject the Issue. If the Issue is rejected, Bind will notify the requesting party that we cannot share the requested report.
4. If the Issue has been Approved, Bind will send the customer the requested audit report and complete the JIRA Issue for the request.

## 1.6 Version Control

Refer to the GitHub repository at [https://github.com/BindBenefits/policies/](https://github.com/BindBenefits/policies/) for the full version history of these policies.

