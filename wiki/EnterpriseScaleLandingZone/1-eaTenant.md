
# Enterprise Enrollment and Azure AD Tenants

## List of related features and user stories in the backlog

::: query-table 457b6286-65f2-408b-ae30-fb3f5bace48c
:::

<font color="red">Remove this and the above line by first go into edit mode and replace it with insert ADO query and select **eaTenants-tags** of the imported queries.</font>

## Introduction 

Give short introduction of relevant items to mention

<br/>

 \<\<customer name\>\> uses one an Enterprise agreement. 

| Role | description |
| ----------------------------------- | -------------------------- |
| EA Admins | This role can view the entire account on all subscriptions. In addition, one can create department admin and accounts. This role has no rights within subscriptions |
| EA Admins Read Only | He can see the entire account of all subscriptions but cannot edit anything. Not yet used within   \<\<customer name\>\>|
| Department Admins | This role can create accounts under a department. In addition, the DA roll can gain insight into costs incurred from subscriptions / accounts under a department (if enabled DA can view charges). This role also has no rights to subscription. Not currently used within   \<\<customer name\>\>|
| Accounts | These can actually create new subscriptions and also delete them. Accounts depending on the setting on enrollment have insight into their costs directly in the Azure Portal or via the ea.portal |

See ..... for current  \<\<customer name\>\> EA portal users and roles. 
<br/><br/>

![Enterprise enrollment](../media/ea.png)

<br/><br/>
 \<\<customer name\>\> have 1 hybride identity via tenant <...>.onmicrosoft.com  that is synced via ADConnect with the onsite Active Directory and federated with AD FS Infrastructure.  

<br/>
The advice is to only use these Hybrid identities (Work and School Accounts) within EA environment. Periodically there will be a review of who has access to https://ea.azure.com and verify the roles. 

<br>

Setup enterprise Dev/Test/Prod environments at an EA account level to support creation of dev/test workload for active Visual Studio subscribers. See https://docs.microsoft.com/en-us/visualstudio/subscriptions/azure-ea-devtest. This can reduce cost for dev/test workloads for Windos VM, WIndows PAAS and SQL workloads.

<br/>
<br/>
nitial the creation of new subscriptions is done manually and they will be placed under the appropriate management group as described in this document.
If desired,  create automated / scripted subscriptions using service principles by means of billing accounts RBAC rights see [link](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/programmatically-create-subscription?tabs=azure-powershell)
