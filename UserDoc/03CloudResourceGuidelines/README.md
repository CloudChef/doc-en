**Cloud Resource Guidelines**


The Cloud Resource Blueprint Service is based on blueprint modeling to define standard service frameworks and components, providing a rich set of out-of-the-box software components to visualize blueprints for automated deployment. After the service configuration is completed, the service is released as a service card, and the user applies for the cloud resource blueprint service through the service catalog.
For example, configuring a vSphere single-node virtual machine service is a typical scenario for a cloud resource blueprint service.
The following describes the specific operations of service request and service deployment.
# Service Request

## Fast Service Request

Users can select quick request in the service catalog. No need for service configuration, just select the required blueprint, and directly apply for service for automated deployment.
E.g:

+ Enter the service catalog. You can view the service card for the request database. The database service is bundled with multiple blueprints including: all pure database blueprints, Oracle (including clustered), MySQL (including clustered), MongoDB, DB2, SQL Server. .

+ Click on “Apply Database” to select the required blueprint to quickly apply for automated deployment.

 

## Service Catalog Request	

Users can apply for configured services or shared services published by the business group in the service catalog.

 Click “Service Catalog” in the left navigation bar, select a service, and click to enter the service application page.

 The details of the service are displayed at the top of the service request page:

Service Request - Service Details 
 
 +   Description:              Description of the service
 +   Basic information:        Service lease time and retention time configured by service configuration/business group configuration
 +   Topology:                 Topology diagram used by the service
 +   Component Configuration:  All components in the service topology diagram can be expanded to view the configuration information of each component
 +   Process Control:          Deployment/ Pre-dismounting/post-operation set on service configuration/business groups, and whether approval and email notification are required

  Fill in the relevant request parameters below the service request page:


+ Organization information
Business group:	If the service is a full business group, that is, a shared service, you need to select a business group (this business group needs to have a related resource bundle, otherwise it will not be allowed to apply); if the service has been assigned a business group, the business group does not need to be filled out.
Project:	If the project is divided under the business group, you can select the project.
Owner:	Select the owner of the service, the owner must be a member of the business group


+ Deployment information
Name:	If the service deployment name naming rule is configured for the business group, the service deployment name does not need to be filled in. The service deployment name is automatically generated according to the business group rules.If the business group name is not configured in the business group, you need to manually fill in the service.
Quantity:	Fill in the number of deployments, the default is 1
Execution time:	Can start service deployment at a specified time, accurate to the minute


+ Other information
Key-value label:	Checked by default, all server nodes use the same key-value label. If not checked, all server nodes under the service deployment will be listed, and key value labels can be set separately for each server node.
All Server nodes:	If you check the key-value label, you can set the key-value label for all server nodes.
Remarks:	Optional
Attachments:	Select a file as an attachment
Field information:	Fill in additional custom fields in the Service Design - Form interface


+ Request Parameters
Request Parameters:	If during service configuration, only "Allow modification" is selected (“Modify only when approved” is not checked), the application parameter field will appear. You can configure the relevant Server and Network parameters as required. 
Software Configuration:	If the “Add Software during request” is selected during service configuration, the software configuration bar will appear. You can add software to the computing node/software component of the service and click “Add Software”.
	Select the software to be installed and all software components will be listed
	Select relationship: “Install to” or “Depend on”
	Select the node to install to or depend on


 After completing the request, click “Apply” to directly deploy or wait for approval according to the business group process control. You can view the deployment status in “Deployments” - “My Deployments” (you can also view the deployment in the operation history in the upper right corner) or go to "Requests" - "My Requests" to view the approval process.

 ### Auto-fill

 When you apply for the service, if you cannot fill in the relevant parameters at one time, click “Save” to save the filled parameters, and at the next application, click “Load” to reload which will automatically fill the last filled in parameters. 

 ### Estimate Cost

 When you apply for a service, the platform can display the cost of this application (on a monthly basis).
	For the private cloud, after the administrator configures the accounting rules of the private cloud in the “Billing & Usage”-“Billing Rules”, the user directly uses the charging API to perform charging when applying for the service.。
	The public cloud needs to cache the public cloud's unit price API structure and then calculate the cost.


# Service Request


+ After the user applies for the service, if the service is configured with an approval process in advance, the service enters the pending approval state and waits for the approver to perform the approval operation.


+ If there is no approval process, the service request information enters the “My Request” message list, and the cloud resource service directly enters deployment state. Go to “My Deployment” to view the deployment information.


## My request


The service request initiated by the current user is displayed here. The steps to view the service details are as follows:

