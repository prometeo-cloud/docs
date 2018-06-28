# DNS Configuration

| Item | Category | Zone | Host | Cert? | SAN | Description |
|---|---|---|---|---|---|---|
| Bastion Zone A | Control Plane | A | bastion01 | No |bastion01.example.com | The SSH jump box used to connect to other boxes for admin purposes. |
| Bastion Zone B | Control Plane | B | bastion02 | No |bastion02.example.com | A second SSH jump box in a different availability zone to provide HA access. |
| Satellite | Control Plane | A | satellite01 | Yes |satellite01.example.com | A Satellite server to manage critical updates and subs for the OCP instances. |
| GoGS | Control Plane | A | gogs01 | Yes | gogs01.example.com |
| CloudForms | Control Plane | A | cf01 | Yes | cfadmin.example.com |
| CloudForms | Control Plane | A | cf02 | Yes | cf.example.com |
| EFK | Control Plane | A | efk01 | Yes | logs.example.com |
| OCP Console Zone A | OCP 01 | A | ocp01mst01 | No |ocp01admin01.example.com | 
| OCP Console Zone B | OCP 01 | B | ocp01mst02 | No | ocp01admin02.example.com | 
| OCP Console Zone C | OCP 01 | C | ocp01mst03 | No | ocp01admin03.example.com |
| OCP Console | OCP 01 | ALL | N/A - Load Balancer | Yes | ocp01admin.example.com, ocp01admin01.example.com, ocp01admin02.example.com, ocp01admin03.example.com, ocp01mst01, ocp01mst02, ocp01mst03 |
| OCP Infra Zone A | OCP 01 | A | ocp01infra01 | No |ocp01infra01.example.com | 
| OCP Infra Zone B | OCP 01 | B | ocp01infra02 | No | ocp01infra02.example.com | 
| OCP Infra Zone C | OCP 01 | C | ocp01infra03 | No | ocp01infra03.example.com |
| OCP Compute Zone A | OCP 01 | A | ocp01comp01 | No |ocp01comp01.example.com | 
| OCP Compute Zone B | OCP 01 | B | ocp01comp02 | No | ocp01comp02.example.com | 
| OCP Compute Zone C | OCP 01 | C | ocp01comp03 | No | ocp01comp03.example.com |  
| OCP Apps    | OCP 01 | ALL | N/A - Load Balancer | Yes | *.ocp01apps.example.com |
| OCP CRS Zone A | OCP 01 Storage | A | ocp01crs01 | No | ocp01crs01.example.com |
| OCP CRS Zone B | OCP 01 Storage | B | ocp01crs01 | No | ocp01crs02.example.com |
| OCP CRS Zone C | OCP 01 Storage | C | ocp01crs01 | No | ocp01crs03.example.com |


