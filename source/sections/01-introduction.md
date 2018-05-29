# 1. Introduction

WatchTower Benefits ("WatchTower") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers and Partners. As a provider of compliant, hosted software solutions to the Employee Benefits industry, WatchTower strives to maintain compliance, proactively address information security, mitigate risk for its Customers and Partners, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by WatchTower to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for WatchTower Customers and Partners.

WatchTower provides secure and compliant cloud-based software. This hosted software falls into two broad categories: 1) **Platform as a Service (PaaS)** and 2) **Platform Add-ons**. These Categories are cited throughout polices as Customers in each category inherit different policies, procedures, and obligations from WatchTower.

## 1.1 WatchTower Organizational Concepts

The physical infrastructure environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS). The network components and supporting network infrastructure are contained within the AWS infrastructure and managed by AWS. WatchTower does not have physical access into the network components. The WatchTower environment consists of Cisco firewalls; nginx web servers; Java, Python, and Go application servers; Percona and PostgreSQL database servers; Logstash logging servers; Linux Ubuntu monitoring servers; Windows Server virtual machines; Chef and Salt configuration management servers; OSSEC IDS services; Docker containers; and developer tool servers running on Linux Ubuntu.

Within the WatchTower Platform on Rackspace, AWS, Azure, and SoftLayer, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. WatchTower assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

Additionally, IPtables is used on each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. WatchTower has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an TLS encrypted session.


The VPN server, nginx web server, and application servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal WatchTower network and can only be accessed through a bastion host over a VPN connection. Access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business-justified reason. Remote access to internal servers is not accessible except through load balancers.

All WatchTower software is tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.2 Requesting Audit and Compliance Reports

WatchTower, at its sole discretion, shares audit reports with customers on a case by case basis. All audit reports are shared under explicit NDA in WatchTower format between WatchTower and the party to receive materials.

The following process is used to request audit reports:

1. Email is sent to compliance-reports@watchtowerbenefits.com. In the email, please specify the type of report being requested and any required timelines for the report.
2. WatchTower staff will log an issue with the details of the request into the WatchTower Quality Management System. The WatchTower Quality Management System is used to track requests' status and outcomes.
3. WatchTower will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, WatchTower will send one for execution.
4. Once it has been confirmed that an NDA is executed, WatchTower staff will move the issue to "Under Review".
5. The WatchTower Security Officer or Privacy Officer must Approve or Reject the Issue. If the Issue is rejected, WatchTower will notify the requesting party that we cannot share the requested report.
6. If the issue has been Approved, WatchTower will send the customer the requested audit report and complete the Quality Management System issue for the request.

## 1.3 Version Control

Refer to the GitHub repository at [https://github.com/WatchTowerBenefits/policies](https://github.com/WatchTowerBenefits/policies) for the full version history of these policies.