1.  Click “Requests” - “My Requests” on the left menu bar to view a list of users requesting services.

2.  This page displays the request number, service name, request type, title, business group, project, request status, request time, and completion time. Click on RequestNo. to view the details of the request.


## Pending approval

After the service application is completed, when the service is configured with the approval process in advance, the service enters the pending approval state, and the “Pending Approval” module displays the details of the service.

Approver can follow the steps below to view the details of the pending service:


1.  Click "Requests" - "Pending Approval" in the left navigation bar. The pending approval page displays the service details of the request to be approved.


2.  Display basic information of the approval request: request number, request type, service deployment name, applicant, business group, project, request status, request time.



## Approved Request

All requests that have been approved are displayed here.

Specific steps of viewing approved requests:


1.  In the left navigation bar, click "Requests" - "Approved". The approved page displays the parts of all the approval requests that you have approved.


2.  Page shows the basic information of the approval request: request number, request type, service deployment name. applicant, business group, project, request status, request time.




# Deployments


## Overview

My Deployment page allows you to view the status, details, monitoring, and more of the service deployment. After selecting the wizard request or service catalog request in the Service Catalog, the user can view the deployed service status on the service deployment interface. If the deployment has an approval process, the service deployment page can be redirected to the approval page to view the current approval process. If there is no approval, you can view the deployment details.


1.  After selecting "Deployment" - "My Deployment" in the left navigation bar, the user will see the service deployment list, click Advanced Search, according to the business group, stage (run, in progress, shutdown, failed, cancelled, deployed in the approval), status (normal, abnormal), owner, project to filter, or directly search operation


2.  In the service deployment list, users can select one or more service deployments to perform some operations quickly, including “stop”, “installation software”, “copy”, “extend expiration time”, “dismount”, “delete management information”, "Change Owner", more operations such as: "Change Project" "Change Business Group" and "Scale in/out"


3.  Click the service deployment name to view the details of the service deployment. The service deployment details information interface includes "Basic Information", " Topology", "Operation History", "Monitoring" (Monitoring of Instances and Application Components), and Operations at the Top


4.  Basic Information includes the name of the service deployment, business group, project, blueprint, resource bundle, cloud platform, and related information such as cost, status, and time. It also includes a list of input parameters for the service deployment and output result information. After the service deployment fails, some scenarios can be repaired offline. After the repair is successful, the service deployment status is changed, and the operation failure is changed to running.


5.  Topology includes blueprints, details, and process information for service deployment. Hovering over the service topology map will display the key information of the node. For example, the server node will display the instance name, guest operating system, IP address, memory, total disk space, number of vCPUs, CPU usage, memory usage, etc.


6.  Operation History shows the operation history of the service deployment


7.  Monitoring displays monitoring information applied to components in the deployment



### Service Deployment and Operation


You can perform operations on the service deployment in the service deployment list interface or by clicking the service deployment name to enter the service deployment details interface.

>「Note」The operation permissions of the service deployment are controlled by the business group and service configuration. Here we assume the user has the authority to operate. For your convenience, platform groups operations into several groups.



#### Change Organization Information 


Change owner

Changing the owner of a service deployment will also change the owner of all virtual machines under the service deployment. Choose the target owner, who is a member of the business group.

Change project 

Changing the project to which the service is deployed will also change the project of all virtual machines under the service deployment. Select the target project and select the user under the project.

Change business group 

All virtual machines under the service deployment will be changed to the new business group at the same time, and the relevant information such as the owner will be modified. Select the target business group, the project (optional), the owner (the member under the business group), and the resource bundle (the resource bundle under the business group). If the resource pool list is empty, it means that no resources are available on the business group.


#### Start Service Deployment {#Start Service Deployment .afff6}

The Start Service Deployment action is available if the service deployment is down. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".


#### Stop Service Deployment {#Stop Service Deployment .afff6}

If the service deployment is in a running state, you can "stop service deployment", which will shut down all virtual machines under the service deployment. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".


#### Dismount Service Deployment {#Dismount Service Deployment .afff6}

After the service is deployed, the cloud resources under the service deployment can be removed. Dismounting a service deployment will remove all new resources created in SmartCMP. If the service deployment includes shared resources, the shared resources will not be deleted; if the service deployment contains existing resources, such as LoadBalance "Use existing resources", the existing resources will not be deleted; if you are the resources owner after you import the resources, you can delete imported resources.



#### Re-execute deployment {#Re-execute deployment .afff6}

The deployment node can be re-executed after the service is deployed.

Steps:


1.  Click Re-execute Deployment to display the service deployment name, all compute nodes/storage node/software component nodes under the deployment, and deployment status


