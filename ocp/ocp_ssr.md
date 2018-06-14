# OCP Standard Service Requests

| SSR Ref. | Name | Description |
|---|---|---|
| **Tenant Management** | | *A Tenant is a logical grouping of OCP projects for configuration management purposes.* |
| T01 | Create Tenant| Creates one or more OCP projects (Tenant) and the required access controls for admin and user roles. |
| T02 | Decommission Tenant| Decommision one or more OCP projects (Tenant) and remove any existing access controls for admin and user roles. | 
| T03 | Add Project to Tenant| Creates a new project under a logical group of existing projects (Tenant) and configures required access control for admin and user roles.  |
| T04 | Remove Project from Tenant| Removes an existing project from a logical group of existing projects (Tenant) and removes any existing access controls for admin and user roles. |
| T05 | Amend Project resource quota. | Changes the resource quota allocated to a existing project. |
| T06 | Add users to Project | Add users to an existing project and allocate them to either the admin or user roles as specified. |
| T06 | Remove users from Project | Removes one or more users from an existing project and de-allocate them from the admin or user roles. |
| **Cluster Management** |||
| C01 | Scale Out Compute | Adds one or more new compute nodes to an OCP cluster. |
| C02 | Scale In Compute | Decommissions one or more compute nodes from an OCP cluster. |
| C03 | Add Storage | Add storage to existing storage node(s) |
| C04 | Remove Storage | Remove storage from existing storage node(s) |
| C05 | Add storage nodes | Add new storage nodes to the cluster |
| C06 | Upgrade Cluster | Upgrade entire cluster to specified OCP version |
