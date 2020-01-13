


**Homepage**


After you log in, the left side is the menu for each level, representing a list of different function modules. Click on the top < arrow to collapse the left menu and click the > arrow to expand the menu. 

On the right is the functional display and operating area. In the upper right corner of the right area is the Quick Search Information function area. You can click the button to view the corresponding information. From left to right are "Home", "Notification", "Operation History", "About", "Help Center" and "Account Information". 



# Homepage


Click "Home" in the top right corner to view the homepage details, including:

 My account: icon, display name, role, business group, last login time

 Pending tasks: The number of pending deployments and requests. Click the link to enter “Pending Approval” and “Pending Requests”

 Alert information (warning, danger)

 Service Information: Requested cloud resource service:

-   Number of services in approval: Click on the link to go to Deployment - My Deployment to view the deployment in the approved state.

-   Number of deployed services: Click on the link to go to Deployment - My Deployment to view the deployments that are running, in progress, closed, failed, and cancelled.

-   The number of services that are about to expire: Click on the link to go to Deployment - My Deployment to view the deployment that will expire in two weeks.

-   The number of services to be dismounted: Click on the link to go to Deployment - My Deployment to view the deployment that will be dismounted within two weeks.

Work order Service:

-   The number of approvals (i.e. the number of manual work order requests waiting for approval), click on the link to enter the “Requests” - “My Requests”, the request type is manual work order service, and the application status is pending	 approval.

-   The number of services in process (i.e. the number of manual work order requests being processed), click on the link to enter the “Requests” - “My Requests”, the request type is manual work order service, and the application status is in progress.

-   Request Service：Click on the link to enter the Service Catalog to apply for the service or resource you need.

Resource information:

-   The number of virtual machines (that is, the number of deployed cloud host instances). Click the link to go to the “Deployments” - “Instances” page to view the instance details.

-   Number of applications (i.e. the number of software resources for cloud resources), click on the link to go to "Deployments" - "Cloud Resources" - "Software Resources" - "Software" to view software details

-   Other resources (i.e. the total number of cloud resources except instances and applications), click on the link to enter “Deployments” – “Cloud Resources” 

-   Total number of CPUs, total memory, total storage, click on the link to access the “Dashboard” - “Cloud Resource Usage” to view the specific usage of CPU, memory and storage



My requests: Display the latest five request information, including the request number, request time, click the request number to jump to the service request details page; click More to enter the "My Requests" service request list 

Alert information: alerts for instances and applications, total number of alerts that trigger both danger and warning, the percentage of warnings in the total number of alerts, the percentage of dangers in the total number of alerts, and the pie chart is formed according to the percentage. Click the link to Go to "Monitor & Alert" - " Triggered Alerts" to view the details of the alert information.



# Navigation Bar


The default tenant administrator has permission to view all features. The left navigation bar displays different functions according to different permissions. The default tenant administrator can view all the menus. The remaining roles have different viewing areas according to the assigned permissions.

SmartCMP Hybrid Cloud Application Management Platform supports permission settings for multiple roles. The system has basic roles including:

-   Maximum privilege: system administrator

-   Tenant level: tenant administrator, software architect, infrastructure administrator, and tenant member

-   Business group level: business group administrators and business group members

-   Project level: project manager and project members

-   You can also customize the role and assign permissions to the role.



## Service catalog
End user can request the service in a self-service manner through the service catalog

## Request
+	My Requests：Service requested by the user
+	Pending Approval：Pending approval service requests 
+	Approved：Service requests approved
+	Pending Requests：Pending service requests
+	Processed：Processed service requests
+	All Requests：Default tenant administrator can view all service requests

## Deployments	
+	My Deployments：After end user requests, the system will generate an instance corresponding to the blueprint, which means deploying the application corresponding to the blueprint. End users can perform various operations in the service deployment.
+	Instances：Manage instances applied through the service catalog, guide-applied instances or imported instances. The administrator can monitor the status of the instances, the information about the related physical host, and perform the operation and maintenance operations of the operation and maintenance to directly manage the application or cloud host. 
+	Resources：Shows various resources user applied successfully, such as storage resources, container services, network resources, PaaS resources and software resources.
+	Host Map：Shows the health status of instances and containers
+	Recycle Bin：All services are manually removed or automatically dismounted after expiration and placed in the Recycle Bin for retention. Support restorage from the recycle bin, manually deletion (all resources are deleted from the cloud platform after deletion), or set the retention time for the recycle bin and automatically delete at expiration (support to set the recycle bin retention time to 0 days, that is, the service is not reserved in recycle bin) 



## Monitor & Alert
Subscribe to host alerts and define response behavior to alerts:
+	Alert Policy：Defines the conditions under which the selected object type (such as instances/application/container, etc.) triggers an alert. 
+	Alert Rules：Defines the scope to which the selected alert policy is applied and the notifications and actions that are triggered 
+	Triggered Alerts：Shows a list of triggered alerts
+	Host Monitoring：View host health in each platform in the current system
+	Host Alerts：Subscribe, edit, delete, and refresh the alarm information of the cloud platform