2.  Can be re-executed by selecting single or multiple nodes; enable timing, specify time for operation 


3.  Click "Submit" and wait for execution




#### Delete

Delete Management Information

Delete the information about the service deployment and related VMs on SmartCMP and keep them in the related cloud platform without deleting them.

Delete a node

The compute nodes, storage, and software components can be removed after the service is deployed. Click Delete Node to display the service deployment name, all compute nodes, storage and software component nodes under the deployment, and deployment status. You can delete the single or multiple nodes or enable scheduled time to operate.


#### Scale in/out
Expansion 

Expand the instance of the current deployment. The static IP deployment server does not support scaling. At least 1 instance can be scaled, up to 6. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".

 Extend the expiration time

To extend the lease expiration time of the service deployment, click to display the maximum number of deferrable times set in the business group and the number of deferred times, and choose which time to extend to, which is accurate to the minute.


Replication Service Deployment
After the service deployment is successful, the service request deployment environment can be copied to other cloud platforms or cloned to the current cloud platform. For example, copying vSphere service deployment to Aliyun, vSphere to vSphere, Aliyun to Ali Proprietary Cloud

Steps：


1.  Select the target service: select the target business group, project (optional), owner, and service, and select the current instance node as a template to copy/create to the target node in the selected service topology map.


2.  Configure parameters: fill in the service deployment name (if the business group has rules, it will be automatically generated according to the business group rules), service deployment lease expiration time, and configure other node parameters in the service topology map (require third-party support if cross-cloud replication)


3.  Click Submit and wait for execution.




#### Install software

Select the instance under Deployments and select the software you need to install. The software list is derived from the "Software Components" and allows you to change the property key values of the software.



# Instance


## Overview


Users can view and manage the instance list according to the following steps. The activation and operation need to be set at the business group level or service configuration level:

Specific operation steps:


1.  After selecting “My Deployment” - “Instance” in the left navigation bar, the user will see a list of instances. You can view the instance name, cloud platform, operating system, instance status (started, lost, stopped, etc.), health status, business group, project, service deployment, lease expiration time, retention expiration time, owner, IP address, label, installed software, resource label, etc. Other display columns can be selected by clicking "Show column". Filter tags by business group, project, etc.


2.  In the instance list, the user can select one or more instances to perform some operations quickly, including “start”, “reboot”, “suspend”, “stop”, “execute script”, “setup tag”, “enable/switch monitor”, "update monitoring agent", "update automation agent". The specific operation introduction will be expanded below


3.  You can also click on a instance to enter its details interface for management and operation. The virtual machine details interface includes “Basic Information”, “Operation History”, “Snapshot”, “Monitoring”, “Application List” and the top operation list.


4.  “Basic Information” includes some information about the virtual machine and its related hosts, the organization information of the virtual machine in the platform, and the CPU, memory, storage running status, VNC connection information, etc. of the virtual machine.


5.  “Operation History” includes the history of operations performed by this virtual machine.


6.  “Snapshot” displays the current snapshot information (snapshot name, creation time, etc.), click “Add” to create a snapshot.


7.  “Monitoring” includes monitoring data of the virtual machine CPU, memory, disk, and network (you can adjust the time span or average time to view historical monitoring data as needed)

>「Note」Only the VMs that are installed and monitored in the VM template can be seen in the monitoring after the deployment is generated. For details on how to configure the installation monitoring, see the chapter "VM Template".


8.  “Application List” displays the list of applications that are currently installed on the virtual machine.


9.  Day2 operation list includes a list of operations that can be performed by the virtual machine. The specific operation introduction will be expanded below.



### Instance Operation


On the instance list interface or click the instance name to enter the instance details page, you can perform the following operations on the instance. The operations are enabled or disabled by the business group/service deployment.

The (shut down) virtual machine can be started in real time, or it can be triggered (at some point in the future) by setting "Enable Timing".


#### Suspend (vSphere) {#SuspendvSphere .afff6}


The virtual machine that is suspended (on) can be triggered by timing (at some point in the future) by setting "Enable Timing".

Suspending multiple (powered-on) virtual machines can be triggered by timing (at some point in the future) by setting "Enable Timing".

>「Note」Only vSphere virtual machines has this option.


#### Stop {#Stop .afff6}


To stop (i.e., power off) the virtual machine (on the power-on state), you can trigger the task by timing (at some point in the future) by setting "Enable Timing".


#### Restart {#Restart .afff6}


Restart the virtual machine (on the power-on state) by setting "Enable Timing" and timing (at some point in the future) to trigger this task.

