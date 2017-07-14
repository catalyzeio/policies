# BIND HIPAA Compliance Policies

BIND Privacy and Security used open source policies from Datica as the starting basis of Bind policies.  We will continue to customize to our needs and compare to the updates made from the forked repository from Datica (formerly Catalyze.io), https://github.com/catalyzeio/policies and published to https://policy.datica.com.

HIPAA compliance is complicated, but it doesn't have to be. Bind helps relieve the technical burden with our HIPAA-compliant On Demand Health Insurance TPA services and platform.

These policies have been written with modern, cloud-based technology vendors in mind. We looked far and wide for policy examples and found that Datica's fit our company best. So we forked their repository and made them our basis. Importantly, the basis of these Datica open source policies have been through three external audits - two HIPAA audits and one HITRUST audit.

## Why did we use these open source policies?

HIPAA compliance really has two halves. The first half includes all technical guidelines, both physical and digital. Compliant companies take measures to secure their hardware and manage their software in a certain way. Encryption, logging, monitoring—these are just a few examples of HIPAA technical requirements. Bind builds its platform with these guidelines in mind.

The second half of HIPAA is focused on administrative and organizational activities. This includes signing Business Associate Agreements (BAAs), and managing company policies like training, among other things. Crafting company policies that align with HIPAA administrative guidelines are straightforward, but an immense burden.

When we were creating our policies, we found lots of policy templates for healthcare providers, but nothing for modern health technology companies. We spent a lot of time and effort writing our policies, then adapting them to meet the demands of external audits. We didn't think we needed to reinvent the wheel. We also feel a broader community can improve the open source polices over time, making them better for everybody and will contribute back to the Datica upstream repository when it makes sense.

## Who is behind this?

[Datica](htts://datica.com), healthcare's trusted HTRUST CSF Certified digital health platform.

### License

All policies are licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).

### Policy Index

* [Introduction](source/sections/01-introduction.md)
* [HIPAA Inheritance](source/sections/02-hipaa_inheritance.md)
* [Policy Management Policy](source/sections/03-policy_management_policy.md)
* [Risk Management Policy](source/sections/04-risk_management_policy.md)
* [Roles Policy](source/sections/05-roles_policy.md)
* [Data Management Policy](source/sections/06-data_management_policy.md)
* [System Access Policy](source/sections/07-systems_access_policy.md)
* [Auditing Policy](source/sections/08-auditing_policy.md)
* [Configuration Management Policy](source/sections/09-configuration_management_policy.md)
* [Facility Access Policy](source/sections/10-facility_access_policy.md)
* [Incident Response Policy](source/sections/11-incident_response_policy.md)
* [Breach Policy](source/sections/12-breach_policy.md)
* [Disaster Recovery Policy](source/sections/13-disaster_recovery_policy.md)
* [Disposable Media Policy](source/sections/14-disposable_media_policy.md)
* [IDS Policy](source/sections/15-ids_policy.md)
* [Vulnerability Scanning Policy](source/sections/16-vulnerability_scanning_policy.md)
* [Data Integrity Policy](source/sections/17-data_integrity_policy.md)
* [Data Retention Policy](source/sections/18-data_retention_policy.md)
* [Employees Policy](source/sections/19-employees_policy.md)
* [Approved Tools Policy](source/sections/20-approved_tools_policy.md)
* [3rd Party Policy](source/sections/21-3rd_party_policy.md)
* [Key Definitions](source/sections/22-key_definitions.md)
* [Datica HIPAA Business Associate Agreement (“BAA”)](source/sections/23-datica_hipaa_business_associate_agreement.md)
* [HIPAA Mappings to Datica Controls](source/sections/24-hipaa_mapping_to_datica_controls.md)

# Setup steps
1. Go to the [BIND forked version of the Catalyze policies](https://github.com/BindBenefits/policies).
2. In the upper right-hand click the drop down menu "Clone or download"
    * click on "Use SSH" if it isn't already selected
    * Grab the ssh url
3. clone your fork to your local box working directory
    ```
    git@github.com:BindBenefits/policies.git
4. do a: git remote -v to show your remotes you should see something like this:
    ```
    $ git remote -v
    origin  git@github.com:user/policies.git (fetch)
    origin  git@github.com:user/policies.git (push)
5. add the upstream:
    ```
    git remote add upstream git@github.com:catalyzeio/policies.git
6. look at the remotes:
    ```
    $ git remote -v
    origin	git@github.com:BindBenefits/policies.git (fetch)
    origin	git@github.com:BindBenefits/policies.git (push)
    upstream	git@github.com:catalyzeio/policies.git (fetch)
    upstream	git@github.com:catalyzeio/policies.git (push)
7. set the upstream to no-push so you don't accidently push to the catalyze/datica repository (although wouldn't have permissions I don't believe)
    ```
    git remote set-url --push upstream no-pushing
8. Finally you should see this:
    ```
    git remote -v
    origin	git@github.com:BindBenefits/policies.git (fetch)
    origin	git@github.com:BindBenefits/policies.git (push)
    upstream	git@github.com:catalyzeio/policies.git (fetch)
    upstream	no-pushing (push)
