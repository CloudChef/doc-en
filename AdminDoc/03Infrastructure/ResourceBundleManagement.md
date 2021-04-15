



**Resource Bundle Management**
 

The infrastructure administrator manages the private cloud, the public cloud, the hybrid cloud, the container, the physical machine, and the mainstream network resources, and pools various resources to form a resource bundle.

The administrator allocates the resource bundle to the business group to implement the segmentation of the cloud platform resources. You can specify the resource bundle to use the specific resources of the target cloud platform. For example, you can customize the resource bundle to associate the storage resource and network resource with the development resource bundle. Through the resource bundle, specify the resource quotas that can be used, such as the total number of virtual machines allowed to be deployed, the total amount of vCPUs allowed, the total amount of memory, and so on.


# Add a Resource Bundle

+ After the cloud platform is successfully added, the cloud platform resources are divided into one or more resource bundles, and the corresponding resource quotas are allocated to different business groups. 

    The relationship between resource bundles and business groups is divided into three types:
    - Resource bundle is only assigned to a unique business group
    - Resource bundle is assigned to all business groups, and the newly added business group automatically associates the resource bundle
    - Resource bundles are shared to multiple business groups

+  Support resource bundle replication. Usage scenarios: When an administrator configures multiple clusters for vCenter, each business group needs to configure these clusters as resource bundles, allowing administrators to quickly create resource bundles with the same or similar configuration. Specific operation steps: In the left navigation, select "Infrastructure" and select "Resource Bundle Management". In the list of resource bundles, select a resource bundle and click the copy button (When multiple resource bundles are selected, the copy button will not work.) to generate a new resource bundle creation page. The name of the copied resource is automatically changed to "<original resource bundle name> -1" (for example, the original resource bundle name is vSphereDemo, and the copied one is vSphereDemo-1). All configurations are the same as the original resource bundle. The administrator can modify the related parameters of the original resource bundle, including the assigned business group and the sharing mode. 

+  Support resource bundle enable or disable. When the administrator is creating and editing a resource bundle, a selection button is added below the priority to enable the resource bundle, which is selected by default. Resource bundles, whether enabled or disabled, can be assigned to business groups. After disabling, when deploying cloud resources, the selection of this resource bundle is not supported, but the existing resources are not affected in any way.




## Add a vSphere Resource Bundle {#AddavSphereResourceBundle}

You can add a vSphere resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "vSphere". The Create Resource Bundle interface will appear. Follow the form to fill in the relevant information and save it.

2.  Fill in the following information on the Basic Information page:

 + Name	Resource Bundle Name
 + Allow sharing to multiple business groups	Checked: If all business groups are selected, the global shared resource bundle are configured and new business group will be automatically associated. If multiple service groups are selected, they will be shared to multiple service groups. Unchecked: the resource bundle is separately assigned to the only selected business group.
 + Tags	Label the resource bundle to distinguish between different usage environments (optional)
 + Priority	Used to help specify a resource bundle selection policy. The smaller the value, the higher the priority.

 + Platform Entrance	Choose which vSphere to partition the resource bundle.
 + Resource Entrance	Choose which cluster or host to use (including clusters and physical hosts that are not in the cluster)
 + Folder	Select folder (optional)



3.  “Compute Resources” page displays basic resource entry information, and fills in the following based on the resource entry information:

 +  vCPU                     Maximum allowable number of vCPU deployment
 +  Memory (GB)               Maximum allowable capacity of memory (GB)
 +  VM number                 Maximum allowable number of virtual machines
 +  Snapshot                  Maximum number of snapshots allowed per virtual machine
 +  vSphere Resource Bundle            Resource bundle Which stores the deployed VM
 +  Host selection           Limited memory or storage priority            
 +  Storage                    Select the storage and storage quotas for the VM deployment. Configure a resource bundle of the appropriate size according to the actual situation. If the resources are too small, the subsequent deployment will be affected.

4.  Network resources: select the network and IP allocation mode (manually specified, IP pool, DHCP); if you select an IP pool, you need to select the corresponding IP pool under the IP address management column. A description can be added to the network. When the service configuration is selected, the description information will be displayed for easy selection. 

5.  Click the “Save” button to successfully create a vSphere resource bundle.

## Add a vSphere with NSX Resource Bundle {#Add a vSphere with NSX Resource Bundle}

The prerequisite for adding vSphere with an NSX resource bundle is the need to associate VMware NSX with the vSphere cloud platform.

You can add a vSphere with NSX resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "vSphere". The Create Resource Bundle interface will appear. Follow the form to fill in the relevant information and save it.

