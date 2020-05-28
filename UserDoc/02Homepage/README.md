**Homepage**

After you log in, the left side is the menu for each level, representing a list of different function modules. Click on the top < arrow to collapse the left menu and click the > arrow to expand the menu. 

On the right is the functional display and operating area. In the upper right corner of the right area is the Quick Search Information function area. You can click the button to view the corresponding information. From left to right are "Home", "Notification", "Operation History", "About", "Help Center" and "Account Information". 
#Homepage


Click "Home" in the top right corner to view the homepage details, including:

 My account: icon, display name, role, business group, last login time

 Pending tasks: The number of pending deployments and requests. Click the link to enter “Pending Approval”and “Pending Requests”

 Alert information (warning, danger)

 Service Information:Requested cloud resource service:

-   Number of services in approval: Click on the link to go to Deployment - My Deployment to view the deployment in the approved state.

-   Number of deployed services: Click on the link to go to Deployment - My Deployment to view the deployments that are running, in progress, closed, failed, and cancelled.

-   The number of services that are about to expire: Click on the link to go to Deployment - My Deployment to view the deployment that will expire in two weeks.

-   The number of services to be dismounted: Click on the link to go to Deployment - My Deployment to view the deployment that will be dismounted within two weeks.

Ticket Service:

-   The number of approvals (i.e. the number of manual ticket requests waiting for approval), click on the link to enter the “Requests” - “My Requests”, the request type is manual ticket service, and the application status is pending approval.

-   The number of services in process (i.e. the number of manual ticket requests being processed), click on the link to enter the “Requests” - “My Requests”, the request type is manual ticket service, and the application status is in progress.

-    Request Service：Click on the link to enter the Service Catalog to apply for the service or resource you need.

Resource information:

-   The number of virtual machines (that is, the number of deployed cloud host instances). Click the link to go to the “Deployments” - “Instances” page to view the instance details. 

-   Number of applications (i.e. the number of software resources for cloud resources), click on the link to go to "Deployments" - "Cloud Resources" - "Software Resources" - "Software" to view software details

-   Other resources (i.e. the total number of cloud resources except instances and applications), click on the link to enter “Deployments” – “Cloud Resources” 

-   Total number of CPUs, total memory, total storage, click on the link to access the “Dashboard” - “Cloud Resource Usage” to view the specific usage of CPU, memory and storage.



My Requests: Display the latest five request information, including the request number, request time, click the request number to jump to the service request details page; click More to enter the "My Requests" service request list 

Alert information: alerts for instances and applications, total number of alerts that trigger both danger and warning, the percentage of warnings in the total number of alerts, the percentage of dangers in the total number of alerts, and the pie chart is formed according to the percentage. Click the link to Go to "Monitor & Alert" - " Triggered Alerts" to view the details of the alert information.

# Navigation Bar


Left Navigation Bar detail:
	

 Service Catalog：End user can request the service in a self-service manner through the service catalog

 Requests：	

 + My Requests：Service requested by the user

 + Pending Approval：Pending approval service requests 

 + Approved：Service requests approved

 + Pending Requests：Pending service requests

 + Processed：Processed service requests


 Deployments

 + My Deployments：After end user requests, the system will generate an instance corresponding to the blueprint, which means deploying the application corresponding to the blueprint. End users can perform various operations in the service deployment.

 + Instances：Manage instances applied through the service catalog, guide-applied instances or imported instances. The administrator can monitor the status of the instances, the information about the related physical host, and perform the operation and maintenance operations of the operation and maintenance to directly manage the application or cloud host. 

 + Resources：Shows various resources user applied successfully, such as storage resources, container services, network resources, PaaS resources and software resources.

 + Host Map：Shows the health status of instances and containers

 + Recycle Bin：All services are manually removed or automatically dismounted after expiration and placed in the Recycle Bin for retention. Support restorage from the recycle bin, manually deletion (all resources are deleted from the cloud platform after deletion), or set the retention time for the recycle bin and automatically delete at expiration (support to set the recycle bin retention time to 0 days, that is, the service is not reserved in recycle bin) 


 Dashboard：Users may view in dashboard: Cloud resource distribution, Instance overview, InstanceOS distribution, Instance with alerts, Ongoing operations, service deployments to be expired,service deployments to be uninstalled, Instances with the highest CPU/memory/disk usage - Top10, Instances with the lowest CPU/memory/disk usage - Top10


 
 Monitor & Alert: Subscribe to host alerts and define response behavior to alerts:

 + Alert Policy：Defines the conditions under which the selected object type (such as instances/application/container, etc.) triggers an alert. 
 
 + Alert Rules：Defines the scope to which the selected alert policy is applied and the notifications and actions that are triggered 
 
 + Triggered Alerts：Shows a list of triggered alerts


 Reports & Usage: Provide analysis reports for the use of various resources:
 
 + Reposts：billing reports, cloud platform overview reports, and other custom reports



# Notifications


Click "Notification" in the upper right corner to view the list of currently unread messages. The notifications include messages (such as waiting for approval), alert notifications, etc. The notifications in the list can be marked as read and will not be prompted. Clicking on a notification in the list will take you to the notification details page.

Click "View All Notifications" under the list to go to the list of all notifications. Advanced Search can be used for quick search and positioning by the start and end time the notification was created, or for general query search. Notifications can be deleted individually or in bulk.

# Operation History


Click on "Operation History" in the top right corner. The list shows the current operation, the name of the operation, the name of the service, the requesting user, and the creation time. You can click on an action message to enter the operation history details page. You can also click "View All" to enter the operation history list interface. Click on an action and the action history details are displayed below the list. You can use the "Advanced Search" to quickly search and search based on the business group, requesting user, start and end time, and status. Or you can use ordinary search.

# Documentation


Click on the question mark icon in the upper right corner to go directly to the online documentation. You can view the product basic concepts, administrator manual and user manual online to learn about the basic concepts and functions of SmartCMP.

>「Note」When the tenant administrator configures to hide "About" or "Help Documents" in "System"-"Interface Settings", after an ordinary user logs in, "About" or "Help Documents" will not be displayed in the upper left corner of the homepage navigation bar.


# My Credentials

+ Users can create and manage their own credentials. Credentials include two types: keys or passwords. Users save frequently used credentials at a unified entrance. When applying for services and performing change operations, saved identity verification can be directly selected. In addition, users can also use the credentials shared by the tenant administrator and the IaaS administrator.
+ Specific steps for adding credentials:
    + On the "My Credentials" page, enter the key name (only numbers or letters), select the algorithm (RSA) and length which currently supports lengths of 1024, 2048 and 4096.
    + Import key, users can import private key and public key to save in the system for later use. Click "Import Key", enter the key name, and fill in the private key.
    + Steps to create and use password type credentials: when adding (password), fill in the user name, password, and confirm password (the password entered before and after must be consistent).
    + Users choose their own credentials or manually enter their username and password when applying for services.
    + In the operation interface of service deployment, after installing the software, if user need to verify the identity after selecting the node, he can select the credentials created or shared in the drop-down box, or manually input the username and password.