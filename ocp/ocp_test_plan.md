# OCP Reference Test Plan

This reference test plan covers the tests that need to be implemented to ensure an OCP instance is functioning correctly.

## Basic health checks

The **oc adm diagnostics** command runs a series of checks for error conditions in the host or cluster:

- Verifiy that the default registry and router are running and correctly configured.

- Check ClusterRoleBindings and ClusterRoles for consistency with base policy.

- Check that all of the client configuration contexts are valid and can be connected to.

- Check that SkyDNS is working properly and the pods have SDN connectivity.

- Validate master and node configuration on the host.

- Check that nodes are running and available.

- Analyze host logs for known errors.

- Check that systemd units are configured as expected for the host.

## Docker Registries

- Pull image from Red Hat Registry

- Pull image from Master Registry

## Project Lifecycle

- Create Project 
    - check master, authentication, ldap sync

- Deploy reference application (which has persistent storage) using s2i
    - check pods, routes, storage, services
    - access web UI as user

- Destroy Project 
    - check cleanup complete

## High Availability (across 3 Zones / Data Centres)

### Pre-requisites

- Find zone where Etcd master is running (target zone)
- Deploy the reference application in the target zone

### Test Tasks

- Suspend all VMs in the target zone

- Wait for automatic fail-over

- Check Etcd is functioning correctly

- Check Reference Application is functioning correctly

- Take VMs in the target zone back online

- Check Etcd is functioning correctly

- Check Reference Application is functioning correctly