2.  Fill in the following information on the Basic Information page:

 + Name	Resource Bundle Name
 + Allow sharing to multiple business groups	Checked: If all business groups are selected, the global shared resource bundle are configured and new business group will be automatically associated. If multiple service groups are selected, they will be shared to multiple service groups. Unchecked: the resource bundle is separately assigned to the only selected business group.
 + Tags	Label the resource bundle to distinguish between different usage environments (optional)
 + Priority	Used to help specify a resource bundle selection policy. The smaller the value, the higher the priority.

 + Platform Entrance	Choose which vSphere to partition the resource bundle.
 + Resource Entrance	Choose which cluster or host to use (including clusters and physical hosts that are not in the cluster)
 + Folder	Select folder (optional)
 + VMware NSX Transmission Area	Used to configure the NSX logical switch. If not selected, the NXS Logical Switch subpage will not be displayed on the Network Resources page.

3.  Computation Resources: same as the previous section [Add a vSphere Resource Bundle](#AddavSphereResourceBundle)


4.  Network resources:


 + Network resources	Select the network and the IP allocation mode of the network among manual assignment, IP pool, and DHCP. If you choose the IP pool allocation mode, you need to specify an IP pool. A description can be added to the network.
 + Distributed virtual exchange	  Select virtual switch
 + NSX Logical switch	  Select the logical switch and the corresponding IP pool
 + NSX Logical router	Select NSX Logical Router
 + NSX Service Gateway	Select NSX Service Gateway
 + NSX Security Policy Group	Select the security policy group to apply to this resource bundle

>「Note」Configure at least one between network resource and NSX logical switch

5.  Click the “Save” button to successfully create a vSphere with NSX resource bundle.

## Add OpenStack Resource Bundle {#Add OpenStack Resource Bundle}

You can add an OpenStack resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "OpenStack". 

2.  Fill in the following information on the Basic Information page:

 + Name	Resource Bundle Name
 + Allow sharing to multiple business groups	Checked: If all business groups are selected, the global shared resource bundle will be configured and new business group will be automatically associated. If multiple service groups are selected, they will be shared to multiple service groups. Unchecked: the resource bundle is separately assigned to the only selected business group.
 + Tags	Label the resource bundle to distinguish between different usage environments (optional)
 + Priority	Used to help specify a resource bundle selection policy. The smaller the value, the higher the priority.

 + Cloud Entry	Choose which OpenStack partition resource bundle
 + Availability zone	Choose which available area to use
 + DNS Domain	According to the DNS domain added in Settings - System, you can choose to add one or more DNS domains to the resource bundle.

>「Note」 DNS domain needs to be a subdomain of the tenant DNS domain name. 


3.  Compute Resource: Fill in the following content according to the resource information content:

 +  vCPU         Maximum allowable number of vCPU deployment
 + Memory (GB)   Maximum allowable capacity of memory (GB)
 +  Storage (GB)   Maximum allowable capacity of storage (GB)
 +  VM number     Maximum allowable number of virtual machines
 +  Floating IP   Maximum reserved floating IP number 

>「Note」Support separate deployment for floating OpenStack IP. After the deployment is complete, you can view it in Deployment - Instances - Network Resources - Floating IP. If the number of Floating IP created during deployment exceeds the number of Floating IP specified by the resource bundle, the deployment fails.

4.  On the “Network Resources” page, there are three tabs: “Network Resources”, “Security Policy Group” and “Firewall”. 
-   Network Resources: Select the network and the corresponding subnet, IP allocation mode (manually specified, IP pool, DHCP). If selecting IP pool, you need to specify an IP pool. A description can be added to the network. When the service configuration is selected, the description information will be displayed for easy selection. 

-   Security Policy Group: Select one or more security policy groups

>「Note」network resources and security policy groups must be configured

-   Firewall: You can view the firewall name, description, policy, associated route, status (running, inactive) under the current cloud platform, and select one or more firewalls. 

5.  Routing: You can specify a route (optional). If you need to configure a firewall, you need to select a route here

6.  Click the “Save” button to successfully create a vSphere with NSX resource bundle.

## Add PowerVC Resource Bundle {#Add PowerVC Resource Bundle}

You can add a PowerVC resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "PowerVC". 

2.  Fill in the following information on the Basic Information page:


 + Name	Resource Bundle Name
 + Tags	Label the resource bundle to distinguish between different usage environments (optional)
 + Priority	Used to help specify a resource bundle selection policy. The smaller the value, the higher the priority.
 + Cloud Entry	Choose which OpenStack partition resource bundle
 + Availability zone	Choose which available area to use
 + Allow sharing to multiple business groups	Checked: If all business groups are selected, the global shared resource bundle will be configured and new business group will be automatically associated. If multiple service groups are selected, they will be shared to multiple service groups. Unchecked: the resource bundle is separately assigned to the only selected business group.


3.  Compute Resource: Fill in the following content according to the resource information content:


 + vCPU         Maximum allowable number of vCPU deployment
 + Memory (GB)   Maximum allowable capacity of memory (GB)
 +  Storage (GB)   Maximum allowable capacity of storage (GB)
 +  VM number     Maximum allowable number of virtual machines

 4.  Network Resources: Select the network and the corresponding subnet, IP allocation mode (IP pool, DHCP). If selecting IP pool, you need to specify an IP pool. A description can be added to the network. When the service configuration is selected, the description information will be displayed for easy selection. 

 5.  Click the “Save” button to successfully create a PowerVC resource bundle.

## Add Microsoft Hyper-V Resource Bundle {#Add Microsoft Hyper-V Resource Bundle}

You can add a Hyper-V resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Hyper-V". 

2.  Fill in the following information on the Basic Information page:


 + Name	Resource Bundle Name
 + Allow sharing to multiple business groups	Checked: If all business groups are selected, the global shared resource bundle are configured and new business group will be automatically associated. If multiple service groups are selected, they will be shared to multiple service groups. Unchecked: the resource bundle is separately assigned to the only selected business group.
 + Business Group	Select the business group to which the resource bundle belongs.
 + Tags	Label the resource bundle to distinguish between different usage environments (optional)
 + Priority	Used to help specify a resource bundle selection policy. The smaller the value, the higher the priority.

 + Cloud Entry	Choose which OpenStack partition resource bundle
 +  Resource Entry	Choose which cluster or host to use (including clusters and physical hosts that are not in the cluster)


3.  ③	Compute Resource: Fill in the following content according to the resource information content：


 + vCPU         Maximum allowable number of vCPU deployment
 + Memory (GB)   Maximum allowable capacity of memory (GB)
 + VM number     Maximum allowable number of virtual machines

 + Storage	Select the storage and storage quotas for the VM deployment. Configure a resource bundle of the appropriate size according to the actual situation. If the resources are too small, the subsequent deployment will be affected.
 + Reserved space	Check the corresponding cluster shared volume CSV and fill in the reserved space.


4.  Network Resources: Select the network and the corresponding subnet, IP allocation mode (IP pool, DHCP). If selecting IP pool, you need to specify an IP pool. A description can be added to the network. When the service configuration is selected, the description information will be displayed for easy selection

5.  Click the “Save” button to successfully create a Hyper-V resource bundle.

## Add Physical Server Resource Bundle {#Add Physical Server Resource Bundle}

You can add a Physical Server resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Physical Server". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, priority, and other attributes.

3.  Select the physical machine on the Physical Host page and import the selected physical machine into the resource bundle of the x86 cloud platform. 

4.  Click the “Save” button to successfully create a Physical Server resource bundle.

## Add Kubernetes Resource Bundle {#Add Kubernetes Resource Bundle}

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Kubernetes". 

2.  Basic Information: Fill in the Resource bundle Name, Resource Tag (optional), Cloud Platform Portal, Namespace, and Priority on the page.

3.  Computing Resource: Fill in the number of PODs

4.  Click the “Save” button to successfully create a Kubernetes resource bundle.

## Add Docker Resource Bundle {#Add Docker Resource Bundle}

You can add a Docker resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select " Docker ". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, container limit (optional), and priority

3.  Host List: Display information about the host, such as name, operating system, architecture, server version, number of CPUs, memory, etc.

4.  Click the “Save” button to successfully create a Docker resource bundle.

## Add NFS Resource Bundle {#Add NFS Resource Bundle}

You can add a NFS resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select " NFS ". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, priority, and other attributes.

3.  Shared Folders: Add several NFS shared directories

4.  Click the “Save” button to successfully create a vSphere with NSX NFS resource bundle.

## Add Aliyun Resource Bundle {#Add Aliyun Resource Bundle}

You can add an Aliyun resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Aliyun". 

2.  Basic Information: Fill in the resource bundle name, resource label (optional), cloud platform portal, network type (classic network and private network) and priority. When the network type is a proprietary network, you also need to select a proprietary network from the list.

3.  Computing Resources: Fill in the number of vCPUs (upper limit), memory (upper limit), and number of virtual machines (upper limit) 

4.  Network Resources: Select the available Aliyun Security Policy Group. If the network type is a proprietary network, you also need to select the virtual switch.

5.  Click the “Save” button to successfully create an Aliyun resource bundle.

## Add Tencent Cloud Resource Bundle {#Add Tencent Cloud Resource Bundle}

You can add a Tencent Cloud resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Tencent Cloud". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, priority, and other attributes.

3.  Compute Resources: Fill in the number of vCPUs, memory size and number of virtual machines.

4.  Network Resources: Select the appropriate security group.

5.  Click the “Save” button to successfully create a Tencent Cloud resource bundle.

## Add QingCloud Resource Bundle {#Add QingCloud Resource Bundle}

You can add a QingCloud resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "QingCloud”. 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, priority, and other attributes.

3.  Compute Resources: Fill in the number of vCPUs, memory size and number of virtual machines.

4.  Firewall: Select a firewall policy 

5.  Click the “Save” button to successfully create a QingCloud resource bundle.

## Add AWS Resource Bundle {#Add AWS Resource Bundle}

You can add an AWS resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "AWS". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), priority, cloud platform portal, zone and VPC network.