## Reports & Usage
Provide analysis reports for the use of various resources:
+	DataCenter Status：Data Center Geographical Map, Overview of Data Center Resource Usage, Large Screen Display
+	Allocation Trend
+	Biz Group Usage：analyze the use of different types of resources by different business groups over a period of time
+	Reposts：billing reports, cloud platform overview reports, and other custom reports


## Infrastructure	
+Cloud Entries：Such as cloud platform type, name, username and password, etc.
+	Resource Bundles：Such as vCPU, memory, number of virtual machines, network, etc.
+	VM Templates：Unified management of templates and images for various cloud platforms
+	Compute Profiles：Define computing profiles of different specifications based on CPU and memory.
+	IPAM：IP range that each NIC can use per virtual machine
+	Key Pairs：Generate and manage the required key pair for the virtual machine
+	Digital Sequences：Management of numeric or character suffixes in naming rules
+	Physical Host：Manage physical hosts

## Organization
+	Business Group：Administrators quota infrastructure in the form of business groups so that infrastructure administrators can distribute infrastructure
+	Projects：Administrators can allocate users in a business group into different projects and share virtual machines among project members.
+	Users：Add, delete, change, check, etc. for users, associate roles for users, and associate business groups.
+	Roles：Permission definitions for different user groups, or custom roles. Predefined roles includes tenant administrator, tenant member, software architect, infrastructure administrator, business group administrator, business group member, project administrator, project member
+	Service Groups：Administrators customize different types of service teams to support associated users

## Service Design	
+	Script Library：Customize scripting software components that you want to perform manually
+	SW Components：Components are the basic unit that makes up a blueprint, and the components contain two types (infrastructure and software components) 
+	Blueprints：Software architects can design application blueprints based on the TOSCA standard through a blueprint management interface. A blueprint is an abstraction of an application. The blueprint contains the topology, workflow, and policy of the application.
+	Form：When creating or configuring services (including cloud resource deployment services and manual request services), you can select the built-in forms (including IP pool creation forms, project creation forms). If you need to modify or add additional field information for users to fill in at the time of application, you can customize the configuration form through the form designer. 
+	Catalog Config：IT administrators can publish blueprints as service and associate them with organizational structures and service catalogs. In addition, integration with third-party systems (such as approval processes, billing systems, etc.) can be achieved through service. 
+	Workflows：Customize the order and policy of each step of activity or task execution, customize the workflow template through the process designer, including cloud resource blueprint service process, manual request service process, approval process
+	Catalog Groups：Custom service types

## Capacity
Subscribe to resource bundle quotas and IP pool alerts and define response behavior to alerts
+	Infra Alert Rules：The resource alert monitors the usage of resource quotas. When the preset conditions are met, an alert is triggered.
+	Triggered Alert：Defines what needs to be done after the alert has been triggered

## Billing & Usage	
+	Cost Analysis：Shows the cost ratio of each business group and time-span cost trend, and can be filtered based on time, cloud platform, resource type, business group, project, and owner. 
+	Cost Optimization：Shows the usage of cloud resources, as well as the cost situation, finds resources with low usage rate, and can directly adjust the configuration. 
+	Billing Rules：Define billing criteria for each resource specification (CPU, memory) and resource category
+	Billing Sync：Timed synchronization of public cloud billing data

## Governance	
+	Event：Define the scope to which the event is applied and the notifications and actions that are triggered

## Settings
+   System：User login type, DNS configuration
+   Notifications：SMTP mail, SMS, Enterprise WeChat, DingTalk, send system notifications, alarms and other messages to the connected message notification platform
+	Menu：Define multiple dashboards or access third-party systems and set different roles to view and customize the location of the extended menu.
+	Report：Set the enable/disable status of the report and the role to be assigned

## Backup and Security
+   Bastion Host: Add details of the bastion host that needs to be connected and managed.
+	Backup system: Add details of the backup recovery management system that needs to be connected and managed.
+	Audit: Users can view all login and operation information recorded by the cloud platform.



# Notifications


Click "Notification" in the upper right corner to view the list of currently unread messages. The notifications include messages (such as waiting for approval), alert notifications, etc. The notifications in the list can be marked as read and will not be prompted. Clicking on a notification in the list will take you to the notification details page.

Click "View All Notifications" under the list to go to the list of all notifications. Advanced Search can be used for quick search and positioning by the start and end time the notification was created, or for general query search. Notifications can be deleted individually or in bulk.

# Operation History


Click on "Operation History" in the top right corner. The list shows the current operation, the name of the operation, the name of the service, the requesting user, and the creation time. You can click on an action message to enter the operation history details page. You can also click "View All" to enter the operation history list interface. Click on an action and the action history details are displayed below the list. You can use the "Advanced Search" to quickly search and search based on the business group, requesting user, start and end time, and status. Or you can use ordinary search.

# Documentation
Click on the question mark icon in the upper right corner to go directly to the online documentation. You can view the product basic concepts, administrator manual and user manual online to learn about the basic concepts and functions of SmartCMP.

>「Note」 The administrator can hide "About” or "Help Document" in the upper left corner of the homepage navigation bar in "System Configuration"-"Interface Settings".
