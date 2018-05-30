# 16. Data Integrity Policy

WatchTower takes data integrity very seriously. As stewards and partners of WatchTower Customers, we strive to assure data is protected from unauthorized access and that it is available when needed. The following policies drive many of our procedures and technical settings in support of the WatchTower mission of data protection.

Production systems that create, receive, store, or transmit Customer and Partner data (hereafter "Production Systems") must follow the guidelines described in this section.

## 16.1 Applicable Standards

### 16.1.1 Applicable Standards from the HIPAA Security Rule

* 164.308(a)(8) - Evaluation

## 16.2 Disabling Non-Essential Services

1. All Production Systems must disable services that are not required to achieve the business purpose or function of the system.

## 16.3 Monitoring Log-in Attempts

1. All access to Production Systems must be logged. This is done following the WatchTower Auditing Policy.

## 16.4 Prevention of Malware on Production Systems

1. All Production Systems must have OSSEC running, and set to scan system every 2 hours and at reboot to assure not malware is present. Detected malware is evaluated and removed.
2. All Production Systems are to only be used for WatchTower business needs.

## 16.5 Patch Management

1. Software patches and updates will be applied to all systems in a timely manner. In the case of routine updates, they will be applied after thorough testing. In the case of updates to correct known vulnerabilities, priority will be given to testing to speed the time to production. Critical security patches are applied within 30 days from testing and all security patches are applied within 90 days after testing.
2. Administrators subscribe to mailing lists to ensure that they are using current versions of all WatchTower-managed software on Production Systems.

## 16.6 Intrusion Detection and Vulnerability Scanning

1. Production systems are monitored using IDS systems. Suspicious activity is logged and alerts are generated.
2. Vulnerability scanning of Production Systems must occur on a predetermined, regular basis. Scans are reviewed by Security and Privacy Officer, with defined steps for risk mitigation, and retained for future reference.

## 16.7 Production System Security

1. System, network, and server security is managed and maintained by the Security and Privacy Officer in conjunction with the Development/Operations team.
2. Up to date system lists and architecture diagrams are kept for all production environments.
3. Access to Production Systems is controlled using centralized tools and two-factor authentication.

## 16.8 Production Data Security

1. Reduce the risk of compromise of Production Data.
2. Implement and/or review controls designed to protect Production Data from improper alteration or destruction.
3. Ensure that confidential data is stored in a manner that supports user access logs and automated monitoring for potential security incidents.
4. Ensure WatchTower Customer Production Data is segmented and only accessible to Customers authorized to access data.
5. All Production Data at rest is stored on encrypted volumes using encryption keys managed by WatchTower. Encryption at rest is ensured through the use of automated deployment scripts referenced in the [Configuration Management Policy](#8.-configuration-management-policy).
6. Volume encryption keys and machines that generate volume encryption keys are protected from unauthorized access. Volume encryption key material is protected with access controls such that the key material is only accessible by privileged accounts.
7. Encrypted volumes use AES encryption with a minimum of 256-bit keys, or keys and ciphers of equivalent or higher cryptographic strength.

## 16.9 Transmission Security

1. All data transmission is encrypted end to end using encryption keys managed by WatchTower. Encryption is not terminated at the network end point, and is carried through to the application.
2. Transmission encryption keys and machines that generate keys are protected from unauthorized access. Transmission encryption key material is protected with access controls such that the key material is only accessible by privileged accounts.
3. Transmission encryption keys use a minimum of 4096-bit RSA keys, or keys and ciphers of equivalent or higher cryptographic strength (e.g., 256-bit AES session keys in the case of IPsec encryption).
4. Transmission encryption keys are limited to use for one year and then must be regenerated.
5. In the case of WatchTower provided APIs, provide mechanisms to assure person sending or receiving data is authorized to send and save data.
6. System logs of all transmissions of Production Data access. These logs must be available for audit.