3.  Compute Resources: Fill in the number of vCPUs, memory size and number of virtual machines.

4.  Network Resources: Select the subnet and security policy group.

5.  Click the “Save” button to successfully create an AWS resource bundle.

## Add F5 Big IP Resource Bundle {#Add F5 Big IP Resource Bundle}

You can add a F5 Big IP resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "F5 Big IP". 

2.  Basic Information: Fill in the resource bundle name, service group, resource label (optional), cloud platform portal, IP pool, and allow sharing to multiple service groups.

>「Note」For the shared status of the associated service group and resource bundle, refer to: [Add Resource Bundle to Business Group](https://cloudchef.github.io/doc-en/AdminDoc/04Organization/BusinessGroup.html#Add%20Resource%20Bundle%20to%20Business%20Group)

3.  Click the “Save” button to successfully create a F5 Big IP resource bundle.

>「Note」F5 Big IP resource bundle needs to be associated with an IP pool before it can be saved. If there is no corresponding IP pool of F5 Big IP, you need to add the corresponding IP pool to complete the creation of the resource bundle. Please refer to [Add an IP Pool](https://cloudchef.github.io/doc-en/AdminDoc/03Infrastructure/IPAM.html#add-an-ip-pool)。

## Add CISCO ACI Resource Bundle {#Add CISCO ACI Resource Bundle}

You can add a CISCO ACI resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "CISCO ACI". 

2.  Basic Information: Fill in the resource bundle name, resource tag (optional), cloud platform entry, priority, and other attributes.

3.  Network Resources: Select an application policy

4.  Click the “Save” button to successfully create a CISCO ACI resource bundle.

## Add Azure Resource Bundle {#Add Azure Resource Bundle}

You can add an Azure resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. Click the "Add" button and select "Azure". 

2.  Basic Information: There are the “Basic Information” and “Cloud Platform Resource Information” sections. Fill in the resource bundle name, resource tag (optional) and priority in "Basic Information". If "Allow share to multiple business groups" is checked, this resource bundle can be used by multiple business groups. In "Cloud platform resource information" you need to select cloud platform portal, input subscription ID, selection area, resource group and virtual network. 

3.  Compute Resources: Fill in the number of vCPUs (upper limit), memory (upper limit), and the number of virtual machines (upper limit).

4.  Network Resources: Including Subnets and Security Policy Groups tab.

-   Subnet: Select the subnet and IP assignment method (manually specified, IP pool, DHCP). You can assign an internal private IP address by manually specifying and IP pool mode. If you select IP pool mode, you need to select the corresponding IP pool under IP pool management. 

-   Security Policy Group: Select a security policy group

5.  Storage Resources: Select a storage account.

6.  Click the “Save” button to successfully create an Azure resource bundle.


# Resource Bundle Selection Strategy

In the service configuration, to configure the instance node, you need to pay attention to the resource bundle selection strategy. The platform mainly provides the following strategies:
+ Manually Specify One: Manually designate the resource bundle. If the resource bundle selection strategy selects "Manually Specify One", the resource tag is supported to narrow the selection range, and the "resource bundle" option will appear. Select the resource bundle in the drop-down box and specify the resource bundle. You can choose to check "Allow Change" and "In Approval Only".
+ Use the largest remaining capacity: the platform automatically selects the currently selectable resource bundle according to the strategy, with the smallest resource usage and the largest remaining capacity.
+ Use the lowest cost: The platform supports the setting of resource billing rules, and selects the currently selectable resource bundle according to the strategy, with the lowest cost.
+ Evenly distribute: When the service is deployed, resources are evenly distributed to different resource bundles. (The premise of even distribution is that the selected resource bundle has sufficient resources.)

>「Note」Resource tag comes from the administrator's configuration in "Infrastructure"-"Resource Tags". For specific configuration reference, please refer to: [Resource Tags](http://CMP-PUBLIC-IP/help/AdminDoc/03Infrastructure/ResourceTag.html). According to the tag, select the resource bundle that matches the tag to deploy the application to a specific resource bundle.


# View the Current Tenant Resource bundle

You can view the resource bundle by following the steps below: 

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”. The resource bundle list interface will be displayed. This list shows the basic information of the currently added resource bundle: resource bundle name, type, cloud platform portal, business group, priority, creator, creation time, allocated vCPU, allocated memory, allocated storage, assigned virtual machine Quantity.

2.  Click the resource bundle name to enter the resource bundle page.

3.  Click on the Resource Usage Trends menu, which visually shows resource bundle usage in the form of a graph, including CPU usage, memory usage, storage usage, and the number of virtual machines used. You can adjust the resource usage trend of different time periods by adjusting the time span, such as 1 day, 7 days, 15 days, 30 days, 90 days, 6 months, 1 year, etc.

The operations that can be performed vary depending on the user's role permissions:

Tenant administrators and infrastructure administrators can edit and modify resource bundle information.

Business group administrator can view the resource bundle quota information and submit the application for expansion：

1.  On the resource list interface, click the resource bundle name to enter the resource bundle editing interface.

2.  Click on “Apply for Capacity Expansion” in the upper left corner to fill in the details of resource expansion: CPU, memory, storage details, etc.

3.  Click “Submit” to prompt the application for expansion. Waiting for the expansion request to be approved. You can check the progress of the request process in "Requests" - "My Requests"

# Import a Resource bundle into a Virtual Machine

You can add a virtual machine by following the steps below:

1.  In the left navigation, select “Infrastructure” and select the secondary menu “Resource Bundles”.

2.  Click the resource bundle name or select a resource bundle and click “Edit” to enter the resource bundle editing interface.

3.  Click the “Cloud Resources” tab and click the “Import” button to import the page, which can be filtered according to the business group, project, owner, and label. You can also choose a cluster and select the virtual machine you want to import. Click "Import"

4.  ④	The imported virtual machine can be viewed in Deployments - Instances. It can be distinguished by the icon under the status bar in the instance list.¬

>「Note」Resource bundle needs to be associate with the business group before it can be imported into the VM.

# Resource bundle Synchronization Policy 

You can set a synchronization policy in the resource bundle to synchronize the new resources of the cloud platform. The supported synchronization objects are as follows:

-   AWS support: Virtual machine, block storage, object storage, security groups 

-   Azure support: Virtual machine, block storage, object storage, security groups, load balancers, MySQL databases, SQL databases, web applications

-   vSphere and OpenStack support: Virtual machine

Go to the navigation bar "Infrastructure" - "Resource Bundles" - Select Resource bundle - "Sync Policy" tab to add, edit, delete, enable and disable synchronization policies. You can set up a resource bundle synchronization policy by following the steps below:

1.  Click “Add” to enter the synchronization policy configuration interface.

2.  Select the synchronization object type: click the object type to select it, click again to deselect

3.  Enter the name of the synchronization policy

4.  Select the association between the business group and the resource bundle. For details: [业务组与资源池](http://CMP-PUBLIC-IP/help/AdminDoc/04组织架构管理/业务组.html#业务组添加资源池)

5.  If there are multiple projects under the business group, select the project

6.  Select owner 

7.  Filtering: Filter out new resources from the cloud platform through "tags" and "name-based regular expressions"

8.  Status: Enabled or Disabled

9.  Execution time: Set the execution time of the synchronization policy using the Cron expression

10. Policy Management: Enable, Disable; Delete, Modify Synchronization Policy

# Modify/Delete a Resource bundle Configuration

In the left navigation, select "Infrastructure" and select the secondary menu "Resource Bundle".

Edit the resource bundle: Click the resource bundle name or select a resource bundle and click Edit. The resource editing interface appears. Modify the existing resource bundle according to the parameter list of adding the OpenStack resource bundle and adding the vSphere resource bundle. After the modification is completed, click "Save".

Delete a resource bundle: Select a resource bundle and click "Delete" to confirm the deletion.

>「Note」If a resource bundle is associated with a business group, the deletion will fail.