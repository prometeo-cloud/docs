## Control Plane Design

The deployment of the Prometeo OCP platform is dependent on the following control plane components :

- Red Hat Satellite 6.3
- Red Hat Ansible Tower 2.4

Each instance deployment additionally requires :

- Red Hat Satellite 6.3 Capsule Server(s)
- Red Hat Ansible Tower Isolated Node(s)

The ongoing management of the OCP clusters requires :

- Red Hat Cloud Forms
- EFK 
- Nagios

Additional support functions are provided by :

- GoGs
- Bastion Host(s)

### Red Hat Satellite

Satellite is used to support the provisioning and ongoing management of the OCP deployment(s) and for bare metal provisioning where necessary.  OCP Hosts are subscribed to a specific, versioned content view hosted on Satellite.  Each Prometeo OCP deployment will use a local Red Hat Satellite capsule server co-located with the OCP deployment.

### Ansible Tower

Ansible Tower is used for both day 1 and day 2 options of the OCP deployment.  Tower is used to provision the underlying cloud hosted infrastructure and to perform the installation and configuration of OCP.  Ongoing management, such as Patching and upgrades and scale out operations are performed by Ansible playbooks executed from Tower.  Each Prometeo OCP deployment will use an Ansible Tower isolated node co-located with the OCP deployment.

### CloudForms

CloudForms is used to to provide governance and compliance of the platform.  It provides, quotas and charge back for OCP hosted projects, performance and capacity management functions for the platform and container security and compliance management via OpenSCAP.  

### EFK Stack

The Elastic Search, Fluentd and Kibana stack provides log aggregation functions for the OCP platform itself.  Applications running on OCP will use the native EFK stack provided by the platform.

### Nagios

Nagios is used to monitor the health of underlying the OCP platform components and provide alerts should issues arise.  

### GoGs

An installation of GoGs provides local GIT source control for installation specific resources required to support the OCP platform.

### Bastion Hosts

Interactive access to the platform is via bastion hosts deployed alongside each OCP deployment.  Interactive access to platform is expected to be minimal and only required for debugging activities allowing the bastion hosts to be shutdown during normal operation.

## High level diagram

![Prometeo Control Plane](https://www.lucidchart.com/publicSegments/view/a3aefddb-afd2-4fc0-8f2f-74f56a7453ae/image.png)
