
**Service Configuration**

The software architect can publish the designed blueprint as a service, and the IT administrator can integrate the service with the internal processes and publish it to the service catalog. 
The main functions of the service items are:

>「Note」After the service is released, you can apply for the service through the service catalog. For details, see: [Service Catalog](https://cloudchef.github.io/doc-en/AdminDoc/06CloudServiceMgmt/ServiceCatalog.html)

 + Service is associated with a specified blueprint, business group

 + Service and service strategy relationships, such as service hours, leases, service processes, etc.

 + Service access settings

 + Integration of services with third-party systems, such as third-party approval processes, third-party billing processes, etc.

In the navigation bar on the left, choose Service Design – Catalog Config. The service list is displayed. The service name, description, blueprint design, service group, status, number of service deployments, and creation time are displayed. You can perform the following operations on the service configuration: add, edit, unpublish, delete, etc.

# Add a Service Configuration

You can add a service configuration by following the steps below:

1.  In the left navigation bar, select "Service desgin" - “Catalog Config” and click "Add".

2.  Fill in the service name, service description (optional), select the business group, service type. When the service type is cloud resource blueprint service, select the blueprint design. When selecting the manual work order service, select the process selection and click " submit"

 Next, Introduce you to the specific steps of the cloud resource blueprint service configuration. For the specific steps of the manual work order service configuration, please refer to: [Manual Work Order Service Configuration](https://cloudchef.github.io/doc-en/AdminDoc/08RequestServiceMgmt/#Manual%20Work%20Order%20Service%20Configuration)

>「Note」The description of the service configuration supports Markdown syntax writing rules to show the display format of different service descriptions during service request. 

3.  Fill in the following information on the "Overview" tab.


+ Name	Service item name
+ Description	Service item description
+ Logo	Service item logo selection, will be displayed in the service catalog after publishing
+ Business Group(read only)	  BG name
>Note：The service configuration can be set to a certain business group or shared to all business groups. When sharing to all business groups, some settings cannot be specified during service configuration. When a user applies for a service and a service group is specified, it will be determined by resources on the business group
+ Status (read only)
	Service item status
•	Published: Publish service items to the service catalog
•	Unpublished: Service item is not published
•	Expired: Service item has expired
+ Service Deployment Lease Time (Day)	After the service deployment lease time expires, all instances in the deployment will be shut down. The configurable lease time is set within the interval configured by the business group. Check "Allow modification" and "Modify only when approved".

+ Service deployment retention time (day)	After the retention time is reached, the deployment will be dismounted. The configurable retention time is set within the interval configured by the business group. Check "Allow modification" and "Modify only when approved". 

+ Enable association rules	  Support for forcibly distributing vSphere virtual machines to different physical machines or to the same physical machine



4.   Click the “Approval Configuration” tab to select the approval process (built-in default approval process or custom approval process, for example: parallel approval process), view approval process flow chart, approval process step

5.   Click the “Workflow” tab and select the service process (built-in standard cloud service deployment process or customized service process) to view the service flow chart and service process steps.

6.   Click the "Form " tab to select the form, form preview


7.   Click the Component Configuration tab to see the blueprint topology and all components in the configuration service:

There are three types of components in the component configuration list: computing components, software components, and network components:

 + Computational components: refer to servers or compute nodes such as Server, Windows Server, Instance, etc.

 + Software components configuration: applications that are typically placed on servers or compute nodes, such as Apache, MySQL, etc.

 + Network components: refer to the network configuration of the server, such as network

Component configuration:

 - Compute component configuration: You can add monitoring to the current node or server by selecting a virtual machine template with monitoring enabled

 - Software components: You can add monitoring points to enable monitoring. The nodes where the software components are located must be enabled for monitoring, and the monitoring of software components will take effect. After the monitored server or node and software components are deployed successfully, you can view the currently deployed monitoring data information on the Monitoring tab of the Deployment Details page. The corresponding node instance details page also has a node monitoring tab for the user to monitor the current node's data. At the same time, if the software component with monitoring points is installed in the current node, you can view the monitoring data of the software components by adding monitoring points.


## Cloud Resource Allocation Strategy

In the service configuration, configure the cloud resource configuration of the instance node. Pay attention to the resource bundle selection strategy. The platform mainly provides the following strategies:

+	Manual designation: Specify the resource bundle manually. If the resource bundle selection strategy selects “manual designation”, which supports the use of resource labels and narrows down the selection, the “resource bundle” selection item will appear. Select the resource bundle in the drop-down box and specify the resource bundle. You can choose to check "Allow modification" and "Only modify during approval". 

+	Automatically select the one with largest remaining capacity: The platform automatically selects the currently selectable resource bundle according to the policy, with the smallest resource usage and the largest remaining capacity.

+	Automatically select the lowest cost: The platform supports setting resource charging rules and selecting the currently selectable resource bundle according to the policy, with the lowest cost and the least cost.

+	Even Allocation: When services are deployed, resources are evenly distributed to different resource bundles.




# Add Cloud Resource Blueprint Service Configuration

## Configure vSphere Single-Node Service {#Configure vSphere Single-Node Service}

1.  Click “Service desgin” - “Catalog Config” on the left navigation, click “Add” in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select [Build vSphere Single-node Blueprints](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Build%20vSphere%20Single-node%20Blueprints), business group, click "submit"

2.  "Overview" "Input and Output" and "Service Deployment Operation Entitlement" configuration please refer to [Overview]

3.  Components: You can see the vSphere service topology and all components: Server, Network

 + Server: Click the server name to enter the detailed settings of the node. There are tabs such as "Basic Information", "Server Configuration", "Network", "User", "Disk", "Relation" and "Operation Permission".

Basic Information:

 
+ Basic Information     Shows basic information such as the type, category, and name of the server.
+ Number of instances   Select the number of instances deployed

 >「Note」check "Allow modification" and "Modify only when approved". There are two cases here: if you select “Allow modification", the user can modify the number of instance parameters when requesting the service, and can also modify the number of instance parameters during the service approval phase; if both "Allow modification" and "Modify only when approved" are selected, the user cannot modify the number of instance parameters when requesting service, and only allows the number of instance parameters to be modified during the service approval phase;
 
 
Server Configuration:
Computing resource
+ OS Hostname	The OS host name (Hostname) inherits the business group naming rules by default when it is not defined. Check "Allow modification" and "Modify only when approved". There are two cases here:
1.  if you select Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase;
2.  if you select both "Allow modification" and "Modify only when approved", the user cannot modify the parameters in the service request, the parameters are only allowed to be modified during the service approval phase;
+ Instance name  	The cloud host name inherits the business group naming rules by default when it is not defined. Check "Allow modification" and "Modify only when approved".
+ Comment	Optional, check "Allow modification" and "Modify only when approved".

Resource Bundle Configuration
+ Resource bundle selection policy
1.	Automatic selection: default option, the platform automatically selects resource pool according to policy
2.	Based on the resource label selection: If the resource map is already in the blueprint used by the service, the resource label is inherited by default. The resource bundle matching the label in the business group is selected according to the label (provided the resource bundle has the resource label set). Resources are deployed to specific resource bundles. You can also select other resource tags in the service configuration; check "Allow modification" and "Modify only when approved".
3.	Manual specification: manually specify the resource bundle. If the resource bundle selection policy selects “manually specified”, the “resource bundle” option will appear, specify the resource bundle, and select “Allow modification” and “Modify only when approved”.
>「Note」If the service is shared to all business groups, the resource bundle cannot be specified. By default, "Allow modification" and "Modify only when approved" are mandatory. If the service is assigned to a service group, the resource bundle under the service group is selected.
+ AD Domain (Windows): AD Domain	After checked, fill in the AD domain name and user name and password. The virtual machine after the service is deployed will be added to the AD domain.

Template setting
+ OS name	Select Linux/Windows operating system
+ VM template	Select the vSphere VM template under this operating system.

Computing specification configuration
+ Computing specification mode	Defines how the instance CPU and memory are configured. “Custom” allows direct entry of numbers, and “Fixed Specifications” will be selected according to the computing specifications configured by the administrator.
+ vCPU Quantity	If you want to customize the computing specification mode, enter the number of vCPUs, check "Allow modification" and "Modify only when approved". 
+ Memory (GB)	If you want to customize the computing specification mode, enter the memory, check "Allow modification" and "Modify only when approved". 
+ Computing Specifications	If you want to customize the computing specification mode, enter the memory, check "Allow modification" and "Modify only when approved".
+ Configure related computing specifications in System - Computing Specifications

System Disk configuration

+ Provisioning mode	   (This option appears only if you select a fully cloned virtual machine template)
Supports three provisioning modes: thin provisioning, thick provisioning delay zeroing, thick provisioning zeroing
+ Folder	The virtual machine is deployed in the selected vCenter folder while supports changes when applying.
Need to select a folder in the Resource Bundle - Cloud Platform Resource Information
+ Data Storage Policy	(This option will only appear if you select a fully cloned virtual machine template). By default, the data storage default value is selected. In the drop-down selects the storage policy configured in VMware vCenter. You may check "Allow modification" and "Modify only when approved". 
+ Storage	Virtual machine is deployed in the selected storage, and the storage determines the compatibility according to the selected storage policy, and displays the free space, total space, and proportion of the storage. If not selected, it is deployed in the storage defined by the resource bundle.



 + Network: Configure access domain (optional) and DNS server (optional); IP assignment mode is specified according to the configuration in the resource bundle, and different network labels can be selected in the Network node.

 + Users (Linux service): You can add Linux users and user groups. One user can have multiple user groups. A user group can have multiple users. After the virtual machine is successfully deployed, there will be corresponding users and groups and the user can choose whether to set it to sudoer. Note: The User Tab page appears only if the agent is installed (installed at deployment time)

 + Disk view: Linux virtual machine logical volumes can be configured. In addition to creating hard disk partitions directly, you can also choose to create logical volumes.

<!-- -->

 + To create a logical volume (LV), you need to create a volume group (VG) and then add a physical volume (PV) to the volume group as the underlying resource of the volume group before you can create a logical volume. The total size needs to be no larger than the total resource size of the volume group. Physical volume can check the swap option to create a swap partition

 + Add/Change Disk (Physical Volume PV): When the storage is empty, click next to and it turns green to indicate that the disk allows being added during deployment. The added disk needs to fill in the size and provisioning mode (currently required), mount point, volume group, data storage name optional 

<!-- -->

 + Relationships: selectable virtual machines that can be associated

 + Operational Entitlement: Refer to Add Cloud Resource Ops Entitlement to some service

<!-- -->

 + Network: Click the network name to enter the node detailed settings. There are two tabs: “Basic Information” and “Properties”.

<!-- -->

 + Basic Information: View Network component type, category, name

 + Properties: You can select the network label and the management network. The network label supports “Allow modification” and “Modify only when approved”.

4.  Service Deployment Operation Entitlement: Here you can enable actions in Service Deployment Management and configure the required approval process. For each operation, different rules and approval processes can be configured for different roles. By default, the business group configuration is inherited, and can be added or deleted. The role list can be filtered.

5.  Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, the vSphere VM service is configured and released successfully.

## Configure VMware NSX Services {#Configure VMware NSX Services}

Configure the vSphere service with the NSX cloud platform. Here are the pre-service operation:

1.  Ensure that the business group has added the vSphere cloud platform and VMware NSX cloud platform, and add the association with the VMware NSX cloud platform at the vSphere cloud platform.

2.  In the vSphere resource bundle, associate the transport area of VMware NSX (will affect the display of the NSX Logical Switch)

3.  After the association is successful, see the three additional tabs of NSX Logical Switch, NSX Logical Router, and Security Policy Group in Resource bundle - vSphere Resource bundle - Network Resources.

 + Configure the NSX Logical Switch, select the switch and allocate the resource bundle (the network resource and the NSX logical switch are configured at least one)

 + Configure NSX Logical Router and select DLR to join the resource bundle

 + Configure the Security Policy Group and check the existing security policy group

4.  Click Save to configure the VMware NSX resource bundle successfully.

### Start configuring the VMware NSX virtual machine service:

1.  "Service Design" - "Catalog Config" - "Add", fill in the service name, select the VMware NSX Blueprint, select the business group, click "Submit"

2.  "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3.  Click on “Component” to see the VMware NSX blueprint topology and all components: Lswitch, Server, SecurityGroup, DLR
-  Server: the same configuration as 6.3.3.1 vSphere service
-  Lswitch: click the Lswitch name to enter the “Node Detail Settings” page: There are two tabs: “Basic Information” and “Properties”.

Basic Information: View basic information about the Lswitch, such as type, category, and name

Properties: 

Properties (uncheck the use of existing network)
+   IP allocation mode                   Supports IP pool and manual designation. If you select an IP pool, you need to specify an IP pool.
+   Copy mode                            Select Unicast. Support unicast, multicast and hybrid
+   Network Management                   Check whether to manage the network

Properties (check to use existing network)
+   Network Label                     Select from the existing network, check "Allow modification" and "Modify only when approved". (need to select the NSX logical switch in the vSphere with NSX resource bundle)
+   IP allocation mode                Supports IP pool, DHCP, and manual designation
+   Network Management                Check whether to manage the network

- DLR: click the DLR name to enter the “Node Detail Settings” page: There are two tabs: “Basic Information” and “Properties”.

Basic Information: View basic information about the DLR, such as type, category, and name

Properties page: Select an existing logical router (DLR) (select NSX logical router in the resource bundle); add interface configuration



- SecurityGroup: click on the SecurityGroup name to enter the “Node Detail Settings” page: There are two tabs: “Basic Information” and “Properties”.



Basic Information: View basic information about the SecurityGroup, such as type, category, and name

Properties: Properties (do not check the use of existing security groups) 
 
+   Name                           Create a new security group, fill in the name of the security group, and check "Allow modification" and "Modify only when approved". 
+   Description                    Fill in the description of the security group (optional)


Properties (check to use existing security groups) 
+   Security Group                 Select one of the existing security groups and select one or more security policies for the resource bundle in the resource bundle “Security Policy Group”.


4.  Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, the VMware NSX service is configured and released successfully.

## Configure vSphere MySQL with Monitoring Service {#Configure vSphere MySQL with Monitoring Service}

1.  In the left navigation, click "Service Design" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select [Create vSphere MySQL with Monitoring Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20vSphere%20MySQL%20with%20Monitoring%20Blueprint), business group, click "Submit" 

2.  "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3.  Component: You can see the vSphere service topology and all components: Server, Network

 + Server: The configuration is the same as the 6.3.3.1 vSphere service (you need to select the VM template with the automation agent)

 + Network: The configuration is the same as the 6.3.3.1 vSphere service.

 + MySQL: Click on the MySQL name to enter the detailed settings of the node. There are tabs such as “Basic Information”, “Properties” and “Relationships”

<!-- -->

 + Basic Information: Basic information such as the type, category, and name of MySQL

 + Properties: Shows information about the MySQL primary key, from the configuration in Service Design - SW Components

 + Relationship: Shows the relationship between Server and MySQLExporter 

<!-- -->

 + “MySQLExporter: Click the MySQLExporter name to enter the detailed settings of the node. There are tabs such as “Basic Information”, “Properties” and “Relationships”.

<!-- -->

 + Basic Information: Basic information such as the type, category, and name of MySQLExporter

 + Properties: Shows the MySQLExporter primary key related information from the configuration in Service desgin - Software Components. If the package_url is not filled, you need to fill in the address.

 + Relationships: Shows the relationship between Server and MySQLExporter

4.  Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, vSphere MySQL is configured and released successfully.

## Configure OpenStack Single-Node Service {#Configure OpenStack Single-Node Service}

1.  Click “Service desgin” - “Catalog Config” on the left navigation, click “Add” in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select 6.3.3.4 Create OpenStack Single-node Blueprint), business group, click "submit”

2.  "Overview" "Input and Output" and "Service Deployment Operation Entitlement" configuration please refer to Overview

3.  Components: You can see the OpenStack service topology and all components: Server, Network

 + Server: Click the server name to enter the detailed settings of the node. There are tabs such as "Basic Information", "Server Configuration", "Network", "User", "Disk", "Security policy group", "Relation" and "Operation Permission".

<!-- -->

 + Basic Information:

 
- Basic Information	 Shows basic information such as the type, category, and name of the server.
- Resource bundle selection policy
1. Automatic selection: default option, the platform automatically selects resource bundle according to policy
2. Based on the resource label selection: If the resource map is already in the blueprint used by the service, the resource label is inherited by default. The resource bundle matching the label in the business group is selected according to the label (provided the resource bundle has the resource label set). Resources are deployed to specific resource bundles. You can also select other resource tags in the service configuration; check "Allow modification" and "Modify only when approved". 
3. Manually specify: You can manually specify a resource bundle for the service. If the resource bundle selection policy is Manually Specify, the resource bundle selection will be displayed. The resource bundle will be specified.
>「Note」If the service is shared to all business groups, the resource bundle cannot be specified. By default, "Allow modification" and "Modify only when approved" are mandatory. If the service is assigned to a service group, the resource bundle under the service group is selected.


- Host Quantity	 Select the number of cloud hosts to be deployed, check "Allow modification" and "Modify only when approved". 

+  Properties:


 + OS Hostname       The OS host name (Hostname) inherits the business group naming rules by default when it is not defined. Check "Allow modification" and "Modify only when approved". 
 + Instance name     The cloud host name inherits the business group naming rules by default when it is not defined. Check "Allow modification" and "Modify only when approved". 
 + OS name	        Select Linux operating system
 + VM template	    Select the OpenStack VM template under this operating system.
 + Volume Type  	If you select a VM template that is booted from a cloud drive or started from a cloud drive snapshot, this option appears. Select the volume type that already exists on the OpenStack cloud platform, or select the volume type not set.
 + Volume Size    	If you select a VM template that is started from the cloud disk or started from the cloud disk snapshot, this option will appear. The volume size must be greater than or equal to the disk size required by the image. Optional
 + Host collection	 virtual machine deployment to selected host
 + VM Specifications     Select the deployed VM CPU and memory specifications, and check "Allow modification" and "Modify only when approved". 

 + Network Resources: Configurable DNS: DNS name, DNS domain, DNS type (A type only), DNS server (check "Allow modification" and "Modify only when approved". 
 + Users (Linux service): You can add Linux users and user groups. One user can have multiple user groups. A user group can have multiple users. After the virtual machine is successfully deployed, there will be corresponding users and groups and the user can choose whether to set it to sudoer. Note: The User Tab page appears only if the agent is installed (installed at deployment time)

 + Disk view: Linux virtual machine logical volumes can be configured. In addition to creating hard disk partitions directly, you can also choose to create logical volumes.

<!-- -->

 + To create a logical volume (LV), you need to create a volume group (VG) and then add a physical volume (PV) to the volume group as the underlying resource of the volume group before you can create a logical volume. The total size needs to be no larger than the total resource size of the volume group. Physical volume can check the swap option to create a swap partition

 + Add/Change Disk (Physical Volume PV): When the storage is empty, click next to and it turns green to indicate that the disk allows being added during deployment. The added disk needs to fill in the size and provisioning mode (currently required), mount point, volume group, data storage name optional 

<!-- -->

 + Security Policy Group: Select a security policy group for the virtual machine

 + Relationships: selectable virtual machines that can be associated

 + Operational Entitlement: Refer to Add Cloud Resource Ops Entitlement to some service 

<!-- -->

 + Network: Click the network name to enter the node detailed settings. There are two tabs: “Basic Information” and “Properties”.

<!-- -->

 + Basic Information: View Network component type, category, name

 + Properties: You can select the network label and the management network. The network label supports “Allow modification” and “Modify only when approved”. 

4.  Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, the OpenStack VM service is configured and released successfully.

## Configure OpenStack Firewall Service{#Configure OpenStack Firewall Service} 

1.  Click “Service desgin” - “Catalog Config” on the left navigation, click “Add” in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design, business group, click "submit"

2.  "Overview" "Input and Output" and "Service Deployment Operation Entitlement" configuration please refer to Overview

3.  Components: You can see the OpenStack Firewall service topology and all Firewall components:

Basic Information page: View Firewall component type, category, name

Properties：Properties (do not check the use of an existing firewall)
 
+ Name	Firewall name (check "Allow modification" and "Modify only when approved". There are two cases here: if you select “Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase; if you select both "Allow modification" and “Modify only when approved”, the user cannot modify the parameters in the service request, only the parameters are allowed to be modified during the service approval phase.
+ Description	Optional
+ Administrator status	 enabled, disabled, enabled by default
+ Routes	Routes are only allowed to be selected at the time of request. You need to add routes when configuring OpenStack resource bundles.
+ Check "Use existing strategy"	     Select an existing policy, check "Allow modification" and "Modify only when approved". There are two cases here: if you select “Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase; if you select both "Allow modification" and “Modify only when approved”, the user cannot modify the parameters in the service request, only the parameters are allowed to be modified during the service approval phase.
+ Uncheck "Use existing policy"     	 Create a new policy, fill in the policy name (required), policy description (optional), and choose whether to "shared" and "audited".
  If you select “Shared”, you can only select the shared policy and the rules under the policy when you perform the operation “Update Firewall Policy” on the Firewall.
  If “Shared” is not checked, you can select the “Shared” and “Unshared” policies and their policies under the policy when you perform the operation “Update Firewall Policy” on the Firewall.

+ Resource bundle selection strategy	Support resource bundle selection strategy
+ Resource bundle	When a service group is associated with multiple OpenStack resource bundles, it is supported to select which resource bundle to use.


Properties (check to use an existing firewall)
+ Firewall	Select one of the existing firewalls, check "Allow modification" and "Modify only when approved". There are two cases here: if you select “Allow modification", the user can modify the parameters when requesting the service, and can also modify the parameters during the service approval phase; if you select both "Allow modification" and “Modify only when approved”, the user cannot modify the parameters in the service request, only the parameters are allowed to be modified during the service approval phase.
+ Resource bundle selection strategy	Support resource bundle selection strategy
+ Resource bundle	When a service group is associated with multiple OpenStack resource bundles, it is supported to select which resource bundle to use.



4.  Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, OpenStack Firewall VM service configuration and release is successful.



## Configure OpenStack LoadBalancer with SecurityGroup Service{#Configure OpenStack LoadBalancer with SecurityGroup Service}
1.  In the left navigation, select "Service Design" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design, business group, click "Submit"

2.  "Overview" "Input and Output" and "Service Deployment Operation Entitlement" configuration please refer to Overview

3.  Component: You can see the OpenStack LoadBalancer with SecurityGroup service topology and all components: Server, Network, LoadBalancer, Listener, SecurityGroup

 + Server: Server node configuration refer to [Create OpenStack Single-node Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20Single-node%20Blueprint)

 + Network: Network node configuration refer to  [Create OpenStack Single-node Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20Single-node%20Blueprint)

 + LoadBalancer: Click the LoadBalancer name to enter the node detailed settings. There are two tabs: Basic Information and Properties.

<!-- -->

Basic Information: basic information such as display type, category, name, etc.

Properties:

Properties (do not check the use of existing resources)
+ Service Provider	Select LoadBalancer's service provider. Support F5 and HA
+ Name	Fill in the name (required), check "Allow modification" and "Modify only when approved". 
+ Description	Optional
+ DNS name	DNS name is only allowed to fill in when requesting service. If you need to specify DNS, please tick to allow change when applying.
If you select to allow modification when applying, the DNS server will be required, and the DNS type is A.
+ DNS domain	Optional, check "Allow modification" and "Modify only when approved".
+ DNS server  	Optional, check "Allow modification" and "Modify only when approved". 
+ DNS Type	    Optional, check "Allow modification" and "Modify only when approved".

Properties (check to use existing resources)
+ Service Provider  	Select LoadBalancer's service provider. Support F5 and HA
+ Name  	Fill in the name (required), check "Allow modification" and "Modify only when approved". 
+ DNS name	DNS name is only allowed to fill in when requesting service. If you need to specify DNS, please tick to allow change when applying.
If you select to allow modification when applying, the DNS server will be required, and the DNS type is A.
+ DNS domain	Optional, check "Allow modification" and "Modify only when approved".
+ DNS server  	Optional, check "Allow modification" and "Modify only when approved". 
+ DNS Type	    Optional, check "Allow modification" and "Modify only when approved".


 + Listener: Click on the Listener name to enter the detailed settings of the node. There are four tabs: "Basic Information", "Properties", "Members", "Policies and Rules".

<!-- -->

 + Basic Information: basic information such as display type, category, name, etc.

 + Properties:

Properties (do not check the use of existing resources)
+   Name	                     Fill in the name (required), check "Allow modification" and "Modify only when approved". 
+   Description	                 Optional
+   Protocol                     Select protocol (optional), support HTTP, TCP, UDP, check "Allow modification" and "Modify only when approved". 
+   Port                         Fill in the port number (required), such as 80, check "Allow modification" and "Modify only when approved". 
+   Traffic Distribution Algorithm            Select an algorithm (optional), check "Allow modification" and "Modify only when approved". 

Properties (check to use existing resources) 
+  Name                        Fill in the name (required), check "Allow modification" and "Modify only when approved". 

 + Members: internal members and external members. Internal members list all server/windowsServers associated with the Listener node in the current blueprint; external members can add external members, fill in IP addresses (required), subnets (Required), port (required), weight, etc.

 + Health Monitoring page:

<!-- -->

 + Monitoring type: Support multiple monitoring types, such as HTTP, HTTPS, TCP, etc. Check "Allow modification" and "Modify only when approved". 

 + Interval (seconds): Must be greater than or equal to 1, check "Allow modification" and "Modify only when approved". 

 + Maximum number of retries: 1~10, check "Allow modification" and "Modify only when approved". 

 + Timeout (seconds): The timeout (seconds) must be less than or equal to the time interval (seconds), check "Allow modification" and "Modify only when approved".

 + HTTP method: If the monitoring type selects HTTP, the HTTP method will be selected. For example, GET, POST, etc., check "Allow modification" and "Modify only when approved". 

 + Expected status code: If the monitoring type selects HTTP, the desired status code will be filled in.

 + URL path: If HTTP is selected for the monitoring type, the URL path will be filled in, and “Allow modification” and “Modify only when approved” will be selected.

<!-- -->

 + Policies and Rules page: You can create new policies and rules that apply to the Listener, check "Allow modification" and "Modify only when approved". Click to add strategy, fill in the name, select the operation (required, REDIRECT_TO_POOL, REDIRECT_TO_URL, REJECT), description (optional), Weight, redirect URL (select this item in REDIRECT_TO_URL)

<!-- -->

 + SecurityGroup: Click on the SecurityGroup name to enter the node detailed settings. There are two tabs: "Basic Information" and "Properties".

<!-- -->

 + Basic Information: basic information such as display type, category, name, etc.

 + Properties: Default Use Existing Security Group to select a security group

>「Note」In the OpenStack resource bundle, you need to select an IPSec policy group in the "Network Resources" - "Security Policy Group" before you can select an existing security group on the SecurityGroup "Properties" page.

4. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, OpenStack LoadBalancer with SecurityGruop VM service is configured and released successfully.

## Configure OpenStack FloatingIP Service {#Configure OpenStack FloatingIP Service}

1.  In the left navigation, select "Service desgin" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (6.3.3.7 OpenStack FloatingIP Blueprint), business group, click "submit" 

2.  "Overview" "Input and Output" and "Service Deployment Operation Entitlement" configuration please refer to Overview

3.  "Component Configuration": you can see the OpenStack FloatingIP service topology map and component FloatingIP

 + FloatingIP: Click on the LoadBalancer name to enter the node detailed settings. There are two tabs: "Basic Information" and "Properties".

<!-- -->

 Basic Information: basic information such as display type, category, name, etc.

 Properties

 Properties (do not check the use of existing resources) 
  
+ Network                       Select the network of FloatingIP, check "Allow modification" and "Modify only when approved". 
+ Subnet                        Select the subnet corresponding to the FloatingIP network, and check "Allow modification" and "Modify only when approved". 
+ IP allocation mode            Select IP allocation mode, support IP pool, DHCP, manual designation. If you choose manual designation, you need to specify the IP address when the service is applied.
+  IP pool	                    If you choose the IP pool allocation method, select the IP pool.
+  DNS name                      DNS name is only allowed to fill in when requesting service. If you need to specify DNS, please tick to allow change when applying.
+ DNS domain	        Optional, check "Allow modification" and "Modify only when approved".
+ DNS server        	Optional, check "Allow modification" and "Modify only when approved". 
+ DNS Type	            Optional, check "Allow modification" and "Modify only when approved".

Properties (check to use existing resources)     
+   Floating IP                       Select the network of FloatingIP, check "Allow modification" and "Modify only when approved". 

4. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, OpenStack FloatingIP VM service configuration and release is successful

## Configure OpenStack DNS Service{#Configure OpenStack DNS Service}

1. In the navigation tbar on the left, choose Service desgin - Catalog Config, click Add in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design, business group, click "submit"

2. "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3. Component Configuration view: You can see the OpenStack DNS service topology map and component DNS

 + DNS: Click on the DNS name to enter the node detailed settings. There are two tabs: "Basic Information" and "Properties".

<!-- -->

Basic Information: basic information such as display type, category, name, etc.

Properties:


+ DNS type	Supports A, CNAME, MX, TXT
•	A record: IP address of the WEB server, used to specify the IP address record corresponding to the host name (or domain name)
•	CNAME record: alias resolution
•	MX record: mail exchange record
•	TXT record: a description of a host name or domain name
•	MX Priority If the DNS type selects MX, the menu "MX Priority" will appear.
+ MX Priority	If the DNS type selects MX, the menu "MX Priority" will appear.
+ DNS Name	Enter the name of the DNS. By default, it is mandatory to allow changes when applying.
+ DNS domain	Select the DNS domain and add the DNS domain in the system configuration.
+ DNS server	Select the DNS server configured in the OpenStack cloud platform server of the service group.
+ DNS parameters	
•	If the DNS type is selected A: fill in the IP address, support multiple, separated by commas;
•	If the CNAME of the DNS type is selected: Enter the domain name, for example test.example.com
•	If the DNS type is selected MX: Enter the domain name, for example test.example.com
•	If the DNS type is selected TXT: enter a description


4.  ④	Click “Save” to return to the component list interface. Click "Verify". After the verification is successful, "Save and Publish" the service. The OpenStack DNS VM service is configured and successfully released.

## Configure Kubernetes Service {#Configure Kubernetes Service}

1.  In the navigation tree on the left, choose Service desgin - Catalog Config, click Add in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (choose 6.3.3.9 Creat Kubernetes Blueprint), business group, click "Submit"

2.  "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3.  "Component Configuration" view: you can see the Kubernetes service topology map and all the components in the service configuration. According to the Kubernetes blueprint, there are four components, namely Deployment, Service, Container, PersistentVolumeClaim.

 + Deployment: Click the Deployment name, go to the “Basic Information” page, click “Properties”, you can choose the number of copies, the default is 1, click “Save”

 + Container: Click on the Container name to go to the basic information page, click on the "Properties" tab:

  Container         

+   Image Source        Select the added image source. Habor and Docker Trusted Registry image sources can be added to the Kubernetes cloud platform. Check "Allow modification" and "Modify only when approved".
+   Image Name          If the image source is selected, the image under the image source is automatically filtered. If the image source is not selected, the name can be automatically created. Check "Allow modification" and "Modify only when approved". 
+   Image Label          Select the desired image label, check "Allow modification" and "Modify only when approved". 
+   Resource Specifications - CPU	Enter the requested CPU size and the maximum CPU size. The requested CPU cannot be greater than the maximum limit.
+   Resource Specifications - Memory	Enter the requested memory size and the maximum memory size. The requested memory cannot be greater than the maximum limit.
+   Container Open Port	e.g. 8080
+   Environment Variable	For example, the value of the parameter /JRE_Home is /usr

 + Service：Click the Service name to enter the basic information page, click “Properties” to configure the port mapping, click on the right side, fill in the following information:

+  Service port	  The port that the service is open to, such as 8080
+  The Deployment node it depends on	 Select a Deployment node that the Service depends on.
+  The Container node that depends on	 Select the container node in the Deployment
+  Container Open Port	                 Select the open port configured in the container
+  Host port	                         Select the open port of Node, the default range is 30000-32767
+  Protocol	                             TCP or UDP

PersistentVolumeClaim: Click on the PersistentVolumeClaim name, go to the basic information page, and click on "Properties":
+  Mount Point	           e.g. /opt/share
+  Access Mode	           Support ReadWriteOnce, ReadOnlyMany, ReadWriteMany
+  Storage	               Standard
+  Space limit (Gi)	       Input space size

4. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, Kubernetes VM service configuration and release is successful

## Configure Alibaba Cloud Service {#Configure Alibaba Cloud Service}

1. In the left navigation, select “Service desgin” - “Catalog Config”, click “Add” in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design, business group, click "Submit"

2. "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3. Component Configuration: You can see the Alibaba Cloud service topology map and all components in the service configuration: Instance, SecurityGroup

    + Instance: Click on the Instance name to enter the detailed settings of the node. There are tabs such as "Profile", "Network", "Properties", "Storage", "Security Policy Group", "Load Balancing", "Operation Permission", etc.
4. Overview: 
 Basic Information	Shows basic information such as the type, category, and name of the Instance.
 Resource bundle selection policy 
 - Automatic selection: default option, the platform automatically selects resource bundle according to policy
 - Based on the resource label selection: If the resource map is already in the blueprint used by the service, the resource label is inherited by default. The resource bundle matching the label in the business group is selected according to the label (provided the resource bundle has the resource label set). Resources are deployed to specific resource bundles. You can also select other resource tags in the service configuration; check "Allow modification" and "Modify only when approved".
 - Manually specify: You can manually specify a resource bundle for the service. If the resource bundle selection policy is Manually Specify, the resource bundle selection will be displayed. The resource bundle will be specified.
>「Note」If the service is shared to all business groups, the resource bundle cannot be specified. By default, "Allow modification" and "Modify only when approved" are mandatory. 


5.  Network:

+ Availability Zone	Select the Availability Zone of the network. Changing the Availability Zone may result in corresponding changes in virtual switches, virtual machine specifications, disk types, etc.
+   Network type	Displays according to the type of network configured in the resource bundle
+   Proprietary network	If you choose proprietary network, you need to choose a proprietary network.
+   Virtual switch	If you choose a private network, you need to select a virtual switch.
+   Assign Public IP Address	Select this option to install software components or run scripts.

6. Properties:


+ Payment method	Choose prepaid or postpaid
+ Virtual machine image	 Select virtual machine image on Aliyun
+ Virtual machine specifications	Select virtual machine specifications
+ Monitoring mode	Select monitoring mode, no monitoring or SSH installation monitoring agent
+ Install automated agent	Not installed or SSH installed
+ Application blueprint automation deployment, service configuration initialization and mounting of disks, and some virtual machine operations (such as resetting passwords, adding new logical volumes, etc.) will use this agent; if not installed, these features will be affected. Installation of an automation agent prerequisite: The network type must be a proprietary network (VPC)
+ Username	root user
+ Password	Please enter the password for the template to install the software on this virtual machine
+ Purchase resource duration unit (prepaid)	month or week
+ Purchase unit duration
(Prepaid)	If you select the “month” for the resource duration, you can select the time from 1 to 9, 12, 24, 36, 48, 60, etc.
If you purchase the resource duration unit and select "Week", you can choose 1~4 weeks.
+ Whether to automatically renew
(Prepaid)	If the automatic renewal is checked, the corresponding week or month is extended according to the unit of time when purchasing resources.

Storage page: support adding or editing disk information, add disk to fill in description (optional), select disk type, fill in size (GB), select snapshot

Security Policy Group page: Default security policy group and not editable

Load Balancing page: None

Operation Entitlement: The service group is inherited by default. 

「SecurityGroup 」: Click on the SecurityGroup name to enter the node detailed settings. There are two tabs: “Basic Information” and “Properties”.
•	Basic Information page: View SecurityGroup component type, category, name

•	Properties:
- Use an existing security group to select an existing security group (a security group configured in the resource bundle)
- If you need to create a new security group, you need to create a new security group here in the "Service desgin" - "Blueprints" - Aliyun Blueprint - SecurityGroup - parameter option, uncheck "Use existing resources"

  +  NIC type: choose private network or public network
  +  Rule direction: choose entrance or exit
  +  Authorization policy: choose to allow or deny
  +  Protocol type: select all or http, udp, icmp, gre
  +  Port range: the range is from 1 to 65535; for example, "1/200", "80/80"
  +  Authorization type: address segment access
  +  Authorized object: Please set the authorization object carefully. According to the authorization policy, 0.0.0.0/0 means to allow or deny access to all IPs (click “Teach me to set”)
  +  Priority: set rule priority

7. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, Aliyun service configuration and release is successful.

## Configure Azure Services {#Configure Azure Services}

1. In the left navigation, select "Service desgin" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design, business group, click "Submit"

2. "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3. Component: You can see the Azure service topology map and all the components in the service configuration: Instance, VirtualNetwork, AvailabilitySet, SecurityGroup, LoadBalancer, LoadBalancerRule, BlobContainer

 +  Instance: Click on the Instance name to enter the detailed settings of the node. There are tabs such as “Profile”, “Cloud Resource Configuration”, “Network” and “Operation Entitlement”.

 +  Overview page: Displays basic information such as type, category, and name. You can set the number of virtual machines to be deployed, and check "Allow modification" and "Modify only when approved".

 +  Cloud Resource Configuration”: includes four parts: “Cloud Host Configuration”, “Resource bundle Configuration”, “Virtual Machine Template Configuration” and “Resource Specification Configuration”.

1. VM Configuration  	VM name, default inherits the business group naming rules, check "Allow modification" and "Modify only when approved". 
2. Resource bundle Configuration	  
  + Resource bundle Selection Policy: Currently supports “manually specify” a resource bundle, check “Allow modification” and “Modify only when approved”. 
  + Diagnostic storage account: Select a storage account.
  + Disk Type: Select a disk type such as HDD or SSD.
3. VM template configuration
  + Operating system name: Select Windows or Linux operating system
  + VM template: Select Azure VM template under Windows or Linux operating system
4. Resource Specification Configuration	 
  + Resource Specification: Select a resource specification created by the system
  + Cloud platform specification: Select one of the Azure cloud platform resource specifications under the resource specification


 + Network page: Displays information such as virtual network name, subnet, and IP assignment. You can check "Use public IP".

 + Operation Entitlement: The service group is inherited by default. 

<!-- -->

 + Virtual Network: Click on the Virtual Network name to enter the detailed settings of the node. There are tabs such as “Basic Information” and “Properties”.

<!-- -->

 + Basic Information page: Displays information such as type, category, and name.

 + "Properties" page: Select subnets, check "Allow modification" and "Modify only when approved". T

<!-- -->

 + Availability Set: Click on the Availability Set name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties".

<!-- -->

 + Basic Information: Displays information such as type, category, and name.

 + Properties: By default, Use Existing Resources is checked. You can select the availability set, check "Allow modification" and "Modify only when approved". 

<!-- -->

 + Security Group: Click on the Security Group name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties". 

<!-- -->

 + Basic Information: Displays information such as type, category, and name。

 + Properties: By default, Use Existing Security Group is checked. You can select the security group, check "Allow modification" and "Modify only when approved". 

<!-- -->

 + LoadBalancer: Click on the LoadBalancer name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties".

<!-- -->

 + Basic Information: Displays information such as type, category, and name

 + Properties: By default, Use Existing Resources is checked. You can select the load balancer and check "Allow modification" and "Modify only when approved". 

<!-- -->

 + LoadBalancerRule: Click the LoadBalancerRule name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties".

<!-- -->

 + Basic Information: Displays information such as type, category, and name.

 + Properties: Enter the load balancing rule name, select the front-end IP address and communication protocol (TCP/UDP), input port, and back-end port. All of the above items are checked "Allow modification" and "Modify only when approved". 

<!-- -->

 + BlobContainer: Click on the BlobContainer name to enter the node detailed settings. There are tabs such as "Basic Information" and "Properties".

<!-- -->

 + Basic Information page: Display type, category, name, etc.

 + Properties: Select a resource bundle based on Resource bundle Selection Policy (Manually Specify/Automatically Select/Resource-Based Label Selection), check "Allow modification" and "Modify only when approved". 

4. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and publish" the service, Azure service configuration and release is successful.

## Configure AWS Services {#Configure AWS Services}

1. In the navigation tree on the left, choose Service desgin - Catalog Config, click Add in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select AWS Blueprint), business group, click "Submit"

2. "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3. Component Configuration: You can see the AWS service topology map and all the components in the service configuration: Instance, SecurityGroup

 + Instance：Click the Instance name to enter the detailed settings of the node. There are tabs such as “Profile”, “Cloud Resource Configuration” and “Operation Entitlement”

<!-- -->

Overview:

+ Basic Information	Shows the basic information such as the type and name of the Instance.
+ Instance Quantity   The default number of instances is 1. You can change or select "Check Allow changes" and "Modify only when approved".

Cloud Resource Configuration:


1. Virtual Machine configuration

+ VM Name	 Inherit the business group naming rules by default when it is not defined. Support the check box "Allow modification" and "Modify only when approved".

2. Resource bundle Configuration: Resource bundle selection policy

+ Manually specify: You can manually specify a resource bundle for the service. If the resource bundle selection policy is Manually Specify, the resource bundle selection will be displayed. The resource bundle will be specified.

> 「Note」If the service is shared to all business groups, the resource bundle cannot be specified. By default, "Allow modification" and "Modify only when approved" are mandatory. If the service is assigned to a service group, the resource bundle under the service group is selected.

+ Resource bundle	    Select a resource bundle that will be filtered according to the blueprint type
+ Availability Zone	  Select an Availability Zone to filter based on the Availability Zones in the selected resource bundle.
+ Subnet	            Select a subnet to filter based on the subnet configured in the selected resource bundle

3. Virtual machine template configuration

+ Operating system	  Select Linux operating system
+ VM template	        Select the AWS VM template under the operating system.

4. Computing specification

+ Resource Specification	Select the specifications customized in "Infrastructure" - "Computing Profiles"
+ Cloud Platform Specification	Select the cloud platform specifications customized in "Infrastructure" - "Computing Profiles", which will be filtered according to the selected resource specifications.

5. Public network configuration
+ Assign a public network IP address	 Optional, whether to assign a public IP address.


Operation Entitlement: Here you can enable the operations of the virtual machine and configure the required approval process. For each operation, different rules and approval processes can be configured for different roles. The default selection inherits the business group configuration, which can be added or deleted, and the role list can be filtered.

<!-- -->

 + SecurityGroup: Click on the SecurityGroup name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties"

<!-- -->

 + Basic Information page: Display Type and Name

 + Properties

By default, "Use existing security group" is selected. Select an existing security group. After selecting it, the rules of the security group will be listed. Check "Allow modification" and "Modify only when approved". 
If you do not check "Use existing security group", create a new security group, fill in the security group name, description, and select "Allow modification" and "Modify only when approved". Click Add rules to configure the relevant security group rules

4. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, AWS service configuration and release is successful

## Configure QingCloud Service {#Configure QingCloud Service}

1. In the left navigation, select "Service desgin" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (choose QingCloud Blueprint), business group, click "Submit"

2. "Overview" "Input and Output" and "Service Deployment Operation License" view configuration please refer to Overview

3. Component Configuration: You can see the QingCloud service topology map and all components in the service configuration: WindowsInstance, SecurityGroup

 + Overview:  
   Basic Information	Shows the basic information of WindowsInstance   
   Instance Quantity   The default number of instances is 1. You can change or select "Check Allow changes" and "Modify only when approved". 

 + Cloud Resource Configuration:
   VM Name: Inherit the business group naming rules by default when it is not defined. Support the check box "Allow modification" and "Modify only when approved". 
   Resource bundle Configuration: Resource bundle selection policy.
   - Manually specify: You can manually specify a resource bundle for the service.
   - Resource bundle	Select a resource bundle that will be filtered according to the blueprint type
   - Subnet	Select a subnet to filter based on the subnet configured in the selected resource bundle

>「Note」If the service is shared to all business groups, the resource bundle cannot be specified. By default, "Allow modification" and "Modify only when approved" are mandatory. If the service is assigned to a service group, the resource bundle under the service group is selected.

+ Virtual machine template configuration: 
   Operating system	Select Linux operating system
   VM template	Select the AWS VM template under the operating system.

+  Computing specification: 
   Resource Specification	Select the specifications customized in "Infrastructure" - "Computing Profiles"
   Cloud Platform Specification	Select the cloud platform specifications customized in "Infrastructure" - "Computing Profiles", which will be filtered according to the selected resource specifications.
+  Public network configuration
   Assign a public network IP address	Optional, whether to assign a public IP address.

+ Operation Entitlement: Here you can enable the operations of the virtual machine and configure the required approval process. For each operation, different rules and approval processes can be configured for different roles. The default selection inherits the business group configuration, which can be added or deleted, and the role list can be filtered.

<!-- -->

 + SecurityGroup: Click on the SecurityGroup name to enter the detailed settings of the node. There are tabs such as "Basic Information" and "Properties".

<!-- -->

 + Basic Information page: Display Type and Name

 + Properties:

By default, "Use existing security group" is selected. Select an existing security group. After selecting it, the rules of the security group will be listed. Check "Allow modification" and "Modify only when approved". If you do not check "Use existing security group", create a new security group, fill in the security group name, click Add Rule, configure the relevant firewall rules.

6. Click “Save” to return to the component list interface. Click "Verify", after the verification is successful, "Save and Publish" the service, QingCloud service configuration and release is successful

## Configure Hyper-V Service {#Configure Hyper-V Service}

1. In the left navigation, click "Service desgin" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select Hyper-V Single-node blueprint), business group, click "submit"

2. Basic Information: 

+   Business group	        Deploy the business group to which it belongs
+   Service deployment name	 Deployment name (If the service group has set the service deployment naming rules, the service deployment name will be automatically generated according to the rules, no need to fill in)
+   Logo image	             Upload image, more beautiful in the service catalog display
+   Description	             Deployment Description
+   Service grouping	Built-in three types: work order service, database, infrastructure, support for customization. For details on service grouping, please refer to: [Service Grouping](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/ServiceGrouping.html)
+   Order                   	Specify the order in the service catalog, The smaller the value, the higher the order
+   Service status	          Shows service status in real time, such as: not released
+   Service deployment lease time (day)	           Lease time, after the lease time, all instances in the deployment will be down and archived
+   Service deployment retention time (day)	        Retention time, after the retention time is reached, the deployment will be removed
+   Allow software to be added when applying	      Check to allow software to be added when the service is requested.
+   Approval process	           Options: no approval process, default approval process, and custom approval process

3. Workflow: You can select the process type and view the process information, flowchart, and process steps.

4. Component Configuration: You can see the Hyper-V service topology map and all components: WindowsInstance and NetworkAdapter, for detailed design of component nodes. The following is a detailed description of the WindowsInstance cloud resource configuration:
 +  Resource bundle configuration                  Resource bundle selection policy: Select manual designation. Resource bundle: Select the Hyper-V resource bundle, check visible during request and it is displayed during the service request, check modifiable during request and it can be modified during the service request
 +  Computing Specifications                      	Computing Specifications: Select Mini (1C1G); Check visible during request and it is displayed during the service request, check modifiable during request and it can be modified during the service request

5. For input and output configuration, please refer to Overview

6. Service Deployment Operation Entitlement: Here you can enable actions in Service Deployment Management and configure the required approval process. For each operation, different rules and approval processes can be configured for different roles. By default, the business group configuration is inherited, and can be added or deleted. The role list can be filtered.

7. Click “Save” to return to the component list interface. Click "Verify". After the verification is successful, "Save and Publish" the service. The Hyper-V VM service is configured and released successfully.

## Configure F5 and OpenStack Combined Services  {#Configure F5 and OpenStack Combined Services}

1. In the left navigation, click "Service desgin" - “Catalog Config”, click "Add" in the upper left corner to enter the new service configuration interface, fill in the service name, service description (optional), blueprint design (select F5 and OpenStack combination) Blueprint), click "Submit".

