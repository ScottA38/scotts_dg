### Historical context for containerisation

![timeline](Container_Evolution.svg)
### Physical server days

- No way to define resource boundaries (_program A gets X CPU time, program B is gets Y etc._), so if multiple applications running on a single server, then one program tends to be dominant, and another passive
	- A solution for this would be to run each application on a different physical server, but hard to scale due to running costs (electricity, repair, etc.)
	- Poor operational security for applications running on the server, as in multi-application scenario, critical files could belonging to a specific application could be deleted or modified by an arbitrary process

### VM days

- Virtualisation introduced in order to enable servers to run multiple applications on a single CPU with enforced resource boundaries
	- Enabled Isolation between application context
	- Isolation of resources allowed security, as resources within a specific VM are under the control of the relevant program, and it would be harder to inadvertently modify them
- Each application runs in it's own environment
- All applications can run on one machine
	- Lowered maintenance costs
	- Easier to update system dependencies for individual applications
- Emulation of a full machine, including Operating System for each application running on server
- Physical resources represented as virtual cluster

### Containerisation days


Containers are analagously similar to VMs, but they have more relaxed principles of resource isolation as compared to VMs, insofar as applications share the operating system of the host machine.

The main advantages of containerisation
- Ease of set-up/tear-down
	- Enablement of Continuous integration - easy to roll back
- Decoupling of applications from infrastructure - container image is standalone from application code
- Vitals signs of application (resource consumption(?) etc.) are more easily observed
- Ensures consistency of final output across environments
- Higher level of abstraction than VMs 
	- VMs run an OS on virtual hardware, whilst Containers run an application upon an OS using logical resources for the purposes of isolation
- Loosely coupled architectures, that are easy to break down and distribute in different compostitions
	- Can be deployed and managed dynamically
	- 