Restart multiple (powered-on) virtual machines, you can trigger this task by setting "Enable Timing" and timing (at some point in the future).


#### Monitoring and Agent


Add an automated agent
If the instance does not have an automated agent installed, you can install it by: entering the username and password/key pair with SSH and administrator privileges, and clicking "Execute" after the input is complete. If the port is not entered, you need to enter the port number in the instance details page, "SSH port".

Update an Automation Agent 

If the instance has an automated agent installed, it can be updated with this action.

Enable/Switch Monitoring

Currently, two monitoring methods are supported for the vSphere instance: built-in agent monitoring and cloud platform monitoring. Built-in agent monitoring includes pre-installed monitoring agent and WinRM/SSH monitoring agent (WinRM for Windows operating system, SHH for Linux operating system). Ccloud platform monitoring refers to reading monitoring data of virtual machine directly from vCenter and there is no need to install a monitoring agent.

Only built-in monitoring agents are supported for the OpenStack cloud platform.

Update Monitoring Agent

If the instance has built-in agent monitoring installed, it can be updated through this operation.



#### Create a Snapshot


 Create a Snapshot

Create a snapshot of the virtual machine, which can be triggered (at some point in the future) by setting "Enable Timing".

 Revert to Snapshot

To restore a virtual machine to a previous snapshot, you can trigger this task by setting "Enable Timing" and timing (at some point in the future).

 Delete a Snapshot 

Delete created snapshot

####  Adjust the configuration


 Adjust the configuration

Adjust the configuration (vCPU, memory) of the virtual machine or container node and click Submit.

#### Add a new disk


 Add a new disk

Add a new disk to the virtual machine, which can be triggered (at some point in the future) by setting "Enable Timing".

>「Note」Cannot be performed in the suspended state

Extend Disk 

To extend an existing disk to a virtual machine, you can trigger the task by timing (at some point in the future) by setting "Enable Timing".

>「Note」Support expansion through the cloud management platform or the disk created in the previous section. This operation cannot be performed in the suspended state.

 Delete a disk

Delete a disk other than the system disk on the virtual machine, including the disk added by the service configuration or the disk added by the operation.

 Add a New Logical Volume

Add a new logical volume to the Linux virtual machine, which can be triggered (at some point in the future) by setting "Enable Timing".

>「Note」Cannot be performed in the suspended state

Expand Logical Volumes

To extend an existing logical volume to a Linux virtual machine, you can trigger this task by timing (at some point in the future) by setting "Enable Timing".

>「Note」Support extensions that are deployed through the cloud management platform or created in the previous section. This operation cannot be performed in the suspended state.


#### vMotion Migration (vSphere) {#vMotion Migration vSphere .afff6}



Support for compute resource migration and storage migration in vSphere. Use vSphere's vMotion migration feature to migrate virtual machines between different hosts using different migration methods.

+ Calculate resource migration, select the target host, you can trigger this task by setting “Enable Timing” and timing (at some point in the future).


+ Storage migration:


<!-- -->

+ Linked clones: Select Require Storage to migrate the target instance to the selected storage.


+ Full clone: Select the provisioning mode (same source format, thin provisioning, thick provisioning delay zeroing, post provisioning zero); select virtual machine storage policy (retain existing virtual machine storage policy, datastore defaults, and other Define the storage policy); storage (determine the compatibility of the storage according to the selected storage policy, and display the space and proportion of each storage)


+ Enable Timing: Set the time to trigger this task at some point in the future


>「Note」Only available for vSphere virtual machines. When you migrate storage, you can retain the original provisioning mode and storage policy or modify it.



#### Remote terminal {#Remote terminal .afff6}


>「Note」OpenStack virtual machine remote terminal operation requires the use of VNC Web Client, your browser needs to support HTML5 Canvas and HTML5 WebSockets. If you need to know all the browsers supported by the VNC Web Client, you can visit <https://github.com/kanaka/noVNC/wiki/Browser-support>

#### WEB Remote Terminal (vSphere) {#WEB Remote Terminal vSphere .afff6}


vSphere's Web console client does not require special browser support.

>「Note」Only available for vSphere virtual machines.


#### Set the Instance Label {#Set the Instance Label .afff6}


>「Note」Each user can set a label for the instance without requiring an administrator to configure an operating license.

Key tags can be set for instances to classify and filter instances.

The instance label is used as follows:


##### Add tags


+ Add tags to the newly created instance:


1.  Select Deployments - Instance in the left navigation bar. On the instance list interface, select a instance.


2.  Click “More Actions” above, “Set Label”, the setting interface of the key value label appears.


