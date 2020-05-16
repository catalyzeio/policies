# 1. Introduction

CareJourney is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. CareJourney strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by CareJourney to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for its Customers.

## 1.1 Software as a Service (SaaS)

CareJourney offers advisory and research as well as Software as a Service (SaaS) products that provide both patient-level and benchmarking data to its customers. As a result, CareJourney processes, analyzes and distributes ePHI data from and back to customers. While CareJourey makes every effort to provide a secure SaaS environment for its customers, they are ultimately responsible for how they access the CareJourney SaaS platforms and how they handle data sent to and received from CareJourney and its employees.

## 1.2 Compliance Inheritance

CareJourney has created a secure environment to house ePHI, which is subject to HIPAA and HITRUST compliance. This environment lives within a single AWS account that primarily occupies the US-EAST-1 region, with some presence within the US-EAST-2 region for backups and disaster recovery purposes. This design is more fully documented elsewhere. For purposes of the Information Security Policy, HITRUST and HIPAA controls inherit to all systems, services residing in the ePHI environment, as well as to the employees that operate within it. 

CareJourney signs business associate agreements (BAAs) with its Customers. These BAAs outline CareJourney obligations and Customer obligations, as well as liability in the case of a breach. Generally speaking, CareJourney and each Customer will run their own independent and free-standing information security programs. CareJourney does not inherit specific security controls from its Customers, nor does CareJourney implement security controls on the Customer's behalf. Rather, CareJourney assumes responsibility for the ePHI that has been transmitted to it by or on behalf of its Customers, while the data is within CareJourney's posession. 

## 1.3 Organizational Concepts

The ePHI Secure Environment is hosted at [Amazon Web Services](https://aws.amazon.com/) (AWS), with edge service delivery and security provided by [CloudFlare](https://www.cloudflare.com/). The network components and supporting network infrastructure are contained within and managed by AWS, with exception to edge service delivery, which is provided by CloudFlare. CareJourney does not have physical access into these network components. The environment within CareJourney's control consists of AWS services and resources, as well as instances and containers running applications written in Java and Python. 

## 1.4 Version Control

Refer to the GitHub repository at [https://github.com/navhealth/infosec/](https://github.com/navhealth/infosec/) for the full version history of these policies.
