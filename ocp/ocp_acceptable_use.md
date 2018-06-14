## OCP Acceptable Use Policy

In order to guarantee that applications carry on working with minimum disruption during normal operation and when platform upgrades are performed, they should follow the following directives:

Applications should:
1. **Not rely on Technology Preview Features**. Technology preview features of the platform can be subject to changes between releases. Therefore when they are used in one release, the can lead to applications not working when performing an upgrade of the platform.

2. **Be designed so that they are resilient to restarts**. The container orchestration engine in the platform can elect to destroy a container running an application workload at any point in time depending on operational circumstances. Workloads that cannot be stopped gracefully can lead to data corruption or erratic behaviour.

3. **Be resilient to unavailability of supporting services**. Application services can rely on other services to perform their job. Applications that cannot handle temporary availability of supporting services are subject to failures when such services are restarted by the container orchestration platform.

In addition, to facilitate troubleshooting of micro-service architectures, applications should:

4. **Identify the name of failing caller/callee service invocations**.

5. **Log errors to standard output**.
