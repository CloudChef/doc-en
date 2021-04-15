



**Backup and security**

Through SmartCMP, cloud resources can be effectively managed and used according to the internal organizational structure of the enterprise. At the same time, SmartCMP also pays attention to how to use resources more safely. The security here includes two aspects, one is safe access and use of resources, the other is data backup And recovery.

+ The user accesses the virtual machine through the bastion host, helping to build a seamless connection between users, permissions, and resource management, which not only ensures that the cloud operation permissions can be controlled and audited, and the compliance can be followed, but also provide users with excellent use experience.

+ System not only integrates the built-in bastion host, but also supports docking with third-party bastion hosts. Different bastion hosts can be configured for different resource bundles. When deploying resources, resources will be automatically registered to the bastion host configured by the resource. When the machine and resources are uninstalled, it will be automatically unbound from the bastion host, and the user does not need to install extra software or open multiple control interfaces separately.

+ When users access the remote instance, they need to pass through the bastion host. We support multiple remote protocols based on cloud platform/RDP/VNC, provide a unified operation entrance, and build a safe and efficient operation channel.

+ Provide a sound and compliant operation audit, including functions such as comprehensive operation records, operation videos, online video playback, retrospective operation failures, and manual interruption of abnormal operations. Every time the operation personnel log in to the virtual machine through Web SSH for operations, they will automatically use the Web SSH service of the bastion host. Each connection will generate a session record operation. The auditor can view the operations through real-time monitoring. If there is any violation of the rules, you can manually terminate one or more sessions. You can also view the detailed information of the session through the session history, and view the video record of the operation through video recording.



+ In addition, SmartCMP has been docked with the Veeam backup platform. After docking with the backup platform, the virtual machine will have two more buttons "backup and restore". Users can self-service backup of individual files, folders, entire virtual machines and applications as needed.

+ Flexible choice of backup point, you can quickly restore the backup data to the current instance. The user will view the execution process and results in the operation history for the backup and restoration operations performed on the resources.

At this point, through the CMP single console, the use of bastion hosts, cloud resource backup, recovery management and self-service are realized to meet the internal backup needs of the organization, ensure service security and business continuity, reduce the burden on IT personnel, and reduce operation risk.


The specific usage method is described below.

# Bastion Host{#Bastion Host}

SmartCMP supports accessing virtual machines through bastion hosts and scheduling various bastion hosts through a unified HTTP request.

Core usage scenarios: 