3.  Fill in the key, value, click "Create" "Execute", the label is created successfully; you can also select the existing label, click "Execute". In the right column of the instance list, you can view the added instance label.


+ Add tags to imported instances:


1.  In the left menu, select “Infrastructure”, click “Resource Bundles”, select a resource bundle, and enter the Edit Resource Bundle interface.


2.  Go to the “Instance” page and click “Import” .


3.  Click the input box after “Label” to pop up the key value label creation page, enter the key value, create a new label, or select the existing label.



##### Modify/Delete Label:

On the instance list interface, select a instance; click “Set Label” to display the key label of the instance, which can be directly deleted and re-created.


##### Add a Network Card

Add a new NIC, take effect for all instances of the compute node, select the network label and IP allocation mode. At present, vSphere only supports DHCP. OpenStack and PowerVC support two IP allocation modes: DHCP and IP pool. OpenStack instance also supports manual IP assignment. 


##### Delete a network card

Delete the newly added NIC of the operation and maintenance, which will affect all instances of the node.


##### Mount NFS

Mount an NFS (Network File System) to the virtual machine, which can be triggered (at some point in the future) by setting "Enable Timing".

>「Note」This operation is available only when the NFS cloud platform and resource bundle are configured.


##### Execute script

A script in a script library of virtual machine can be triggered by timing (at some point in the future) by setting "Enable Timing" or by selecting an IP address.

>「Note」If you do not have an agent installed, you must enter the username and password of the virtual machine when executing the script.


##### Update the instance display name

Click "Update Instance Display Name" to reset the display name of the instance.


##### Reset the Operating System Host Name

Click "Reset OS Hostname" to reset the operating system hostname.

>「Note」Windows operating system can only perform this operation if the agent is installed.


##### Elevate  Linux User Permissions

Temporarily give a Linux user a Sudo privilege (free secret) for a while. If the instance has an automated agent installed, simply enter the username and permission usage time. If the instance does not have an automated agent installed, enter the administrator username and password (or select a key pair) and select an IP address.


##### Reset Password

Click "Reset Password" to reset the new password for the virtual machine.


##### Application level lifecycle operations

In the detailed interface of the instance, there is an application tab with a list of applications belonging to the instance. When an application is selected, the life cycle operation of the application appears, and the operations include "start", "stop" and "custom" operations.


## Cloud Resources   

Under the cloud resource menu, all the cloud resources are uniformly managed, the related information is displayed and the corresponding D2 operations to each cloud resource are provided.


Click on "Deployments" - "Cloud Resources" in the left navigation bar. On the left, you will see five menus: "Storage", "Container", "Network Resources", "PaaS" and "Software".


### Storage


#### Cloud hard disk {#Cloud hard disk .afff6}

Support unified management of OpenStack/Azure/Alibaba Cloud/QingCloud cloud hard disk.


1.  Click “Cloud Drive” under “Storage” and you will see the list of cloud drives.


2.  On the list of the cloud disk, you can view related information about the cloud disk: name, cloud platform type, status, business group, service deployment, project, owner, size (GB), mount status, mounted cloud host, and creation time


3.  Click on the name to go to the cloud drive details page. The cloud hard drive details page includes "Basic Information" and "Operation History"


4.  Basic Information page of the cloud drive details includes:


+ Basic information: name, cloud platform type, status, business group, service deployment, project, owner, cloud host to which the size is mounted, creation time, etc.


+ Organization information: service deployment name, service name, business group, tenant, project, etc.


+ Operations: Volume separation: remove the mount relationship between the cloud drive and the cloud host. Volume mounting: Establish mount relationship between cloud and cloud hosts. Resize: Supports resizing of hard drives (Azure/AWS)


+ Operation History: include the operation history of the cloud drive.



#### Object storage {#Object storage .afff6}

Supports unified management of object storage for AWS, Azure, and Alibaba Cloud, respectively S3, Blob, and OSS.


1.  Click “Object Storage” under “Storage” and you will see the object storage list.


2.  In the object storage list interface, you can view related information about object storage: name, cloud platform type, status, status, business group, service deployment, project, owner, creation time.


3.  Click on the name to enter the object storage details page. The object storage details page includes "Basic Information" and "Operation History"


4.  Basic Information page of the object storage details includes: Basic information: name, cloud platform type, status, owner, public access level, storage account, resource group, creation time, etc. Organization information: service deployment name, service name, business group, tenant, project, etc.


5.  Operation History: includes the operation history of the cloud hard disk.



#### Container Service {#Container Service .afff6}


