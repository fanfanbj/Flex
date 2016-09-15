# About
Flex is a plateform solution which provides to deploy containerization applications, manage those applications's lifecycle. At the meantime, it includes solutions to manage containerization cluster,monitor,loggregation and etc.

Has the following functions:

* application management (stage application and scale-out,log, monitor, debug, health check and so on.)
* cluster management
* host management (add host, host component monitor, host system monitor and so on.)
* network management
* multi-tenant management

Has the extra functions:

* registry management
* stack
* application store (middleware services and big data components)
* CI/CD
* config server
* Rolling update

# Product Subsystems or Components
The following picture shows an overview of the functional architecture. It represents all components of the product which produce some functionality. and how they are placed with each others.
![image](https://github.com/fanfanbj/Flex/blob/master/flex.jpg)

# OpsManager
OpsManager is a plateform management, which is micro-service framework. it will use consul and fabio as service registration and service load-balance.

* User Interface: Console and API Client
* Micro-service framework
* Backplane including Consul for service-register and health-check, and fabio for service zero-conf load-balance.
* Comon service including mysql and other common services, for self-platform and will be place in appStore in the future.
* all mico-services will use one mysql service, with seperate-table to be seperate.


# Elastic Runtime
Elastic Runtime is a container management system, which is based on mesos.

* core components: mesos-master,zookeeper, mesos-slave, marathon.
* compose-executor and app staging & running can be store in app DB, for metrics and log or debug.
* each host in cluster has main services, including: service discovery (consul and fabio), sshd, access service for loggregator and other services, such as: network-agent and so on.

#TODO
* consider OpsManager HA.
* mesos components in elastic runtime should be changed by other framework, such as: kubernetes and swarm.