2. Basic Information page: In addition to the service name customization, the rest is the same as the configuration of the vSphere single-node service basic information page.

3. Workflow: You can select the process type and view the process information, flowchart, and process steps.

4. Component Configuration view: You can see the OpenStack service topology and all components: Server, Network, F5 service all components: Virtual Server, Pool, and SNAT Pool 

OpenStack Server and Network components configuration reference: [Create OpenStack Single-node Blueprint](https://cloudchef.github.io/doc-en/AdminDoc/05ServiceDesign/BlueprintDesign.html#Create%20OpenStack%20Single-node%20Blueprint)

 Component configuration of the F5 service:

 1. Pool: Go to the Properties, select the resource bundle selection policy (manually specified), select the resource bundle (F5 BIG-IP resource bundle), select Allow modification, allow modification when the service is applied, select load balancing mode; 
 2. SNAT Pool: Go to the Properties view, select the resource bundle selection policy (manually specified), select the resource bundle (F5 BIG-IP resource bundle), and select Allow modification to allow modification when the service is applied. 
 3. Define the basic properties: 
   Check Use existing resources	Select an existing SNATPool, for example: F5-SNATPool
   Do not check Use existing resources	Define IP names and IP addresses.

 4. Virtual Server: Go to the Properties view, select the resource bundle selection policy (manually specified), select the resource bundle (F5 BIG-IP resource bundle), and select Allow modification to allow modification when the service is applied. IP allocation mode selection: IP Pool

5. Click “Save” to return to the component list interface. Click "Verify". After the verification is successful, "Save and Publish" the service. The F5 service is configured and published successfully.

# Edit Service Configuration

In the navigation on the left, choose Service desgin - Catalog Config. On the Service Configuration List screen, click the service configuration name and go to the Overview page. You can edit the corresponding parameters and click Save.

# Unpublish Service Configuration

In the navigation tree on the left, choose Service desgin - Catalog Config. On the Service Configuration List page, select a service configuration. If the service configuration status is Released, the Unpublish operation is available. Click OK to confirm and it is Unpublish successfully. In the service configuration list interface, the service configuration status changes to "Unpublished", and the unpublished service configuration will not be displayed on the service catalog and cannot be applied.

# Dismount Service Configuration

In the navigation tree on the left, choose Service desgin - Catalog Config. On the Service Configuration List page, select a service configuration and click Dismount Service Deployment to confirm the dismounting is successful.
