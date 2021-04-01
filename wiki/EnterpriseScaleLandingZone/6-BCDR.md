
# Business Continuity and Disaster Recovery

## List of related features and user stories in the backlog

::: query-table 726f78ea-44f2-4e8d-a7a4-e875fb0c5623
:::


## High availability

* The application architecture of the various workloads must use Availability Zones if high availability is required. This means that the application and the data has synchronously replication between Availability Zones in the Azure region (West Europe) for high availability, asynchronously replication of data between Azure regions (North Europe) is used for DR disaster recovery protection.
* Azure services have built-in replication between the Availability Zones such as Zone-Redundant Storage and Azure SQL DB.
* All network components will be deployed zone-redundantly as much as possible, so that services can be implemented zone-redundantly if necessary.
* Stateless virtual machine workloads can be deployed with multiple instances in different Availability Zones behind a Load Balancer standard or Application Gateway (v2).
* Statefull virtual machine workloads must use application-level replication between the Availability Zones, such as Active Directory, SQL AlwaysOn.
* Statefull virtual machine workloads that do not support application level replication require Azure Site Recovery Zonal-Replication (preview) or possibly Region replication for DR.

During deployment, one must always consciously select the correct zone or zone configuration. Consult the documentation for this.

A design will be made for each workload, taking into account the availability requirements of the workload and  \<\<customer name>\> will choose the correct availability measures.
The advise is to start with a zone redundant S2S VPN Gateway. 



## Disaster Recovery

Part of workload design.
Depending on RPO, RTO.

Applications are deployed redundantly from high availability Zone if necessary.
The backup can be the DR using GRS storage.  \<\<customer name>\> and should consider if you have low RPO, RTO for the deployment of Azure Site Recovery (Azure to Azure) 

## Backup
Part of workload design.
Depending on RPO, RTO.
Proposed is as much as possible the Azure platform use backup features of PAAS and Azure Backup.

Possible policies.

| Policy                                                                   | Intent                                                          | Assignment scope                 | Result                                                                                                          |
| ------------------------------------------------------------------------ | --------------------------------------------------------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [Deploy Backup Vault and enforce backup setting for Windows and Linux VMs | Deploy backup vault and enable backup                           | 'Landing Zones' management group | Every Resource Group with VMs in a landing zone subscription has a backup vault to which all VMs are backed up. |
| [Add diagnostic setting to backup vault]                                   | Link Backup Vault diagnostics to central Log Analytics instance | 'Landing Zones' management group | Platform team has horizontal view over all VM backup                                                            |

---