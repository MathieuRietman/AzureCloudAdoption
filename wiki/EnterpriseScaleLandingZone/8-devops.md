# Platform automation and DevOps

## List of related features and user stories in the backlog

::: query-table 72d6d597-085c-427b-825f-c16258da7688
:::

<font color="red">Remove this and the above line by first go into edit mode and replace it with insert ADO query and select **DevOps-tags** of the imported queries.</font>

## Central vs Application responsibilities

The following list presents a recommended distribution of responsibilities between the central IT team and application teams. You're striving to empower migration and transformation activities with minimal central dependencies. At the same time, you want to support the centralized governance of security and operability across the entire estate.

Application functions (AppDevOps)
- Application migration and transformation.
- Application management and monitoring (application resources).
- Key management (application keys).
- Azure RBAC (application resources).
- Security monitoring and audit (application resources).
- Cost management (application resources).
- Network management (application resources).

Central functions (Platform Ops)
- Architecture governance.
- Subscription management.
- Platform as code (management of templates, scripts, and other assets).
- Policy management and enforcement (holistic).
- Platform management and monitoring (holistic).
- Azure RBAC (holistic).
- Key management (central services).
- Network management (including networks and network virtual appliances).
- Security monitoring and audit (holistic).
- Cost management (holistic).



## Operationalize

Consider adopting azOps for infrastructure as code deployment for the landingzone.
see [Getting started with infrastructure-as-code](https://github.com/Azure/Enterprise-Scale/blob/main/docs/Deploy/getting-started.md)