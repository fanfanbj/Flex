# About
Flex is a plateform solution which provides to deploy containerization applications, manage those applications's lifecycle. At the meantime, it includes solutions to manage containerization cluster,monitor,loggregator and etc.

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

# RoadMap
* －> Container solution and integrate with distribution system solution(mesos，kubernetes，swarm) 
	* －> OpsManager
		* -> provides common service solutions, to be Paas in the future.

# Product Subsystems or Components
The following picture shows an overview of the functional architecture. It represents all components of the product which produce some functionality. and how they are placed with each others.
![image](https://github.com/fanfanbj/Flex/blob/master/flex.jpg)

# OpsManager
OpsManager is a management console, which is micro-service framework. it will use consul and fabio as service registration and service load-balance.

* User Interface: webUI and API Client
* Micro-service framework
* Backplane component including Consul for service-register and health-check, and fabio for service zero-conf load-balance.
* Comon service, as basic service in OpsManager including mysql and other common services, whose are for self-platform and will be added into appStore in the future for apps using.
* all mico-services in OpsManager will use one mysql service as share database, with seperate-tables policy to be seperated.


# Elastic Runtime
Elastic Runtime is a container management system, which is based on mesos.

* core components: mesos-master,zookeeper, mesos-slave, marathon.
* compose-executor and app staging & running should be stored in app DataBase, for metrics and log or debug to use.
* each host in cluster has main services, including: service discovery (consul and fabio), sshd，and access service for log and metrics and other services, such as: network-agent and so on.

#TODO
* Consider OpsManager High Availability.
* mesos components in elastic runtime should be replaced by other framework, such as: kubernetes and swarm.