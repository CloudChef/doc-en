

**My Deployment**

My Deployment page allows you to view the status, details, monitoring, and more of the service deployment. After selecting the wizard request or service catalog request in the Service Catalog, the user can view the deployed service status on the service deployment interface. If the deployment has an approval process, the service deployment page can be redirected to the approval page to view the current approval process. If there is no approval, you can view the deployment details.

1. After selecting "Deployment" - "My Deployment" in the left navigation bar, the user will see the service deployment list, click Advanced Search, according to the business group, stage (run, in progress, shutdown, failed, cancelled, deployed in the approval), status (normal, abnormal), owner, project to filter, or directly search operation

2. In the service deployment list, users can select one or more service deployments to perform some operations quickly, including “stop”, “installation software”, “copy”, “extend expiration time”, “dismount”, “delete management information”, "Change Owner", more operations such as: "Change Project" "Change Business Group" and "Scale in/out"

3. Click the service deployment name to view the details of the service deployment. The service deployment details information interface includes "Basic Information", " Topology", "Operation History", "Monitoring" (Monitoring of Instances and Application Components), and Operations at the Top

4. Basic Information includes the name of the service deployment, business group, project, blueprint, resource bundle, cloud platform, and related information such as cost, status, and time. It also includes a list of input parameters for the service deployment and output result information. After the service deployment fails, some scenarios can be repaired offline. After the repair is successful, the service deployment status is changed, and the operation failure is changed to running.

5. Topology includes blueprints, details, and process information for service deployment. Hovering over the service topology map will display the key information of the node. For example, the server node will display the instance name, guest operating system, IP address, memory, total disk space, number of vCPUs, CPU usage, memory usage, etc.

6. Operation History shows the operation history of the service deployment

7. Monitoring displays monitoring information applied to components in the deployment

## Service Deployment and Operation{#7.3.2	Service Deployment and Operation}

You can perform operations on the service deployment in the service deployment list interface or by clicking the service deployment name to enter the service deployment details interface. The operations of the service deployment are controlled by the business group and service configuration. You can choose to enable or disable the corresponding \operations in the "Business Group" - "Service Deployment Ops Entitlement" to the corresponding role. If enabled, you can also specify whether approval is required and its approval template. If enabled, you can select the service group configuration for the service or the business group configuration in the Service Design - Catalog Config - Service Deployment Ops Entitlement to delete the operations. 

### Refresh status
Users cannot view the details of the lost virtual machine. In some business scenarios, the lost virtual machine rejoins the platform and needs to be = manually refreshed the state. At the same time, it must be able to support the refresh of other cloud resource status.
+ Support for batch refresh: in the service deployment list, select one or more deployments
+ Click the “Refresh Status” button to manually refresh the status. The button to refresh the state is placed first.
+ After refreshing, the status of each service deployment in the background updates including modification of specification configuration, addition of disk and modification of IP address and the refresh result is returned by notification. The refreshed operation is logged to the operation history.
+ When performing operations on the instance, SmartCMP can refresh the correct state of the virtual machine based on the UUID of the virtual machine.•	When performing operations on the instance, SmartCMP can refresh the correct state of the virtual machine based on the UUID of the virtual machine.




### Start service deployment

The Start Service Deployment action is available if the service deployment is down. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".

### Stop Service Deployment
If the service deployment is in a running state, you can "stop service deployment", which will shut down all virtual machines under the service deployment. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".


### Install software

Select the instance under Deployments and select the software you need to install. The software list is derived from the "Software Components" and allows you to change the property key values of the software.

### Change owner

Changing the owner of a service deployment will also change the owner of all virtual machines under the service deployment. Choose the target owner, who is a member of the business group.

### Change project

Changing the project to which the service is deployed will also change the project of all virtual machines under the service deployment. Select the target project and select the user under the project.

### Change business group

All virtual machines under the service deployment will be changed to the new business group at the same time, and the relevant information such as the owner will be modified. Select the target business group, the project (optional), the owner (the member under the business group), and the resource bundle (the resource bundle under the business group). If the resource pool list is empty, it means that no resources are available on the business group.
 


### Scale in/out

Expand the instance of the current deployment. The static IP deployment server does not support scaling. At least 1 instance can be scaled, up to 6. This task can be triggered by timing (sometime in the future) by setting "Enable Timing".


### Replication Service Deployment
After the service deployment is successful, the service request deployment environment can be copied to other cloud platforms or cloned to the current cloud platform.

Common application scenarios: for example, copying vSphere service deployment to Aliyun, vSphere to vSphere, Aliyun to Ali Proprietary Cloud

Steps:

1. Select the target service: select the target business group, project (optional), owner, and service, and select the current instance node as a template to copy/create to the target node in the selected service topology map.

2. Configure parameters: fill in the service deployment name (if the business group has rules, it will be automatically generated according to the business group rules), service deployment lease expiration time, and configure other node parameters in the service topology map, for each compute node, you can choose Copy or create (deploy a new machine from the template)

3. Click Submit and wait for execution.

>「Note」Require third-party support if it is cross-cloud replication.

### Extend the expiration time

To extend the lease expiration time of the service deployment, click to display the maximum number of deferrable times set in the business group and the number of deferred times, and choose which time to extend to, which is accurate to the minute.


### Dismount Service Deployment

After the service is deployed, the cloud resources under the service deployment can be removed. Dismounting a service deployment will remove all new resources created in SmartCMP. If the service deployment includes shared resources, the shared resources will not be deleted; if the service deployment contains existing resources, such as LoadBalance "Use existing resources", the existing resources will not be deleted; if you are the resources owner after you import the resources, you can delete imported resources.

### Delete Management Information

Delete the information about the service deployment and related VMs on SmartCMP and keep them in the related cloud platform without deleting them.

### Delete a node 
The compute nodes, storage, and software components can be removed after the service is deployed. Click Delete Node to display the service deployment name, all compute nodes, storage and software component nodes under the deployment, and deployment status. You can delete the single or multiple nodes or enable scheduled time to operate.


### Re-execute deployment

The deployment node can be re-executed after the service is deployed.
Steps:

1. Click Re-execute Deployment to display the service deployment name, all compute nodes/storage node/software component nodes under the deployment, and deployment status

2. Can be re-executed by selecting single or multiple nodes; enable timing, specify time for operation 

3. Click "Submit" and wait for execution
