Support to display various component information of Kubernetes in cloud resources, including deployment, container, service, route (Ingress), storage volume (PVC), configuration dictionary (Config Map), secret dictionary (Secrets), etc.


#### Network resource {#Network resource .afff6}


Supports OpenStack firewall (FireWall), floating IP (Floating IP) independent deployment and full lifecycle management. After the deployment is complete, you can view basic information and health status in Cloud Resources - Network Resources. It also supports OpenStack's load balancer (LoadBalance) and load balancing listener (Listener), as well as VMware NSX's virtual server (VirtualServer).


#### Load balancer {#Load balancer .afff6}


If the load balancer (LoadBalancer) is included in the deployment, you can view the details in Cloud Resources - Network Resources - Load Balancer after the deployment is successful.

1.  On the load balancer (LoadBalancer) list interface, display the name of the load balancer, cloud platform type, status, service group, service deployment, project, owner, IP address, creation time, etc. 


2.  Click on the name to go to the details page, including "Basic Information" and "Operation History"


3.  Operations (OpenStack):


+ Bind floating IP: Select a floating IP, bind the load balancer and floating IP, and start timing to perform operations at specific time.


+ Unbind floating IP: If the load balancer is bound to a floating IP, you can unbind the operation and start the operation at a specific time.



#### Load balancing listener {#Load balancing listener .afff6}

VMWare NSX / OpenStack / Azure load balancing listener is supported. VMWare NSX load balancing listener is VirtualServer, OpenStack load balancing listener is Listener, and Azure load balancing listener is LoadBalancerRule. The load balancer can listen for requests on multiple ports, each specified by a load balancing listener. After the deployment is successful, you can view the details in Cloud Resources - Network Resources - Load Balanced Listener.


1.  In the load balancer listener (Listener) list interface, display the name, status, description, business group, project, owner, protocol, cloud platform type, creation time, etc. of the load balancing listener.


2.  Click the name to enter the details page, including the "Basic Information" and "Operation History" interface, and operations of "Add Member" and "Delete Member".


3.  Operations – OpenStack


+ "Add members": add internal and external members. Select the instance to which you want to add members, specify the IP address, port, and weight. Bootable timing can be performed at specific times.


+ Delete member: Click to select the member to be deleted, you can set up timing to perform operations at a specific time.



#### Floating IP {#Floating IP .afff6}

Supporting OpenStack's floating IP (Floating IP), Floating IP can be deployed separately. After the deployment is successful, you can view the detailed information by selecting "Cloud Resources" - "Network Resources" - "Floating IP" in the left navigation bar.


1.  Select Cloud Resource - Network Resource - Floating IP to view the list of successfully deployed floating IPs. The interface displays the name of the floating IP, cloud platform type, status, business group, service deployment, and Project, owner, IP address, network, mapped address, creation time, etc.


2.  Click on the name to go to the details page, including "Basic Information" and "Operation History"


3.  "Basic Information" page, showing the basic information and organization information of the floating IP


4.  “Operation History” page, showing the operation history. When clicked, the operation details will be displayed below the operation history list.


5.  Operations:


+ “Associated Port”: If the current floating IP is not associated with any port, the “Associated Port” operation will be displayed at the top of the details page. After clicking, select the port to be bound in the bullet box. All unassociated ports (Ports) in the OpenStack cloud platform will be listed in the drop-down box. Select "Submit" after selecting.


+ “Unbind”: If the current Floating IP has been associated with the port, the “Unbind” operation will be displayed at the top of the details page. Click “Submit” to enable the operation at a specific 



#### Firewall {#Firewall .afff6}


Support for OpenStack Firewall as a service, Fwaas for OpenStack objects such as projects, routers and router ports. The core concepts of the OpenStack firewall are firewall policies and firewall rules. A policy is an ordered collection of rules. In the left navigation bar, select "Cloud Resources" - "Network Resources" - "Firewall" to view the deployed firewalls.


1.  Select Cloud Resources - Network Resources - Firewall to view the successfully deployed firewall list interface, which displays the name of the firewall, cloud platform type, status, business group, service deployment, project, owner, Policy, routing, activation status, administrator status, creation time, etc.


2.  Click on the name to go to the details page, including "Basic Information" and "Operation History"


3.  Basic Information: displays basic and organizational information about the firewall.


4.  Operation History page: Display the operation history. When clicked, the operation details will be displayed below the operation history list.


5.  Operations：


+ Update Firewall: Click to select an existing firewall policy or create a new firewall policy. Check "Use existing policy" to list all available firewall policies in the OpenStack cloud platform under the current business group. If it is not checked, create a new firewall policy, fill in the policy name (required), policy description (optional), choose whether it is shared, audited, or timed. Click “Submit” after the operation is completed.


