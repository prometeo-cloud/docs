# Bill of Materials (BOM)

This document provides examples of typical a bill of materials for OCP instances and how they relate to stock keeping units SKUs.

## OCP Non-Production Instance

Example within single availability zone.

### Items

| # | Server Role | Qty | vCPUs | Total vCPUs | Schedulable | Memory | Storage |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | Master/Etcd | 3 | 12 | 36 | no |
| 2 | Infrastructure | 3 | 8 | 24 | no |
| 3 | Router (Optional) | 2 | 4 | 8 | no |
| 4 | *Compute* | 4 | 16 | *64* | *yes* |
| 5 | Storage (CRS) | 3 | 8 | 24 | no |
| - | **Total** | **15** | **48** | **156** | - |

### Subscriptions

| Server Role | Subscription | SKU | Qty | vCPU/VM |
|---|---|:---:|:---:|:---:|
| OCP Compute Node| Red Hat OpenShift Container Platform, Standard, 2-Core | MCT2736 | 16[*] | 64 |  
| CRS Storage | Container Storage Add-On for OpenShift Container Platform, Standard (3 Nodes) | RS00149 | 3 | N/A |
| CRS Storage | Red Hat Enterprise Linux Server with Smart Management, Standard (Physical or Virtual Nodes)| RH00009 | 2[**] | N/A |
| OCP Node | Smart Management | RH00031 | 8[***] | N/A |

\[*\]: assuming VM based nodes and hyper-threading, 1 core = 2 vcpus, the sample calculation is:
 - 64 vcpu / 2 vcpu/core / 2 core/unit = **16 units**
 - 4 units per compute node => 4 nodes * 4 unit/node = **16 units**

\[**\]: covers for 3 CRS RHEL nodes managed by Satellite.
 
\[***\]: covers for 12 OCP nodes managed by Satellite, the sample calculation is:
 - 2 VMs/module * 8 module = **16 VMs**, or
 - 15 VMs / 2 VMs/module = **7.5 => 8 modules**

## OCP Production Instance 

Example stretched across 3 availability zones.

### Items

| # | Server Role | Qty | vCPUs | Total vCPUs | Schedulable |
|---|---|:---:|:---:|:---:|:---:|
| 1 | Master/Etcd | 3 | 12 | 36 | no |
| 2 | Infrastructure | 3 | 8 | 24 | no |
| 3 | Router (Optional) | 3 | 12 | 8 | no |
| 4 | *Compute* | 3 | 16 | *96* | *yes* |
| 5 | Storage (CRS) | 3 | 8 | 24 | no |
| - | **Total** | **18** | **54** | **188** | - |

### Subscriptions

| Server Role | Subscription | SKU | Qty | vCPU/VM |
|---|---|:---:|:---:|:---:|
| OCP Compute node | Red Hat OpenShift Container Platform, Premiun, 2-Core | MCT2735 | 24[*] | 96 |  
| CRS Storage | Container Storage Add-On for OpenShift Container Platform, Premium (3 Nodes) | RS00148 | 3 | N/A |
| CRS Storage | Red Hat Enterprise Linux Server with Smart Management, Premium (Physical or Virtual Nodes)| RH00008 | 4[***] | N/A |
| OCP Node | Smart Management | RH00031 | 9[**] | N/A |
 
\[*\]: assuming VM based nodes and hyper-threading, 1 core = 2 vcpus, the sample calculation is:
 - 96 vcpu / 2 vcpu/core / 2 core/unit = **24 units**
 - 4 units per compute node => 6 nodes * 4 unit/node = **24 units**
 
\[**\]: covers for 3 CRS RHEL nodes managed by Satellite.

\[***\]: covers for 15 CRS RHEL nodes managed by Satellite, the sample calculation is:
 - 2 VMs/module * 9 module = **18 VMs**, or
 - 18 VMs / 2 VMs/module = **9 modules**
 
