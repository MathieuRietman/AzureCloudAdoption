# Security, Governance and Compliance

## List of related features and user stories in the backlog

::: query-table 30631937-2cfb-4e31-8f4c-ba3db6d8512b
:::

  
## Introduction

Security will be largely implemented through policy-driven management. The proposed  \<\<customer name>\>'s policies ensure that new subscriptions and resources immediately comply with the compliant state. By using "deployIfNotExists", "deny", "append", and "modify" the Azure resources are made compliant with regard to the Azure platform (Logging, Public Endpoints, Agent install etc).

- With "deployIfNotExist" policies,  *custname* IaaS and PaaS resources, as well as new subscriptions, resources become compliant when created regardless of how they were created.

- With the "deny" policies,  *custname* ensures that there is no misconfiguration. This will cause the deployment to fail and thus prevent non-compliant resource configurations from occurring
  
- With "append" policies, necessary tags are added to resources without user interaction, eg for appropriate cost center tags.

- With the "modify" policies,  *custname* changes can be made to resource tags

Advice is to start with "audit" and "auditIfNotExists" policies to understand current status and compliance, and deploy if not exist for agents and monitoring configurations.

- Security is non-negotiable
Policies enforce enforcement.

The following security policies and governance are used:

<table>
<tr>
<th>Policy</th>
<th>Intent</th>
<th>Assignment scope</th>
<th>Result</th>
</tr>
<tr>
<td>Enforce Azure Security Center</td>
<td>Deploy ASC on every Azure subscription</td>
<td> *custname* management group</td>
<td>All subscriptions will have ASC enabled when they are created</td>
</tr>
<tr>
<td>Enforce Azure Security Monitoring</td>
<td>Enable ASC monitoring on every subscription</td>
<td> *custname* management group</td>
<td>All subscriptions will have all the security monitors enabled</td>
</tr>
<tr>
<td>Enforce Azure Security Center alerts</td>
<td>Enforce consumption of ASC alerts</td>
<td> *custname* management group</td>
<td>All subscriptions will have ASC alerts exported to platform Log Analytics workspace</td>
</tr>
<tr>
<td>Enforce audit of KeyVault</td>
<td>Ensure logging is enabled for Key Vault</td>
<td> *custname* management group</td>
<td>All Key Vaults will have logging enabled, and stored centrally to Log Analytics workspace</td>
</tr>
<tr>
<td>Enforce Anti-Malware</td>
<td>Ensure all virtual machines have anti-malware enabled</td>
<td>Landing Zone management group</td>
<td>Every virtual machine will have the anti-malware VM extension installed</td>
</tr>
<tr>
<td>Allowed resources</td>
<td>Ensure no non-relevant resources can be created</td>
<td><p>Management subscription,</p>
<p>Connectivity subscription</p></td>
<td>Only allowed resources can be created in the management and connectivity subscription</td>
</tr>
<tr>
<td>Deny resources</td>
<td>Explicitly deny resources from being created</td>
<td>Landing Zone management group</td>
<td>Azure services that are not allowed can not be deployed into a landing zone</td>
</tr>
<tr>
<td>Enforce Key Vault recovery</td>
<td>Ensure Key Vault objects can be recoverable</td>
<td> *custname* management group</td>
<td>All Key Vault objects are recoverable in  *custname* tenant</td>
</tr>
<tr>
<td><p>Enforce Private Link for  Azure Services </p>
<p>Storage</p>
<p>ADLS </p>
<p>SQL DB</p>
<p>Synapse</p>
<p>Cosmos DB</p>
<p>PostgreSQL</p>
<p>MySQL</p>
<p>MariaDB</p>
<p>Key Vault</p>
<p>AKS (API)</p>
</td>
<td>Ensure Private Link is used for all supported Azure services</td>
<td>Landing Zone management group</td>
<td> <a href='https://docs.microsoft.com/en-us/azure/private-link/private-link-overview#availability'> Supported Azure services  always use Private Link to communicate to PaaS service over the vNet</td>
</tr>
</table>