+ Permission management: Integrate the access control of the bastion host and the platform (the platform and the bastion host are connected to the permission system, set user permissions, and set whether users can connect to the virtual machine through SSH or RDP. 

+ User management: all users accessing the virtual machine need to go through the bastion host. 

+ Operations: after the virtual machine is created, register the virtual machine to the bastion host; after the virtual machine is deleted, log out the virtual machine from the bastion host; after the virtual machine changes, update the bastion host. For example when a virtual machine’s owner is changed, the registration information of the virtual machine in the bastion host is modified synchronously.

+ Session management and video playback: The platform also supports the bastion host session management function. When the user performs operations on the remote instance through the bastion host, a real-time session link will be formed, and the tenant administrator can view the current ongoing session. If an exception is found, the administrator can manually terminate one or more sessions by clicking terminate to disconnect the corresponding user's session. User can also view the history of all the sessions, learn the details of each historical session, and click playback to view the recording.

## Dock Bastion Host

The platform supports the docking of Guacamole bastion host and Anheng bastion host, with Webssh and remote terminal, which is convenient for users to remotely operate.

Take the Guacamole bastion host as an example, the specific configuration steps are as follows:

Specific configuration steps:

+ Specific steps for accessing Guacamole (ie Apache Guacamole) bastion host: Click "Backup & Security"-"Guacamole" on the left navigation bar, click Add, fill in the bastion host information, name (virtual machine name), description, Guacd Address (that is, the URL link of the bastion host) and Guacd port (that is, the access port of the bastion host). SmartCMP uses Cloudchef-Integration to verify if the login information is correct.

> Connect to third-party bastion hosts, for example: Qizhi bastion hosts, access through the "bastion host entrance". "Guacamole bastion host" is the embedded bastion host management interface of SmartCMP.

+	Bind the bastion host to the resource bundle: Click the "Infrastructure"-"Resource Bundle Management" on the left navigation bar, and specify one of the bastion hosts that have been connected. For example: when adding a vSphere resource bundle, bind the bastion host Guacd, the virtual machine deployed using the vSphere resource bundle will be automatically registered to the bastion host, and the virtual machine deployed using the vSphere resource bundle will be automatically unregistered from the bastion host when it is uninstalled. 

+	Use of the bastion host. After the vSphere resource bundle is bound to the bastion host, use the vSphere resource bundle to successfully deploy the instance. Click the left navigation bar "Deployments"-"Instance"-"Overview" tab, select Remote protocol types, including: based on cloud platform, RDP or VNC (choose based on RDP or VNC, you need to select the remote protocol port). After the selection is completed, click "Remote Terminal" and you can directly pass "RDP or VNC". The instance is configured to open the remote terminal on the cloud platform. You can modify the parameters of the protocol information through the remote terminal, for example, modify the user name and password of the virtual machine.
 
+ Every time the operation personnel logs in to the virtual machine through Web SSH for operation, system will automatically use the bastion host's Web SSH service, and each connection will generate a session record of operation. Audit personnel may click on the "Backup & Security"-"Guacamole"-active session on the left navigation bar to check if there's any illegal operation, if found, they can manually click the "terminate" button to immediately terminate the session.

+ Click "Backup & Security"-"Guacamole"-Session Management on the left navigation bar to view the detailed information of the session, including: host name, IP address, protocol, Guacd name, user name, start time, duration and operation recording. Click Play to play the operation video online.


# Backup system{#Backup system}

SmartCMP supports fast and reliable backup of all instances on the vSphere cloud platform based on Veeam. Configure the backup management platform and bind the resource bundle to the backup management platform. The instances deployed in this resource bundle can be managed by Veeam. Supports recovery of individual files, entire virtual machines, applications, and more, ensuring service security and high availability.

Core usage scenarios: 

+	Backup: It is an instant backup (that is, manual backup). Click this operation to trigger a backup operation. The backup parameters may include the name of the backup file. The parameters need to be configured. You can view the execution process and results of backup operations (successful or failed backups) in the operation history. 

    For example: backup the current entire instance, similar to taking a snapshot

+	Restore: Supports selecting a backup point and restoring in the current instance (The backup point is a list, allowing the user to select the name of the backup file, time information, more additional parameters need to be configured in the form. Click on the backup point and trigger the restoration process restoring the data of the backup point to the current instance.) The execution process and result of the restoration operation (successful restoration or failure) can be viewed in the operation history. 
    
    For example: a backup copy of the instance is restored to the current cloud virtual machine


Specific configuration steps: 

+	Backup management portal configuration: Click "Backup & Security"-"Backup Management Platform" on the left navigation bar, click Add, fill in Veeam information, name (name of Veeam system platform), description, Veeam address (i.e. URL link of Veeam platform) , Username and password (i.e. login username and password for Veeam platform) 

+	Bind to the resource bundle: Click the "Infrastructure"-"Resource bundle Management" cloud platform resource information tab on the left navigation bar to specify the backup management platform that has been connected. For example, when adding a vSphere resource bundle, bind the backup management platform Veeam, and the virtual machines deployed using the vSphere resource bundle will be automatically associated with Veeam, and the instance will be managed through the backup management platform. 

+	Backup and restore operations. After the vSphere resource bundle is bound to the backup management platform Veeam, the instance successfully deployed using the vSphere resource bundle. Click Deployments"-"Instances" on the left navigation bar. Support basic "Backup" / "Restore" operation. 



# Audits


Support records of user access and operation information. The tenant administrator and sysadmin have this permission by default. If you need to add this permission to other roles, please add a role and add this permission. 

For details, see [Roles](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/Roles.html)

Click "System Management"-"Operation Audit" on the left navigation bar, you can see the operation records of the tenant. It displays the operator, operation object, operation name, operation parameter, status, and operation time. You can use "Advanced Search" for quick filtering and positioning. It supports the filtering of operators, statuses, operating objects,and start and end times. You can also use ordinary search functions.
