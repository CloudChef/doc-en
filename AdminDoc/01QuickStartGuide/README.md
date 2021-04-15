
**Admin Quick Start Guide**


SmartCMP mainly has two service scenarios, one is the cloud resource blueprint service scenario; the other is the ticket service scenario. 
+	Cloud resource blueprint service scenario
The Cloud Resource Blueprint Service is based on blueprint modeling to define standard service frameworks and components, providing a rich set of out-of-the-box software components to visualize blueprints for automated deployment.
For example, configuring a vSphere single-node virtual machine service is a typical scenario for a cloud resource blueprint service.
After the blueprint is modeled by the administrator, the service configuration can specify the resources and parameters that the user can apply for, and form a standard service based on the blueprint. After the release, the user can apply for self-service and automate the delivery.

+	Ticket service scenario
There are two types of ticket services:
1. Apply for non-standardized resources (for example, apply for a cloud resource blueprint service to uninstall a service deployment. This action is a typical service scenario for ticket services) 
2. Services that require IT manual intervention (for example, manual ticket service for resetting passwords. This action is also a typical service scenario for ticket services)

>「Note」Please refer to [Quick Configuration of Cloud Resource Blueprint Services](#QuickConfigurationofCloudResourceBlueprintServices) for more cloud resource blueprint services. For detailed ticket service please go to [Request service Management](https://cloudchef.github.io/doc-en/AdminDoc/08RequestServiceMgmt/)


When using the system release service for the first time, you need to do the following to configure the system:

1.  Configure the cloud platform portal: administrator login information such as vSphere and OpenStack. 

2.  Add IP Pool: Define the range of available IP addresses

3.  Define resource bundles: configure available physical resources and set quotas, such as CPU, memory, storage, network, etc. 

4.  Define business groups, associated personnel, resource bundles, configuration approval process, deployment specifications, etc.

5.  Define virtual machine templates: Select the cloud platform and the corresponding template or image

6.  Define blueprints: define the architecture of the service and automate the installation logic

7.  Configure and publish the service: associate the blueprint to the service group and resource bundle, and configure the deployment parameters, such as selecting a VM template.

8.  Request service: Apply for service in the service catalog. You can also enable the guided application function of the business group in the "Organization" - "Business Groups"

9.  Self-service operation: View detailed information about service deployment, instances or cloud resources in Deployment menu, and perform self-service operation. 

The next chapter will explain how the administrator configures the first cloud resource, publishes and requests the service. 

# Log in


+ Enter SmartCMP IP in browser, such as: http：//SmartCMP-Public-IP/#/login
+ Enter username & password.

# Configure cloud platform portal


The cloud platform portal defines the cloud infrastructure resources of the public cloud, private cloud, container, or physical machine that SmartCMP manages. Different cloud infrastructure account has different forms and acquisition methods. The administrator can complete the registration of the cloud platform infrastructure by filling in the corresponding infrastructure access information. 

>「Note」Please use the tenant administrator or infrastructure administrator to log in to the SmartCMP platform. Public cloud access information acquisition method, please refer to [Add Aliyun Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20Aliyun%20Cloud%20Platform)

## Add vSphere Cloud Platform

1.  Go to "Infrastructure" - "Cloud Entries", select "vSphere" and click "Add"

2.  Enter the required parameters (please input the relevant parameters according to your real environment, the example only gives a reference)

|Parameter |Description |Example|
|:------:|:------:|:-----:|
|Cloud name|vSphere cloud platform name|A--vCenter|
|Username|vSphere Username|administrator@vsphere.local|
|Password| vSphere Password |Confirm Password |                        
|URL|vSphere API URL |192.168.xx.xx|
|Port|API port|443|
|Data Center|Data center location|Shanghai|
|Connect VMware NSX|NSX cloud platform (need to add VMware platform first)|Select the corresponding NSX cloud platform name|


3.  Click Verify to verify the connection to the vSphere virtualization platform. If the input parameters are incorrect, an error is displayed. If the configuration is correct, the connection is successful.

4.  After the verification is successful, click “Submit” and the vSphere virtualization platform is successfully connected.

## Add OpenStack Cloud Platform

1.  Go to "Infrastructure" - "Cloud Entries", select "OpenStack" and click "Add"

2.  Enter the required parameters (please input the relevant parameters according to your real environment)


|Parameter|   Description|                        Example|
|:------:|:------:|:-----:|
|Cloud name |    OpenStack cloud platform name|         OpenStack|
|Authentication URL|    OpenStack keystone认证URL|   http://xxx.xxx.xxx.x:500/v2|
|API version |   Select API version|   Version 2|
|Tenant name |  Tenant name | admin|
|Username|     Username|   admin|
|Password|       Password | Confirm Password|     
|Region|     Region name |   RegionOne|
|Data Center|   Data center location| Shanghai|

3.  Click Verify to verify the connection to the OpenStack virtualization platform. If the input parameters are incorrect, an error is displayed. If the configuration is correct, the connection is successful.

4.  After the verification is successful, click “Submit” and the OpenStack virtualization platform is successfully connected.

## Add Aliyun Cloud Platform

You can add an Aliyun Cloud platform using following steps:

1.  Go to "Infrastructure" - "Cloud Entries", select "Aliyun"

2.  Click "Add" and enter following information:

|Parameter|Description  |Example|
| :------:|:------:|:-----:|
|Cloud name|       Aliyun cloud name|   Aliyun|
|Access Key ID|   Access Key ID|   |
|Secret Access Key|     Aliyun Secret Access Key  |   |

3.  Click “Verify”. After the connection is successful, click “Submit”, the Aliyun Cloud platform entry has been saved.

# Add IP Pool


Administrator can configure the IP pool in SmartCMP, manage the IP address segment, and view the IP address usage in the IP pool to occupy and release the occupied IP address.

1.  Users can add IP pools as needed, select "Infrastructure" - "IPAM", click "Add", select IP pool (also supports F5 BIG-IP, ACI IP pool), enter the Create IP Pool page. 

2.  On the Overview page: enter a name, description (optional), CIDR, gateway, etc.

3.  Click the “IP Range” menu, click “Add” under the IP range: Enter the name, start IP and end IP on the Create IP Range page, click “Submit”, and the IP range is created successfully. At the bottom of the list, you can see the status of the IP address in the IP range (available, occupied, reserved, cooled), which can be released and occupied. 

4.  Click “Save” and the IP pool is created successfully.

>「Note」The start IP should be greater than the CIDR range, and the end IP should be greater than the start IP.

# Define Resource bundles


SmartCMP can map resources in a cloud platform to multiple logical units by defining resource bundles, and configure them to different organizational structures, thereby designating different organizations and users to use the infrastructure resources in the cloud platform, including computing, storage and network resources, etc. A cloud platform can define a resource bundle or multiple resource bundles.

Define the relationship between the resource bundle and the service group. There are three types of resource sharing:

1.  The resource bundle is only assigned to a unique service group. Operation method: Do not select "Allow sharing to multiple business groups", click "Business Group" to select the business group. 

2.  The resource bundle is assigned to all service groups, and the newly added service group is automatically associated with the resource bundle. To do this, select “Allow sharing to multiple service groups” and click “Business Group” to select all service groups 

3.  Resource bundles are shared to multiple service groups. Operation method: Select “Allow sharing to multiple service groups”. Click “Business Group” to selects multiple service groups.

The steps to create a resource bundle are as follows:

>「Note」Please use the tenant administrator or infrastructure administrator to log in to the SmartCMP platform.

## Adding vSphere Resource 

1.  Go to “Infrastructure” - “Resource bundles, click “Add”, select vSphere, fill in the following information:

2.  Basic Information page:

  + •	Basic information: name, resource tag (optional), priority (the smaller the value, the higher the priority),

  + •	Cloud platform resource information: Select cloud platform portal (select the newly created vSphere cloud platform), resource portal, folder (optional)

3.  ③	After the “Basic Information” page loads successfully, click “Compute Resource”:

  + Resource entry information: view only

  + Physical host information: view only

  + Compute resources: number of vCPUs (upper limit), memory (upper limit), number of virtual machines (upper limit), number of snapshots allowed per virtual machine (upper limit) 

  + Storage: Select storage and its reserved space

4.  Network Resources:

  + Network resources: Select a network, select the IP pool in IP allocation method, and select the newly created IP pool under the “IPAM”.

  + Distributed Virtual Switch: Default

5.  Click Save. After saving, the newly created vSphere resource bundle appears in the resource bundle list.

## Add OpenStack Resource bundle

1.  Go to “Infrastructure” - “Resource bundles”, click “Add”, select OpenStack, fill in the following information

2.  Basic Information page:

  + Basic information: name, business group, whether to share to multiple business groups, resource label (optional), priority

  + Cloud platform resource information: Select cloud platform portal (select the newly created OpenStack cloud platform), Availability zone (appears after selecting cloud platform), DNS domain (optional)

>「Note」Domain name consists of a multi-level domain name such as root domain name, top-level domain, second-level, third-level, etc. Each domain name consists of letters, numbers, and hyphens (-) (the first character cannot be a hyphen), regardless of capitalization and no more than 63 characters in length. A full domain name has a total length of no more than 255 characters and must end with a dot. Configure the DNS domain in the tenant before configuring the resource bundle DNS domain. 


3.  After the “Basic Information” is successfully loaded, click “Compute Resource”:

  + Resource information: view only

  + Computing resources: number of vCPUs (upper limit), memory (upper limit), storage (upper limit), number of virtual machines (upper limit), number of floating IPs (upper limit)

4.  Network Resources

  + Network Resources: Select the network and the corresponding subnet, select the IP pool in IP allocation mode and select the newly created IP pool

  + Security Policy Group: Select one or more security policy groups

  + Firewall: Select one or more firewalls

5.  Routing: optional

6.  Click Save. After saving, the OpenStack resource bundle appears in the resource bundle list 

## Add Aliyun Cloud Resource bundle

You can add a cloud resource bundle according to the following steps: 

1.  Go to “Infrastructure” - “Resource bundles”, click “Add”, select Aliyun, fill in the following information:

2.  Basic Information page:

  + Basic information: Name, whether to share to multiple business groups, resource tags (optional), priority (the smaller the value, the higher the priority)

  + Cloud platform resource information: Select cloud platform portal (Aliyun), region and available zone (the corresponding available zone appears after selecting the zone, you can select more than one), network type (classic network/private network)

3.  After the “Basic Information” is successfully loaded, click “Compute Resource”: vCPU quantity (upper limit), memory (upper limit), number of virtual machines (upper limit)

4.  Payment method: choose prepaid or postpaid

Prepaid: Prepaid means you need to pay first to use the resource. According to the billing cycle, prepaid can be divided into:

  + Pay weekly: billing cycle is one week

  + Annual/ monthly subscription: the billing period is month or year

 After choosing prepaid, please choose the length of the purchase, as short as one week and as long as 5 years. You can check the automatic renewal fee. The automatic renewal fee is one week for weekly purchase, one month for monthly purchase and one year for annual purchase.

Postpaid: Postpaid is the way you pay after using resource. In this way, you can access resources on demand and open and release resources at any time without having to purchase large amounts of resources in advance.

5.   Network Resources

Security Policy Group: Select one or more security policy groups

Virtual Switch: If you choose a private network, you can choose a virtual switch.

6.   Click “Save” and the Aliyun resource bundle is created successfully.

# Define Business Group


A business group is a logical organization structure within a tenant. SmartCMP supports the creation of a multi-level business group for the organization structure of the enterprise within the system. The business group associates the user to which the business group belongs and the resource bundles that the business group can use.

A business group is a logical concept. Entities that need to associate users, service catalogs, and resource quotas can be associated with business groups, such as subsidiaries, departments at different levels, and so on. 

Default business group and tenant administrator, business group administrator, and business group members are created by default. Resource bundles can be assigned by the following steps:

>「Note」If you need to modify the settings of this business group or create a new business group, please refer to the detailed steps in [Organization](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/)

1.  Click “Organization” - “Business Groups” and click the business group name (Default) to enter the editing page

2.  Overview page, keep the default value

3.  User page: keep the default value. By default, two users are set up as business group administrators and business group member.

4.  Resource Bundles: click Add, select the vSphere resource bundle and OpenStack resource bundle created in the previous section, and click OK.

5.  Click Save to associate the business group with the resource bundle.

6.  Apply for resource and service association approval process for the business group, set naming rules and request specification. 

7.  Configure cloud resource operations entitlement and service deployment operations entitlement for business group members 

8.  Configure resources and budget quotas for business group members

# Define Virtual Machine Template


The platform supports the creation of virtual machine templates. One operating system can correspond to multiple virtual machine templates, and one virtual machine template can be used in multiple cloud platforms. The virtual machine template is associated with a template in the vSphere platform or an image in the OpenStack platform. 

The installation mode and account information of the two SmartCMP agents can be configured in the VM template. The two agents are monitoring agents and automation agents. Some automation features in the SmartCMP platform rely on automated agents. 

For example: blueprint with application deployment or disk addition, service configuration initialization with disk mounted and new users created and some virtual machine operations (including reset password, execute script, application start & stop, add and extend Linux logical volume or Windows Disk, etc.). 

Once a virtual machine template is created, it can be specified directly in the service configuration. SmartCMP automatically recognizes virtual machine templates based on the cloud platform on which the blueprint objects are located.

Here defines two virtual machine templates: CentOS 7 and Windows 2012 R2.

>「Note」Please use the tenant administrator or infrastructure administrator to log in to SmartCMP. Tenant administrators can assign an infrastructure administrator role to a user. By default, three virtual machine templates are created: Windows 2012 R2, Redhat 7, and CentOS 7. You need to add the corresponding cloud platform information to use.

Add a Linux VM Template

## Add a Linux VM Template

1.  Select Infrastructure - VM Templates to enter the VM template list interface. This page has 2 Linux virtual machine templates by default, Redhat 7 and CentOS 7 respectively.

2.  Click “CentOS 7” to enter the “Basic Information” page of the VM template, which displays the operating system name, description, and system type (Linux or Windows). 

3.  Click the VM Template tab to enter the VM template list interface.

## Add vSphere VM Template {#Add vSphere VM Template .afff6}

1.  Click Add. Enter the template name: Linux CentOS 7 on vSphere. Select the vSphere cloud platform configured in Section 2.2.1 and configure it as follows:

+ Clone mode: select "Full clone" or "Linked clone"

>「Note」Full clone is a completely independent copy of the original virtual machine. It does not share any resources with the original virtual machine and can be used independently from the original virtual machine. Linked clones need to share the same virtual disk file with the original virtual machine, can not be separated from the original virtual machine. But using shared disk files greatly reduces the time it takes to create a cloned virtual machine, while also saving valuable physical disk space.

 + Full clone：
•	Template: Select a Linux CentOS 7 template  

 + Linked clone

•	Virtual Machine: Select a template for Linux CentOS 7. Snapshot mode: “Specify a snapshot” by default. You can select the “select when applying” or “always use the latest” snapshot mode. Select “Select when applying” to select the virtual machine snapshot at the time of service request. Snapshot: If the snapshot mode selects “Specify a Snapshot”, a snapshot will be selected.	Specification: Select “Built-in” (Select None, Built-in, or Custom Specification on demand. The specification helps prevent conflicts when deploying virtual machines with the same settings). SSH is enabled in the template: Check this option to enable SSH in the template. You can choose to install the monitoring agent and the automation agent through SSH. The default SSH port is 22. If the SSH port is modified in the template, Enter the modified SSH port number in the template. Username and password: If you choose to enable SSH, fill in the user with SSH permission and its password 

+ Monitoring method:

<!-- -->

  + No monitoring: The monitoring function of the platform is not available if the monitoring agent is not installed

  + SSH monitoring agent: If you choose to install SSH, you will access the virtual machine through SSH and install the monitoring agent. Set the monitoring port. The default is 9100

  + Pre-installation monitoring agent: Pre-installation means that the monitoring agent is already installed in the template

  + Cloud platform monitoring: directly read the monitoring data of the virtual machine from the vCenter, no need to install the monitoring agent

+ Install the automation agent:



  + Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or disks adding, some virtual machine operations such as resetting passwords, executing scripts, etc.

  + SSH installation: Select SSH installation, access virtual machine via SSH and install automation agent

  + Pre-installation: Pre-installation means that an automation agent is already installed in the template.


+ Admin user: Enter the administrator username configured in the template

+ Administrator password: Enter the administrator password configured in the template

2.  Click Submit, it shows that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated. 

## Add OpenStack VM Template {#Add OpenStack VM Template .afff6}

Click Add, enter the virtual machine template name Linux CentOS 7 on OpenStack, select the OpenStack cloud platform configured in Section 2.2.2 and do the following configuration:

  + Startup source type: boot from image, launch from snapshot, boot from cloud drive, boot from cloud drive snapshot 
  + Boot from image: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select " Select when applying", you will specify a virtual machine snapshot at the time of service request. 
  + Launch from Snapshot: Select Snapshot Name
  + Boot from the cloud drive: Select the image name and snapshot mode. The snapshot mode defaults to “Do not use snapshots”, you may select “Select when applying” and “Always use the latest”. If you select "Select when applying", the virtual machine snapshot will be specified when the service is applied; if "Delete after termination" is checked, the hard disk will be deleted after the host is terminated. Selecting "Boot from Cloud Drive" mode requires volume type and configuration volume size to be selected during service configuration 
  + Boot from the cloud disk snapshot: Select the cloud disk snapshot name. If you select “Delete after termination”, the hard disk will be deleted after the host is terminated. Selecting "Start from Cloud Drive Snapshot" mode requires volume type and configuration volume size to be selected during service configuration 
  + How to monitor and automate agents: Same as the Linux template for vSphere, you can configure the SSH port. In addition, the SSH user supports the key mode (you can create a new key or import a key in the Infrastructure - Key Pairs). 
  + Administrator username and password: Enter the operating system administrator username and password

	Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated. At this time, the Linux operating system of CentOS 7 is associated with two virtual machine templates. When configuring service, the platform automatically selects the VM template corresponding to the service without repeating the settings.


## Add Windows VM Template

1.  Select Infrastructure - VM Template to enter the VM template list interface. This page has 1 Windows virtual machine template by default, Windows 2012 R2
    
2.  Click “Windows 2012 R2” to enter the “Basic Information” page of the VM template

3.  This page displays the operating system name, description, and system type

4.  Click the VM Template tab to enter the VM template list interface

## Add vSphere VM Template {#Add vSphere VM Template-1 .afff6}

1. Click Add. Enter the template name: Windows 2012 R2 on vSphere. Select the vSphere cloud platform configured in Section 2.2.1 and configure it as follows:

+ Clone mode: select "Full clone" or "Linked clone"

>「Note」Full clone is a completely independent copy of the original virtual machine. It does not share any resources with the original virtual machine and can be used independently from the original virtual machine. Linked clones need to share the same virtual disk file with the original virtual machine, can not be separated from the original virtual machine. But using shared disk files greatly reduces the time it takes to create a cloned virtual machine, while also saving valuable physical disk space.

  + Full clone：Template: Select a Windows 2012 R2 template


<!-- -->

  + Linked clone
  •	Virtual Machine: Select a template for Windows 2012 R2. 	Specification: Select “Built-in” (Select None, Built-in, or Custom Specification on demand. The specification helps prevent conflicts when deploying virtual machines with the same settings). 	WINRM is enabled in the template: Check this option to enable WINRM in the template. You can choose to install the monitoring agent and the automation agent through WINRM. The default WINRM port is 22. If the WINRM port is modified in the template, Enter the modified WINRM port number in the template. 

+ Monitoring method:


  + No monitoring: The monitoring function of the platform is not available if the monitoring agent is not installed

  + WINRM monitoring agent: If you choose to install WINRM, you will access the virtual machine through WINRM and install the monitoring agent. Set the monitoring port. The default is 9182.

  + Pre-installation monitoring agent: Pre-installation means that the monitoring agent is already installed in the template.

  + Cloud platform monitoring: directly read the monitoring data of the virtual machine from the vCenter, no need to install the monitoring agent



+ Install the automation agent:


  + Do not install: If you do not install an automated agent, some of the platform's automation features will not be available, such as blueprints with application deployment or disks adding, some virtual machine operations such as resetting passwords, executing scripts, etc.

  + WINRM installation: Select WINRM installation, access virtual machine via WINRM and install automation agent

  + Pre-installation: Pre-installation means that an automation agent is already installed in the template.



+ Admin user: Enter the administrator username configured in the template

+ Administrator password: Enter the administrator password configured in the template

2.  Click Submit, it shows that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated. 

## Add OpenStack VM Template {#Add OpenStack VM Template-1 .afff6}

1.  Click Add, enter the virtual machine template name Windows 2012 R2 on OpenStack, select the OpenStack cloud platform configured in Section 2.3.2 and do the following configuration:

  +  Startup source type: boot from image, launch from snapshot, boot from cloud drive or boot from cloud drive snapshot 



  1. Boot from image: Select image name (select Windows 2012 image) and snapshot mode (do not use snapshot, select when applying, always use the latest)
    

  2. Launch from Snapshot: Select Snapshot Name (Select Snapshot for Windows 2012)

  3. Boot from the cloud drive: Select the image name (select the Windows 2012 image) and snapshot mode (do not use snapshots, select when applying, always use the latest)
   

  4. Boot from a cloud drive snapshot: Select the cloud drive snapshot name (select a snapshot of Windows 2012)


  + Install monitoring and automation agents in the same way as vSphere's Windows templates


  + Windows username: Enter the Windows administrator username you need to set.Windows用户名: 输入需要设置的Windows管理员用户名


  + Authentication type: key pair or password, select password

 +  Windows password: set the password corresponding to the username

2.  Click Submit to prompt that the virtual machine template has been created. Click "Save" to indicate that the VM template has been updated



# Define Blueprint


Software architects can visually design virtual machines or application blueprints through a blueprint management interface. The blueprint is an abstraction of the application, including the topology of the application, the workflow and the strategy.

With drag-and-drop visualization of blueprint modeling, software architects can model complex multi-node applications efficiently.

Users can apply for services through the service catalog on their basis, complete one-click application, and deploy multiple times quickly.


The system has built-in blueprints by default, including vSphere Linux, vSphere Windows, etc., which can be used directly. Go to the next section for service configuration and release. 


>「Note」To create a new blueprint, please refer to the detailed steps in [Service Design](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/)

# Configure and Publish Services


Services can be created, configured, and published in the service configuration interface of SmartCMP. Here the default vSphere Linux blueprint (1 Server+1 Network) is associated with the underlying resource bundle, and the necessary parameters required for deployment such as templates are configured.


>「Note」Please use the business group administrator or infrastructure administrator role to log in to the SmartCMP platform.

## Add vSphere Linux Single-Node Service

1.  Select Service Design - Catalog Config., click Add: enter the service name and service description (optional), select the default Linux blueprint, select the Default business group or all business groups and click "Submit" 


2.  After the service configuration succeeds, go to edit page. Keep default in “Profile” page (can be modified according to requirements).

>「Note」When configuring the service, many options can be checked "Allow modification" and "Modify only when approval". There are two cases here: if you select "Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase and if you select both "Allow modification" and "Modify only when approval", the user can not modify the parameters in the service request, the parameters are only allowed to be modified during the service approval stage.

3.  Go to the “Components” and select “Server” to enter the server node detailed settings page.

 Basic Information: Keep the default value (you can modify the number of instances as needed)


 + Computing resources

 OS Hostname: Inherit the business group naming rules (Do not check "Allow modification" and "Modify only when approval")
 

 Virtual Machine name： Inherit the business group naming rules (Do not check "Allow modification" and "Modify only when approval")


 Note: Optional (Do not check "Allow modification" and "Modify only when approval")

 + Resource Bundles 

 Resource bundle selection strategy: default automatic selection

 + Templates

 Select the vSphere virtual machine template configured in the previous section (Centos 7 - Linux CentOS 7 on vSphere)

 + Computing Specification

 Mode: custom

 Number of vCPUs: 2 (Do not check "Allow modification" and "Modify only when approval")

 Memory (GB): 8 (Do not check "Allow modification" and "Modify only when approval")

 + System disk

 Provisioning mode: optional when fully cloned in a virtual machine template

 Folder: Select a folder, virtual machine deployment in the selected vCenter folder (configured in the resource pool)

 Virtual machine storage policy: default, (Do not check "Allow modification" and "Modify only when approval")
 Storage: Virtual machines are deployed in the selected storage. If not selected, it is deployed in the storage defined by the resource bundle.

 Allow users to select provisioning mode and storage when adding new disks: unchecked

 + Network

 Configure the IP allocation mode. Click "IP Allocation Method" and select "IP Pool". (Optional range is provided according to the "Network Resource" configuration in the resource pool. If only the IP pool allocation mode is configured in the resource pool, the service configuration use and only use the default method for IP pool)

  User: keep the default

  Disk: keep the default

  Relationship: keep the default

  Operation Entitlement: Keep the default

  Click Save to return to the component configuration page. Select "Network" to edit

  Go to the Network Properties page and select the desired network tag (select it according to the network tag configured in Network Resources), check Manage Network, click Save, and return to the component configuration page. 

  Click "Save and Publish" and the new service becomes released.

>「Note」After the successful publish, use the business group member role to log in to the SmartCMP platform and apply for a virtual machine in the Service Catalog.

## Add OpenStack Linux Single-Node Service

1.  Select Service Design - Catalog Config., click Add: enter the service name and service description (optional), select the default OpenStack Linux blueprint, select the Default business group or all business groups and click "Submit"


2.  After the service configuration succeeds, go to edit page. Keep default in “Profile” page (can be modified according to requirements).

>「Note」When configuring the service, many options can be checked "Allow modification" and "Modify only when approval". There are two cases here: if you select "Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase and if you select both "Allow modification" and "Modify only when approval", the user can not modify the parameters in the service request, the parameters are only allowed to be modified during the service approval stage.

3.  Go to the “Components” and select “Server” to enter the server node detailed settings page.

 + Basic Information:

Keep the default value (you can modify the number of instances as needed)

 + Cloud Resource Configuration

<!-- -->

 + Basic information

 OS Hostname: Inherit the business group naming rules (Do not check "Allow modification" and "Modify only when approval")
 

 Virtual Machine name： Inherit the business group naming rules (Do not check "Allow modification" and "Modify only when approval")


 Host collection: Do not select


 + Resource Bundles

 Resource bundle selection strategy: default automatic selection

 + VM Template

 Select the virtual machine template configured in the previous section Linux CentOS 7 on OpenStack

 + Network

 DNS is not configured by default

 Disk: Keep the default

 Security Policy Group: Keep the default

 Relationship: Keep the default

 Operation Entitlement: Keep the default

4.  Click Save to return to the component configuration page. Select "Network" to edit

5.  Go to the Network Properties page and select the desired network and subnet. Uncheck "Allow Changes" and "Modify Only when Approval". The IP allocation method is determined by the configuration of the selected network and subnet in the resource bundle. Uncheck "Manage Network", click "Save" to return to the component configuration page. 

6.  Click "Save and Publish" and the new service becomes released.

# Request Service


After the service is successfully published, you can view and apply for the published service in service catalog.

1.  Click Service Catalog, select the vSphere single-node service or OpenStack single-node service configured in the previous section, and click to enter the service request interface.

2.  View the details of the service on this page, such as: organization information, deployment information, application parameters, etc.

3.  Fill in/modify relevant information, if not enter the next step directly

4.  Click Apply and the request is successful after approved by the process control (approval template) of the business group. Since Default business group has no approval process, service will be deployed directly after request.

# Self-service Operation


After the service is requested, you can check the status of the deployment in Deployment - My Deployment.

 + If there is an approval process, you can go to “Requests” - “Pending Approval” to view the current approval process.

 + If there is no approval process, click on the service deployment name to go to the deployment details page to view basic information, topology and operation history.



 + The current deployment process can be viewed in the operation history. Go to "Deployment" - "My Deployment" - "Operation History", select the action to view the current deployment process below.

 + On the basic information page: View service name, blueprint, deployment time, expiration time, retention time, business group, project, owner, etc.

 + Operations for service deployment are available at the top of the page.

## View Deployment Details and Self-Service Operation

After the service is successfully deployed, you can view the detailed information about the service deployment and the monitoring information of the instances and application components on the My Deployment page. A service deployment consists of one or more instances.

1.  After selecting “Deployment” - “My Deployment”, you will see the service deployment list, which can be filtered by business group, stage (running, operation processing, shutdown, failed), state  (normal, abnormal), owner or project in advanced search, or directly search operation. 

2.  In the service deployment list, you can select one or more service deployments to quickly perform some operations, including stop, installation SW, copy, extended expiration time, tear down, delete management information, change owner, change project, change business group and update Exts (example is vSphere service deployment and operation of different cloud platforms are different)

 >「Note」Users can see the list of allowed operations after the deployment is generated only if the operating entitlement of the virtual machine is configured when the business group is set or the service is configured. Default business group defaults all operations to the business group administrator and there is no approval process.

3.  Click on the name to view the details of the service deployment including "Basic Information", " Topology", "Operation History" and "Monitoring" (Monitoring of VMs and Application Components)

  + Basic Information: Includes name, business group, project, blueprint, resource bundle, cloud platform, and related information such as cost, status, and time. It also includes a list of input parameters for the service deployment and output result information. After the service deployment fails, some scenarios can be repaired offline. If the repair is successful, the service deployment status will be changed to "Running".

  + Topology: Includes blueprints, details, and process information for service deployment. Hovering over the service topology map will display the key information of the node. For example, the server node will display the instance name, guest operating system, IP address, memory, total disk space, number of vCPUs, CPU usage, memory usage, etc.

  + History: Shows the operation history of the service deployment

  + Monitoring: Shows monitoring information for instances and application components in the deployment.

## View Deployment Details and Self-Service Operation

At the same time, instance status and details can be managed and operated in "Instances ". The enabling and approval of the operation needs to be set at the business group level or service configuration level.

1.  Select “Deployments” - “Instances”, you will see a list of instances. In “Advanced Search”, you can filter by business group, state (started, lost, stopped), owner, project and tag. Click on "Show Columns" to select or not select certain columns for display. 

2.  In this list, you can select one or more instances to quickly perform some operations, including "Start", "Reboot", "Suspend", "Stop", "Run Script", "Set Tag", "Enable/Switch Monitoring". "Update Monitoring Agent", "Update Automation Agent", etc. 

3.  You can also click on an instance to enter its details interface for management and operation, including “Basic Information”, “History”, “Snapshot”, “Monitoring”, “Application List” tab and the top operation list.

>「Note」Monitoring and tags may only be viewed if this instance is installed monitoring and applications and deployed successfully.

4.  Basic Information:

 + Basic information about the virtual machine and its associated hosts, such as: name, operating system, installed software, vCPU, memory, status, SSH port, automation agent, monitoring mode, monitoring port, lease/retention expiration time, etc. 

 + Relationships: server information, resource bundles, data storage, virtual machine storage policies, network labels, etc.

 + Physical host information

 + Users and groups

 + Organizational information: service deployment name, service name, business group, tenant, project, etc.

 + Operating status

 + IP address

 + Key-value labels

>「Note」More host related information will be determined according to different cloud platforms and different service configuration items

5.  History includes the operation history of the virtual machine

6.  Snapshot displays the current snapshot information (snapshot name, creation time, etc.), and “refresh”, “add”, “restore” and “delete” the snapshot

7.  Monitoring includes monitoring data of the virtual machine CPU, memory, disk, and network (you can adjust the time span or average time to view historical monitoring data as needed)

>「Note」Only after the instance configured with monitoring in VM templates is deployed successfully can data be seen in monitoring. 

8.  Application List displays the list of applications that are currently installed on the virtual machine (if the virtual machine does not have an application installed, the application list menu is not displayed)

9.  Operation includes a list of operations that can be performed by the virtual machine. The specific operation introduction will be expanded later.

>「Note」Users can see the list of allowed operations after the deployment is generated only if the operating entitlement of the virtual machine is configured when the business group is set or the service is configured. Default business group defaults all operations to the business group administrator and there is no approval process.

## View Cloud Resource Details

In Resources, you can view and manage related cloud resource status and detail.

Select "Deployments" - " Resources", you will see the following categories: storage, container, network, PaaS and software.

 + Storage: Cloud Drive, Object Storage
 
 + Container: Deployment, Daemonset, StatefulSet, Container, Service, Ingress, PVC, ConfigMap and Secret.

 + Network: Load Balancer, LB Listener, LB Pool, LB SNAT Pool, Floating IP, Firewall, Security Group and DNS

 + PaaS: Relational Databases, Web App

 + Software: Software


# Ticket Service


SmartCMP supports tenant and system administrators to define and publish standard ticket services and supports user self-service request and tracking. This chapter will show you how to create your first ticket, publish and apply for a service.

Tenant administrators can customize and publish standard ticket services, and users can apply for self-service through the service catalog and track ticket processing status through service requests.

## Define Service Group

Service group is a collection of service personnel who process ticket tasks during the ticket service management process. Support the tenant administrator to customize the associated users.

Brief steps to create a service team:

1.  Click on “Organization” - “Service Group”, click on the service group name to enter the edit page.

2.  Basic Information page: fill in name and description

3.  User page: associate or unlink users

4.  Click “Save”, the service group is created and successfully associated with the users.

>「Note」To modify the settings of the service group or create a new service group, please refer to the detailed steps in [Organization](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/)

## Configure and Publish Service

Brief steps to configure the service:

1.  Select "Service Design" - "Catalog Config" and click "Add"

2.  Fill in the service name, service description (optional), select the business group, and when the service type is manual ticket service, add a service process and click “Submit” to enter the service configuration “Overview” page 

3.  Fill in the following information on the “Basic Information” tab: Name, Description, Logo Image, Service Group and Order as well as specifying the handler to process the ticket task, configuring the role type of the handler and the specific handler. 

4.  Click the Save button, the service will be saved without publishing, click the Save and Publish button, and the service will be published to the Service Catalog page.

>「Note」Please use the tenant administrator role to log in to the SmartCMP platform. To modify the configuration and release settings, or to create a new configuration and release, refer to the detailed steps in [Manual Ticket Service Configuration](https://cloudchef.github.io/doc-en/AdminDoc/08RequestServiceMgmt/). To modify the configuration of a service process or create a new service process configuration, please refer to [Service Process Mgmt.](https://cloudchef.github.io/doc-en/AdminDoc/08RequestServiceMgmt/).

## Process and Track Request

Brief steps for processing and tracking requests：

1.  Click " Requests" - "Pending Requests", which displays the basic information of the ongoing request: request number, request type, title, business group, project, request status, request time, completion time.

2.  Select a pending service request, click the “Request Number” link, and jump to the request details page to view the basic information of the request, ticket information, processing records, process steps, service processing information, and so on. 

3.  Processing methods are defined as two types, direct processing and transfer processing. Select the direct processing method, click on the direct processing, fill in the processing result description then click submit.

4.  Click on “Requests” - “All Requests” to view the details of all service requests.

>「Note」For detailed requests processing and tracking please refer to: [Requests processing and tracking](https://cloudchef.github.io/doc-en/AdminDoc/08RequestServiceMgmt/)




# Quick Configuration of Cloud Resource Blueprint Services {#QuickConfigurationofCloudResourceBlueprintServices}


This section links the required steps and processes to configure the following services to help you quickly locate content.

[vSphere Single-node VM Service](#vSphereSingle-nodeVMService)

[VMware NSX Service](#VMwareNSXService)

[vSphere MySQL Service with Monitoring](#vSphereMySQLServicewithMonitoring)

[OpenStack Singel-node Service](#OpenStackSingel-nodeService)

[OpenStack Firewall Service](#OpenStackFirewallService)

[OpenStack LoadBalancer with SecurityGroup Service](#OpenStackLoadBalancerwithSecurityGroupService)

[OpenStack FloatingIP Service](#OpenStackFloatingIPService)

[Kubernetes Service](#KubernetesService)

[Aliyun Service](#AliyunService)

[Azure Service](#AzureService)

[AWS Service](#AWSService)

[QingCloud Service](#QingCloudService)

[Hyper-V Service](#Hyper-VService)

## vSphere Single-node VM Service{#vSphereSingle-nodeVMService}

i.	  Add vSphere cloud platform: refer to [Add vSphere Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20vSphere%20Cloud%20Platform)

ii.	  Add vSphere resource bundles: refer to [Add a vSphere Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20a%20vSphere%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add a vSphere VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20a%20vSphere%20VM%20Template)

v.	Define Computing Specifications: refer to [Add vSphere Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20vSphere%20Computing%20Specifications)

vi.	Create vSphere Single-node Blueprint: refer to [Build vSphere Single-node Blueprints](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Build%20vSphere%20Single-node%20Blueprints)

vii.	Configure vSphere Single-node Service: refer to [Configure vSphere Single-Node Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20vSphere%20Single-Node%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Service: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operations: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## VMware NSX Service{#VMwareNSXService}

i.	Add VMware NSX Platform: refer to [Add VMware NSX Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20VMware%20NSX%20Cloud%20Platform)

ii.	Add vSphere Cloud Platform: refer to [Add vSphere Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20vSphere%20Cloud%20Platform)

iii.	Add vSphere with NSX resource bundle: refer to [Add a vSphere with NSX Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20a%20vSphere%20with%20NSX%20Resource%20Bundle)

iv.	Configure VM Template: refer to [Add a vSphere VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20a%20vSphere%20VM%20Template)

v.	Define Computing Specifications: refer to [Add vSphere Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20vSphere%20Computing%20Specifications)

vi.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

vii.	Create VMware NSX Blueprint: refer to [Create VMware NSX Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20VMware%20NSX%20Blueprint)

viii.	Configure VMware NSX Service: refer to [Configure VMware NSX Services](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20VMware%20NSX%20Services)

ix.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

x.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

xi.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## vSphere MySQL Service with Monitoring{#vSphereMySQLServicewithMonitoring}

i.	Add vSphere Cloud Platform: refer to [Add vSphere Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20vSphere%20Cloud%20Platform)

ii.	Add vSphere resource bundle: refer to [Add a vSphere Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20a%20vSphere%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add a vSphere VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20a%20vSphere%20VM%20Template)

v.	Define Computing Specifications: refer to [Add vSphere Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20vSphere%20Computing%20Specifications)

vi.	Create vSphere MySQL with Monitoring Blueprint: refer to [Create vSphere MySQL with Monitoring Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20vSphere%20MySQL%20with%20Monitoring%20Blueprint)

vii.	Configure vSphereMySQL with Monitoring Service: refer to [Configure vSphere MySQL with Monitoring Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20vSphere%20MySQL%20with%20Monitoring%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## OpenStack Singel-node Service{#OpenStackSingel-nodeService}

i.	Add OpenStack Cloud Platform: refer to [Add OpenStack Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20OpenStack%20Cloud%20Platform)

ii.	Add OpenStack resource bundle: refer to [Add OpenStack Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20OpenStack%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add OpenStack VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20OpenStack%20VM%20Template)

v.	Define Computing Specifications: refer to [Add OpenStack Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20OpenStack%20Computing%20Specifications)

vi.	Create OpenStack Single-node Blueprint: refer to [Create OpenStack Single-node Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20Single-node%20Blueprint)

vii.	Configure OpenStack Single-node Service: refer to [Configure OpenStack Single-Node Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20OpenStack%20Single-Node%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## OpenStack Firewall Service{#OpenStackFirewallService}

i.	Add OpenStack Cloud Platform: refer to [Add OpenStack Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20OpenStack%20Cloud%20Platform)

ii.	Add OpenStack resource bundle: refer to [Add OpenStack Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20OpenStack%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)


xi.	Configure VM Template: refer to [Add OpenStack VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20OpenStack%20VM%20Template)

xii.	Define Computing Specifications: refer to [Add OpenStack Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20OpenStack%20Computing%20Specifications)

iv.	Create OpenStack Firewall Blueprint: refer to [Create OpenStack Firewall Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20Firewall%20Blueprint)

v.	Configure OpenStack Firewall Service: refer to [Configure OpenStack Firewall Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20OpenStack%20Firewall%20Service)

vi.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

vii.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 



## OpenStack LoadBalancer with SecurityGroup Service{#OpenStackLoadBalancerwithSecurityGroupService}

i.	Add OpenStack Cloud Platform: refer to [Add OpenStack Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20OpenStack%20Cloud%20Platform)

ii.	Add OpenStack resource bundle: refer to [Add OpenStack Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20OpenStack%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add OpenStack VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20OpenStack%20VM%20Template)

v.	Define Computing Specifications: [Add OpenStack Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20OpenStack%20Computing%20Specifications)

vi.	Create OpenStack LoadBalancer with Security Group Blueprint: refer to [Create OpenStack LoadBalancer with SecurityGroup Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20LoadBalancer%20with%20SecurityGroup%20Blueprint)

vii.	Configure OpenStack LoadBalancer with Security Group Service: refer to [Configure OpenStack LoadBalancer with SecurityGroup Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20OpenStack%20LoadBalancer%20with%20SecurityGroup%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 



## OpenStack FloatingIP Service{#OpenStackFloatingIPService}

i.	Add OpenStack Cloud Platform: refer to [Add OpenStack Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20OpenStack%20Cloud%20Platform)

ii.	Add OpenStack resource bundle: refer to [Add OpenStack Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20OpenStack%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add OpenStack VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20OpenStack%20VM%20Template)

v.	Define Computing Specifications: refer to [Add OpenStack Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20OpenStack%20Computing%20Specifications)

vi.	Create OpenStack Floating IP Blueprint: refer to [Create OpenStack FloatingIP Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20FloatingIP%20Blueprint)

vii.	Configure OpenStack Firewall Service: refer to [Configure OpenStack FloatingIP Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20OpenStack%20FloatingIP%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 



## OpenStackDNS服务{#OpenStackDNS服务}

i.	Add OpenStack Cloud Platform: refer to [Add OpenStack Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20OpenStack%20Cloud%20Platform)

ii.	Add OpenStack resource bundle: refer to [Add OpenStack Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20OpenStack%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add OpenStack VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20OpenStack%20VM%20Template)

v.	Define Computing Specifications: refer to [Add OpenStack Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20OpenStack%20Computing%20Specifications)

vi.	Create OpenStack DNS Blueprint: refer to [Create OpenStack DNS Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20DNS%20Blueprint)

vii.	Configure OpenStack DNS Service: refer to [Configure OpenStack DNS Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20OpenStack%20DNS%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 



## Kubernetes Service{#KubernetesService}

i.	Add Kubernetes Cloud Platform: refer to [Add Kubernetes Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20Kubernetes%20Cloud%20Platform)

ii.	Add Kubernetes resource bundle: refer to [Add Kubernetes Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20Kubernetes%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Create Kubernetes Blueprint: refer to [Create Kubernetes Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20Kubernetes%20Blueprint)

v.	ConfigureKubernetes Service: refer to [Configure Kubernetes Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20Kubernetes%20Service)

vi.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

vii.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 



## Aliyun Service{#AliyunService}

i.	Add Aliyun Cloud Platform: refer to [Add Aliyun Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20Aliyun%20Cloud%20Platform)

ii.	Add Aliyun resource bundle: refer to [Add Aliyun Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20Aliyun%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template (Similar to Azure): refer to [Add an Azure VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20an%20Azure%20VM%20Template)

v.	Define Computing Specifications (Similar to Azure): refer to [Add Azure Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20Azure%20Computing%20Specifications)

vi.	Create Aliyun Blueprint: refer to [Create Aliyun Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20Aliyun%20Blueprint)

vii.	Configure Aliyun Service: refer to [Configure Aliyun Cloud Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20Alibaba%20Cloud%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## Azure Service{#AzureService}

i.	Add Azure Cloud Platform: refer to [Add Azure Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20Azure%20Cloud%20Platform)

ii.	Add Azure resource bundle: refer to [Add Azure Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20Azure%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add an Azure VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20an%20Azure%20VM%20Template)

v.	Define Computing Specifications: refer to [Add Azure Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20Azure%20Computing%20Specifications)

vi.	Create Azure Blueprint: refer to [Create Azure Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20Azure%20Blueprint)

vii.	Configure Azure Service: refer to [Configure Azure Services](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20Azure%20Services)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 



## AWS Service{#AWSService}

i.	Add AWS Cloud Platform: refer to [Add AWS Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20AWS%20Cloud%20Platform)

ii.	Add AWSresource bundle: refer to [Add AWS Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20AWS%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)


iv.	Configure VM Template (Similar to Azure): refer to [Add an Azure VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20an%20Azure%20VM%20Template)

v.	Define Computing Specifications (Similar to Azure): refer to [Add Azure Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20Azure%20Computing%20Specifications)


vi.	Create AWS Blueprint: refer to [Create AWS Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20AWS%20Blueprint)

vii.	ConfigureAWS Service: refer to [Configure AWS Services](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20AWS%20Services)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## QingCloud Service{#QingCloudService}

i.	Add QingCloud Cloud Platform: refer to [Add QingCloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20QingCloud%20Platform)

ii.	Add QingCloudresource bundle: refer to [Add QingCloud Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20QingCloud%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template (Similar to Azure): refer to [Add an Azure VM Template](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20an%20Azure%20VM%20Template)

v.	Define Computing Specifications (Similar to Azure): refer to [Add Azure Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20Azure%20Computing%20Specifications)


vi.	Create QingCloud Blueprint: refer to [Create QingCloud Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20QingCloud%20Blueprint)

vii.	Configure QingCloude Service: refer to [Configure QingCloud Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20QingCloud%20Service)

viiii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 


## Hyper-V Service{#Hyper-VService}

i.	Add Hyper-V Cloud Platform: refer to [Add Hyper-V Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20Hyper-V%20Cloud%20Platform)

ii.	Add Hyper-Vresource bundle: refer to [Add Microsoft Hyper-V Resource Bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20Microsoft%20Hyper-V%20Resource%20Bundle)

iii.	Add relationship between Business Group and resource bundle: refer to [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

iv.	Configure VM Template: refer to [Add a Hyper-V VM Templates](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/VMTemplates.html#Add%20a%20Hyper-V%20VM%20Templates)

v.	Define Computing Specifications (Similar to Azure): refer to [Add vSphere Computing Specifications](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ComputingSpecifications.html#Add%20vSphere%20Computing%20Specifications)

vi.	Create Hyper-V Blueprint: refer to [Create Hyper-V Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20Hyper-V%20Blueprint)

vii.	Configure Hyper-V Service: refer to [Configure Hyper-V Service](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20Hyper-V%20Service)

viii.	Service Request: refer to [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

ix.	Service Deployment Operation: refer to [Service Deployment and Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 

x.	Virtual Machine related Operation: refer to [Instance Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.4%20%20%20%20Instance%20Operation) 

## F5 Service{#F5Service}

Platform supports F5 management and modeling, including: 
1. ①	When creating and designing Blueprint deployment virtual machines and application software, it can cooperate with F5's Virtual Server, Pool and SNAT Pool Network Configure to automatically deploy and deliver services.

2. ②	Support adding F5 load balancing to deployed virtual machines 
3. ③	After the service deployment is complete, the operation modification of the configuration of the Virtual Server and SNAT Pool is supported. 

You may deploy F5 Service using following steps: 

i.  Add F5 BIG-IP Cloud Platform: refer to [Add F5 BIG-IP Cloud Platform](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/CloudPlatformManagement.html#Add%20F5%20BIG-IP%20Cloud%20Platform)

ii.	Add IP POOL: refer to [Add IP POOL](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/IPAM.html#add-an-ip-pool)

iii.	Create F5 BIG-IP resource bundle: refer to [Create F5 BIG-IP resource bundle](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/ResourceBundleManagement.html#Add%20F5%20Big%20IP%20Resource%20Bundle)

iv.	Create relationship between F5 BIG-IP resource bundle and Business Group: refer to [Add F5 BIG-IP resource bundle to BG](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

v.	Create F5 Blueprint: refer to [Create F5 and OpenStack Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20a%20Blueprint%20for%20F5%20and%20OpenStack%20Combinations)

vi.	Configure F5 Service: refer to [Configure F5 and OpenStack Combined Services](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceConfiguration.html#Configure%20F5%20and%20OpenStack%20Combined%20Services)

vii.	F5 Service Deployment Operation: refer to [Service Deployment Operation](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/Deployments.html#7.3.2%20%20%20%20Service%20Deployment%20and%20Operation) 
