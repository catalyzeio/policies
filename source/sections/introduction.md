# Introduction

BIND is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of compliant hosted On-Demand Health Insurance platform used by employers, health insurance companies, health technology vendors, and enterprises, BIND strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by BIND to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for BIND Customers.

BIND provides secure and compliant cloud-based software. This hosted software falls into two broad categories: 1) **On-Demand Employer Health Insurance** 2) **On-Demand Health Insurance Platform as a Service (PaaS)**. These Categories are cited throughout polices as Customers in each category inherit different policies, procedures, and obligations from BIND.

## On-Demand Employer Health Insurance

BIND On-Demand Employer Health Insurance services cover all third party administration (TPA) aspects for self-insured employers choosing to offer their employees on-demand health insurance. The services offered as part of the BIND On-Demand Health Insurance PaaS currently include: healthcare adapters, data science, provider network, and plan design components. Also included are mobile and web applications used to administer and interact with the services.

Third-Party, add-on services may be available as part of the BIND Platform. Any third-party, or Partner Services, shall be reviewed by BIND to ensure compliance with BIND information and security posture.

## On-Demand Health Insurance Platform as a Service (PaaS)

PaaS Customers utilize hosted software and infrastructure from BIND to configure, host, and scale custom developed on-demand health insurance applications and solutions. These customers are deployed into compliant containers run on systems secured and managed by BIND. BIND makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of PaaS Customer data through network (firewalls, dedicated IP spaces, etc) and server settings (encryption at rest and in transit, Intrusion Detection Systems (IDS) throughout the Platform, etc).

(TODO): needs to align with technology, sales, and marketing
PaaS Customers can opt for a list of Services from BIND, which include Human Experience Service, Operations Service, Micro-Network Service, Plan Design Service, Data Science Service. 

## Compliance Inheritance

BIND provides compliant hosted software infrastructure for its Customers. (TODO): BIND has been through a HIPAA compliance audit by a national, 3rd party compliance firm, to validate and map organizational policies and technical settings to HIPAA rules. (TODO)BIND, as a company, and its technology, is in progress of being HITRUST Certified.  BIND's infrastructure at Amazon AWS is in progress of being HITRUST Certified.

BIND signs either (1) business associate agreements (BAAs) or (2) sub-contractor agreements with its Customers. These agreements outline BIND obligations and Customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, BIND manages various aspects of compliance for Customers. The aspects of compliance that BIND manages for Customers are inherited by Customers, and BIND assumes the risk associated with those aspects of compliance. In doing so, BIND helps Customers achieve and maintain compliance, as well as mitigates Customers risk.

Certain aspects of compliance cannot be inherited. Because of this, BIND Customers, in order to achieve full compliance or HITRUST Certification, must implement certain organizational policies. These policies and aspects of compliance fall outside of the services and obligations of BIND.

Below are mappings of HIPAA Rules to BIND controls and a mapping of what Rules are inherited by Customers, both On-Demand Health Insurance Customers and Platform Customers.

## BIND Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructure and managed by AWS. BIND does not have physical access into the network components. The BIND environment consists of AWS network security and firewalls; AWS application load balancers (ALBs); Java application servers; AWS relational datastore (RDS) database servers; (TODO: Finalize)Elasticsearch, Logstash, Kibana (ELK) logging servers; Ubuntu Linux monitoring and management servers; Threat Stack IDS, Vulnerability, and AWS Security services; Docker containers; and developer tool servers running on Ubuntu Linux.

Within the BIND Platform on AWS, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. BIND assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

The data and network segmentation mechanism for AWS uses hosted load balancers that segment data across dedicated Virtual Private Clouds (VPCs) for the BIND platform.

(TODO: confirm with Gruntwork on what we should write into this paragraph)
Additionally, IPtables is used on each each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. BIND has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

In the case of On-Demand Health Insurance Platform as a Service (PaaS), once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into AWS RDS databases through programming logic, such that access to one database server will not present you with the full ePHI spectrum.  (TODO: determine if we should include this DB separation statement, as this might not be the case initially, since we'll have a single Aurora DB RDS instance with a single authN and multiple DBs within the instance)

The bastion host, public application load balancers (ALBs) are externally facing and accessible via the Internet. The internal ALBs, application, and database servers, where the ePHI resides, are located on the internal BIND network and can only be accessed directly over an SSH connection through the bastion host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

All platform components, containers, and operating systems are tested end-to-end for usability, security, and impact prior to deployment to production.

## Version Control

Policies were last updated March 27th, 2017.
