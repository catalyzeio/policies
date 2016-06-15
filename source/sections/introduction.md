# Introduction

Agathos, Inc ("Agathos") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As providers of an analytics platform designed to help providers make more valuable decisions, Agathos strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. This document addresses core policies used by Agathos to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for Agathos Customers.

## Compliance Inheritance

Catalyze provides compliant hosted software infrastructure for its Customers. Catalyze has been through a HIPAA compliance audit by a national, 3rd party compliance firm, to validate and map organizational policies and technical settings to HIPAA rules. Catalyze, as a company, and its technology, is HITRUST Certified.  Catalyze's infrastructure at Rackspace is HITRUST Certified and certification for AWS, Azure, and SoftLayer are in progress.

Catalyze signs business associate agreements (BAAs) with its Customers. These BAAs outline Catalyze obligations and Customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, Catalyze manages various aspects of compliance for Customers. The aspects of compliance that Catalyze manages for Customers are inherited by Customers, and Catalyze assumes the risk associated with those aspects of compliance. In doing so, Catalyze helps Customers achieve and maintain compliance, as well as mitigates Customers risk.

Below are mappings of HIPAA Rules to Catalyze controls and a mapping of what Rules are inherited by Customers, both PaaS Customers and Add-on Customers.

## Catalyze Organizational Concepts

The physical infrastructure environment is hosted at [Rackspace](http://broadcast.rackspace.com/downloads/pdfs/RackspaceSecurityApproach.pdf), [Amazon Web Services](https://aws.amazon.com/) (AWS), [Microsoft Azure](https://azure.microsoft.com/), and [IBM SoftLayer](http://www.softlayer.com/). The network components and supporting network infrastructure are contained within the Rackspace, AWS, Azure, and SoftLayer infrastructures and managed by Rackspace, AWS, Microsoft, and IBM (respectively). Catalyze does not have physical access into the network components. The Catalyze environment consists of Cisco firewalls, Apache and nginx web servers, Dropwizard Java application servers, Percona and PostgreSQL database servers, Logstash logging servers, Linux Ubuntu monitoring servers, Salt configuration management server, OSSEC IDS services, Docker containers, and developer tools servers running on Linux Ubuntu.

Within the Catalyze Platform on Rackspace, AWS, Azure, and SoftLayer, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. Catalyze assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

In the case of PaaS Customers, it is the responsibility of the Customer to restrict, secure, and assure the privacy of all ePHI data at the Application Level, as this is not under the control or purview of Catalyze.

The data and network segmentation mechanism differs depending on the primitives offered by the underlying cloud provider infrastructure:

* Within Rackspace, hosted load balancers segment data and traffic while Cisco firewalls route traffic to private subnets for PaaS Customers and for Platform Add-ons.
* Within AWS, hosted load balancers segment data across dedicated Virtual Private Clouds for PaaS Customers and for Platform Add-ons.
* Within Azure, hosted load balancers segment data across dedicated Virtual Networks for PaaS Customers and for Platform Add-ons.
* Within SoftLayer, hosted load balancers segment data across dedicated Private Networks for PaaS Customers and for Platform Add-ons.

The result of segmentation strategies employed by Catalyze effectively create RFC 1918, or dedicated, private segmented and separated networks and IP spaces, for each PaaS Customer and for Platform Add-ons.

Additionally, IPtables is used on each each server for logical segmentation. IPtables is configured to restrict access to only justified ports and protocols. Catalyze has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an SSL encrypted session.

In the case of Platform Add-ons, once the data is received from the application server, a series of Application Programming Interface (API) calls is made to the database servers where the ePHI resides. The ePHI is separated into PostgreSQL and Percona databases through programming logic built, so that access to one database server will not present you with the full ePHI spectrum.

The bastion host, Apache web server, Dropwizard application servers are externally facing and accessible via the Internet. The database servers, where the ePHI resides, are located on the internal Catalyze network and can only be accessed directly over an SSH connection through the bastion host. The access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business justified reason. Remote access to the internal servers is not accessible except through the load balancers and bastion host.

All Platform Add-ons and operating systems are tested end-to-end for usability, security and impact prior to deployment to production.

## Version Control

Policies were last updated May 10th, 2016.
