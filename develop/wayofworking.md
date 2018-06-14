## Way of working

### General Guidelines

- The development machine should have RHEL 7+ or CentOS 7+
- The development machine should have at least 16 Gb RAM
- If OS is not one of the above then development should be done in [Europa](https://github.com/gatblau/europa).
- [Ansible]() and [Molecule]() should be installed in the developer machine
- The structure of a Role Repository should be as [this](https://github.com/prometeo-cloud/prometeo-role-test).
- The structure of a Configuration Repository should be as [this](https://github.com/prometeo-cloud/prometeo-cfg-test).
- Generation of hosts for testing is done by including roles for docker host creation or vagrant vm host creation in a Configuration Repository.

### Process

- Functional decomposition and identification of automation functions, dependencies and configuration sets.
- Creation of Role repository.
- Collaborator access provided to development staff.
- Unit testing of Role Repository using [Molecule]().
- Creation of Configuration Repository.
- Collaborator access provided to development staff.
- Integration test of roles using Configuration Repository and Docker containers or Vagrant boxes as hosts.

### Tools

- Source code repository: Github - [here](https://github.com/prometeo-cloud/)
- Binary artefact repository: private Nexus
- ChatOps: private RocketChat
- Build server for Ansible roles: private Jenkins
- All documentation created using markdown and diagrams using graphml format.