+ Update Firewall Policy: This page lists a list of all currently available rules. Support for using existing rules and creating new rules. If you use an existing rule, check the rules that will be used in the list. If you create a new rule, click   on the upper right corner of the list to display the new rule interface:

  Fill in the basic information: name, description, protocol (required, TCP, UDP, ICMP, and any), action (required, allowed, denied), source IP, source port, destination IP, destination port, whether the selection is shared and activate.

  You can select the location of the new rule, specify that the current rule is inserted before a rule (before the rule), or specify that the rule is inserted after a rule (after the rule). If both are specified, the former has a higher priority.

 >「Note」：A firewall policy can be associated with multiple rules, but rules can only be associated with one policy.


+ Delete firewall rules: Delete the associated rules in the firewall. After deletion, they will not be recoverable. You can select multiple rule deletions at the same time, or you can start timing to perform operations at specific times.


#### Security group {#Security group .afff6}


Support for displaying security groups for OpenStack, AWS, Azure, and Alibaba Cloud. If the security group component is deployed, the deployed security group components are viewed in Cloud Resources - Network Resources - Security Groups.


1.  On the Security Group list page, display the security group name, cloud platform type, status, business group to which it belongs, service deployment, project, owner, creation time, etc.


2.  Click on the name to go to the details page, including the "Basic Information" and "Operation History". 


3.  Basic Information page displays basic information, organization information, and inbound/outbound security group rules for the security group.


4.  Operation History shows the operation history. When clicked, the operation details will be displayed below the operation history list.



#### Domain Name System DNS {#Domain Name System DNS .afff6}


Support OpenStack Domain Name System DNS. If the DNS component is deployed, the deployed DNS components will be viewed in "Cloud Resources" - "Network Resources" - "Domain Name System DNS".


1.  On the Domain Name System DNS list, display the DNS name, status, business group, project, owner, DNS type, DNS domain, DNS server, DNS parameters, etc.


2.  Click on the name to go to the details page, including the "Basic Information" and "Operation History".


3.  Operations  


+ Update DNS: update DNS parameters, DNS type cannot be changed



### PaaS resources


Supports independent deployment and full lifecycle management of relational databases (RDS) of AWS, Azure,and Aliyun, supporting relational database as a service (RDS as a Service) and web applications. After the deployment is complete, you can view basic information and health status in Cloud Resources - PaaS Resources.


### Software Resources


> Support unified display and management of software resources.


#### Software {#Software .afff6}


1.  Select Cloud Resources - Software Resources - Software to view a list of successfully deployed software that displays the software name, cloud platform type, status, business group, service deployment, project, owner, version, system type, creation time, etc. Filter your business groups, status, projects, or owners with advanced search, or use normal search for quick targeting.


2.  Click on the name to go to the details page, including "Basic Information" and "Operation History"


3.  Basic Information displays basic information, organization information, and parameters of the software.


4.  Operation History displays the operation history. When clicked, the operation details will be displayed below the operation history list.


5.  Operations:


> The operations displays the corresponding operations according to the operation definition of the software in "Service Design" - "Software Components", for example, start, stop, delete, create, configure,etc.



## Host Map


The host map can display the health status of the instance and container and display different colors according to the status of the performance indicator. If the instance or container is not configured for monitoring, it is grayed out by default.

Move the mouse to the instance to display the instance name

Click to show details：

+ Basic information: IP address, operating system, number of vCPUs, memory, total disk space

+ Organizational information: business groups, projects, owners

+ Performance monitoring metrics: memory usage, CPU usage, disk usage

>「Note」Will not display performance monitoring indicators if monitoring is not installed.

Displayed content can be filtered according to your needs, such as all or installed monitoring or not installed monitoring, filtering by cloud platform, business group, project screening, label, etc.


## Monitoring & Alert


Alert provides the user with the virtual machine and any application self-service alert configuration.

In the left navigation, select "Monitoring & Alert". There are 5 secondary menus under the Monitoring & Alert, followed by "Alert Policy", "Alert Rules", "Triggered Alert", "Host Monitoring" and "Host Alerts".


### Alert Policy

Used to define the conditions under which the selected object type (such as instance/application/container, etc.) triggers an alert. Click the second level menu "Alert Policy" under "Monitoring & Alerts" on the left navigation to display the alert policy list. The list includes the alert policy name, category, type (downtime, threshold or prediction), creation time, and creator. Users may add, edit, delete, etc. alert policies.



