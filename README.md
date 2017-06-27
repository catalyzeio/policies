# BIND HIPAA Compliance Policies

BIND Information Security used these opensource policies as the starting basis of our policies.  We will continue to customize to our needs and compare to the updates made from the forked repository from Datica (formerly Catalyze.io), https://github.com/catalyzeio/policies.

##Setup steps
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


###Original readme follows:

HIPAA compliance is complicated, but it doesn't have to be. Datica helps relieve the technical burden with our HIPAA-compliant cloud computing platform and solutions for healthcare.

In an effort to make compliance as easy as possible for companies working with protected health information (PHI), we decided to open source our company policies.

Our policies have been written with modern, cloud-based technology vendors in mind. We looked far and wide for policy examples that fit our company, and couldn't find any. So we wrote our own. Importantly, these policies have been through three external audits—two HIPAA audits and one HITRUST audit.

Do you handle PHI and not yet have your own company policies in place? Then you'll find our content useful.

## Why did we open source these policies?

HIPAA compliance really has two halves. The first half includes all technical guidelines, both physical and digital. Compliant companies take measures to secure their hardware and manage their software in a certain way. Encryption, logging, monitoring—these are just a few examples of HIPAA technical requirements. Datica builds its platform with these guidelines in mind.

The second half of HIPAA is focused on administrative and organizational activities. This includes signing Business Associate Agreements (BAAs), and managing company policies like training, among other things. Crafting company policies that align with HIPAA administrative guidelines are straightforward, but an immense burden.

When we were creating our policies, we found lots of policy templates for healthcare providers, but nothing for modern health technology companies. We spent a lot of time and effort writing our policies, then adapting them to meet the demands of external audits. We don't want people to reinvent the wheel; trust us, it's not fun. We also feel a broader community can improve these polices over time, making them better for everybody.

By open sourcing our own company policies, we hope other companies who handle PHI will benefit. It aligns with our company mission: to help you focus on building innovative healthcare applications.

## What do I do with these policies?

As a company who handles PHI, it's critical you maintain and publish your own policies. To make use of our policies, we recommend the following steps.

1. Read through all the enclosed policies to get an understanding to the structure.
2. When ready, download the policies and comb through for mentions of Datica or our business and change to appropriate references to your company.
3. Publish your policies in a publicly available location. The files are markdown, so you may need to convert to HTML if you don't have a publishing platform capable of markdown format. You can either create an index page linking to each individual policy, or create a single page listing all the policies in line, [much like we did](https://policy.datica.com).

## Who is behind this?

[Datica](htts://datica.com), healthcare's trusted HTRUST CSF Certified digital health platform.

We help companies who handle PHI, both business associates and covered entities, maintain compliance with our ([Compliant Cloud](https://datica.com/compliant-cloud)) and ([Managed Integration](https://datica.com)).

To get in touch, shoot us an email at [hello@datica.com](mailto:hello@datica.com). We'd love to hear from you!

### License

All policies are licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).

### Policy Index

Each policy is included as it's own markdown file in case you want to cherry pick specific policies. If you currently have no policies in place, we encourage you to consider utilizing all policies.

* [Introduction](source/sections/introduction.md) //Chad in progress 3/27/17
* [HIPAA Inheritance for PaaS Customers](source/sections/hipaa_inheritance_for_paas_customers.md)
* [HIPAA Inheritance for Platform Add-on Customers](source/sections/hipaa_inheritance_for_platform_addon_customers.md)
* [Policy Management Policy](source/sections/policy_management_policy.md)
* [Risk Management Policy](source/sections/risk_management_policy.md)
* [Roles Policy](source/sections/roles_policy.md)
* [Data Management Policy](source/sections/data_management_policy.md)
* [System Access Policy](source/sections/systems_access_policy.md)
* [Auditing Policy](source/sections/auditing_policy.md)
* [Configuration Management Policy](source/sections/configuration_management_policy.md)
* [Facility Access Policy](source/sections/facility_access_policy.md)
* [Incident Response Policy](source/sections/incident_response_policy.md)
* [Breach Policy](source/sections/breach_policy.md)
* [Disaster Recovery Policy](source/sections/disaster_recovery_policy.md)
* [Disposable Media Policy](source/sections/disposable_media_policy.md)
* [IDS Policy](source/sections/ids_policy.md)
* [Vulnerability Scanning Policy](source/sections/vulnerability_scanning_policy.md)
* [Data Integrity Policy](source/sections/data_integrity_policy.md)
* [Data Retention Policy](source/sections/data_retention_policy.md)
* [Employees Policy](source/sections/employees_policy.md)
* [Approved Tools Policy](source/sections/approved_tools_policy.md)
* [3rd Party Policy](source/sections/3rd_party_policy.md)
* [Key Definitions](source/sections/key_definitions.md)
* [Datica HIPAA Business Associate Agreement (“BAA”)](source/sections/datica_hipaa_business_associate_agreement.md)
* [HIPAA Mappings to Datica Controls](source/sections/hipaa_mapping_to_datica_controls.md)