#### Add an Alert Policy {#Add an Alert Policy .afff6}


1.  In the navigation tree on the left, choose Alert Policy, enter the alert policy list interface, and click Add to enter the alert policy interface.


2.  On the Add Alert Policy page, define the basic information of the alert policy. Enter the name of the alert policy in turn and select the alert category and alert type. The alert category supports alerts for instances, applications, and containers. The alert type supports downtime alerts, threshold alerts, and predicted alerts for instances, threshold alerts and predicted alerts for applications, thresholds for containers, and predictive alerts.


3.  Define the triggering conditions of the alert policy according to different alert types selected.


+ Downtime alert: Input time (minutes). After the instance loses response within the specified time, it will trigger the downtime alert. 


+ Threshold alert: Select the maximum/minimum/average value of virtual machine/container’s indicator (such as memory usage (percentage), CPU usage (percentage), POD memory usage, etc.) in the past minutes/hours. If the value is less than / less than or equal to / greater than / greater than or equal to certain value, an alert will be triggered.


+ Predictive alert: Based on the value of the indicator in the past minutes / hours / days (such as memory usage (percentage), CPU usage (percentage), etc.), predict those in future time range (minutes / hours / days). If the value of the indicator is less than/less than or equal to / greater than / greater than or equal to certain value, an alert will be triggered.


4.  Click "Save". The alert policy is added successfully and the alert policy list interface will be displayed.



#### Edit an Alert Policy {#Edit an Alert Policy .afff6}


Click "Alert Policy", select a line of added alert policy, the toolbar "Edit" button becomes available, click the "Edit" button, or directly click the alert policy name to enter the alert policy editing interface.

#### Delete an Alert Policy {#Delete an Alert Policy .afff6}


Click "Alert Policy" to select an alert policy that has been added. The "Delete" button on the toolbar becomes available. Click the "Delete" button to confirm the deletion prompt, and the alert policy is deleted successfully.

### Alert Rules


Supports the user to define the scope to which the selected alert policy is applied and the notifications and actions that are triggered.

Click the secondary menu "Alert Rules" under "Monitoring & Alerts" on the left navigation to display the alert rules list, including the alert name, alert level, alert policy name, range, object, status, creation time, creator, and so on. Alert rules can be added, edited, enabled, disabled, deleted, and so on.

#### Add an Alert Rules {#Add an Alert Rules .afff6}


1.  Click "Alert Rules", enter the alert rules list interface, and click "Add".


2.  Define basic information. Enter the name, select the alert policy, alert range, and alert level. After triggering xx times, it will automatically upgrade to a higher level. This supports alerts for business groups, projects, service deployments, and VMs. The alert object is based on the selected alert range and the alert level is warning and danger.


3.  Define the user, role, or email address to be notified when the alert is triggered.


4.  You can define the behavior after the alert is triggered. After triggering the behavior, you can set up to xx operations and stop the automatic execution.


+ Support instance expansion operations: shrink one node horizontally, scale one node horizontally, shut down, restart, expand 5G logical volume, increase 1G memory (vSphere), add 1 vCPU (vSphere), etc.


+ Support for the expansion of the container: reduce the number of 3 copies, increase the number of 2 copies, etc.


5. 	 Click “Save” to return to the alert rules interface.



### Triggered Alert

Click "Triggered Alerts" to display the list of triggered alerts, including name, target, type, first trigger time, last trigger time, and alert status. The alert status is divided into firing, muted, and resolved. It is also possible to recover, pause, and release the triggered alerts in the list.


1.  Select a triggered alert. "Pause" and "Relieve" in the toolbar will become available. Click "Pause", there will be a prompt. After confirmation it will shows that the operation is successful.


2.  Click on the alert name in the list to view the historical data. This page shows the object triggered the alert, the level of the alert, the triggered condition, the business group, the owner, the IP address, the alert chart (the adjustable time range help flexibly view the alert data for each time period), and the subsequent operation history of the alert.


3.  Objects triggered alerts can be linked, such as service deployment link to service deployment monitoring page, instance link to instance monitoring page, application link to service deployment monitoring page.


## Resource Analysis


### Report

You can view related billing reports and instance status reports or other custom reports in Resource Analysis - Reports. In Settings - Reports, you can choose to enable or disable a report for different user roles. Support filtering criteria for multiple dimensions of the report and displaying column selection for the header. Excel files can be exported.

>「Note」For the customized configuration of the report, please consult CloudChef engineer.


## 回收站


All services are manually removed or automatically dismounted after expiration, and will be placed in the Recycle Bin for reservation, allowing users to recover when needed. 
